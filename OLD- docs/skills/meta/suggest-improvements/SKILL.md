---
name: suggest-improvements
title: Suggest KB Improvements
description: Audit the knowledge base to identify gaps, thin content, and opportunities for new documentation.
version: 1.0.0
authors: [Agent]
tags: [meta, audit, quality, kb-management]
---

# Suggest KB Improvements

## Purpose
Systematically analyze the knowledge base to find gaps, incomplete sections, outdated content, and opportunities for new playbooks or skills. Helps maintain KB health and ensures comprehensive coverage.

## Inputs
*   `scope` (optional): Area to audit (`all`, specific category, or `skills`/`playbooks`)
*   `focus` (optional): Type of issues to find (`gaps`, `quality`, `outdated`, `all`)
*   `depth` (optional): `quick` (structure only) or `deep` (content analysis)

## Procedure

### 1. Generate Structure Map
First, understand what exists:

```bash
# Get full directory tree
find docs -name "*.md" -type f | sort

# Count docs per category
for dir in docs/*/; do
  echo "$dir: $(find "$dir" -name "*.md" | wc -l) docs"
done
```

### 2. Identify Structural Gaps

**a) Check for missing index files:**
```bash
for dir in docs/*/; do
  if [ ! -f "${dir}index.md" ]; then
    echo "Missing index: $dir"
  fi
done
```

**b) Find orphan docs (not linked anywhere):**
```bash
for file in $(find docs -name "*.md" -type f); do
  basename=$(basename "$file" )
  if ! grep -rq "$basename" docs/; then
    echo "Possibly orphaned: $file"
  fi
done
```

**c) Check for empty categories:**
```bash
find docs -type d -empty
```

### 3. Analyze Content Quality

**a) Find thin content (< 500 chars):**
```bash
find docs -name "*.md" -type f -exec sh -c '
  chars=$(wc -c < "$1")
  if [ "$chars" -lt 500 ]; then
    echo "Thin: $1 ($chars chars)"
  fi
' _ {} \;
```

**b) Find incomplete markers:**
```bash
grep -rn "TODO\|FIXME\|WIP\|TBD\|PLACEHOLDER\|\[\.\.\.\]" docs/
```

**c) Find docs without proper frontmatter:**
```bash
for file in $(find docs -name "*.md" -type f); do
  if ! head -1 "$file" | grep -q "^---"; then
    echo "No frontmatter: $file"
  fi
done
```

**d) Check skill completeness:**
```bash
for skill in docs/skills/*/SKILL.md; do
  missing=""
  grep -q "## Purpose" "$skill" || missing="$missing Purpose"
  grep -q "## Inputs" "$skill" || missing="$missing Inputs"
  grep -q "## Procedure" "$skill" || missing="$missing Procedure"
  if [ -n "$missing" ]; then
    echo "$skill missing:$missing"
  fi
done
```

### 4. Check for Outdated Content

**a) Find old files:**
```bash
# Not modified in 6+ months
find docs -name "*.md" -mtime +180 -type f
```

**b) Check for stale references:**
```bash
# Look for old year references
grep -rn "2022\|2021\|2020" docs/
```

**c) Find broken internal links:**
```bash
grep -roh "\[.*\]([^http].*\)" docs/ | while read link; do
  target=$(echo "$link" | sed 's/.*(\(.*\))/\1/')
  if [ ! -f "docs/$target" ]; then
    echo "Broken link: $link"
  fi
done
```

### 5. Identify Coverage Gaps

**a) Compare to expected categories:**
Expected KB sections for an e-commerce business:
- [ ] `amazon/` - Marketplace operations
- [ ] `website/` - DTC site management
- [ ] `seo/` - Search optimization
- [ ] `ppc/` - Paid advertising
- [ ] `content/` - Content marketing
- [ ] `sales/` - Sales processes
- [ ] `operations/` - Fulfillment, inventory
- [ ] `customer-service/` - Support procedures
- [ ] `branding/` - Brand guidelines
- [ ] `onboarding/` - New hire/customer processes
- [ ] `tools/` - Software documentation
- [ ] `skills/` - Agent capabilities
- [ ] `templates/` - Reusable formats
- [ ] `playbooks/` - Step-by-step guides

**b) Check for skill coverage:**
Every major process should have either a skill or playbook:
- Lead handling?
- Customer complaints?
- Content creation?
- Reporting?
- Competitor analysis?

### 6. Compile Recommendations

Categorize findings by priority:

**🔴 Critical (blocks work):**
- Missing essential docs
- Broken links to key resources
- Outdated procedures that could cause errors

**🟡 Important (degrades quality):**
- Thin content needing expansion
- Missing playbooks for common tasks
- Incomplete skills

**🟢 Nice to Have (improvements):**
- Better organization
- Additional examples
- Cross-linking opportunities

### 7. Generate Action Items

For each finding, suggest specific actions:

```markdown
## Recommended Actions

### 🔴 Critical
1. **Create customer complaint playbook**
   - Location: `docs/playbooks/customer-service/`
   - Use: `create-playbook` skill
   - Priority: This week

### 🟡 Important  
2. **Expand SEO audit skill**
   - Current: 15 lines
   - Missing: Technical SEO checks, tool references
   - Action: Add mobile, Core Web Vitals, schema sections

### 🟢 Nice to Have
3. **Add changelog to older docs**
   - Affected: 12 docs in `operations/`
   - Action: Add last-reviewed date
```

## Example

**Input:** `scope: "skills", focus: "gaps"`

**Output:**

```markdown
# KB Audit Report: Skills

## Summary
- **Total skills:** 7
- **Complete:** 5
- **Needs work:** 2
- **Missing:** 3 recommended

## Findings

### Incomplete Skills

#### 1. `generate-leads` 
**Issues:**
- Missing Example section
- Procedure has only 2 steps
- No output format specified

**Recommendation:** Expand with LinkedIn/email outreach examples

#### 2. `seo-audit`
**Issues:**
- Thin content (420 chars)
- Missing tool references

**Recommendation:** Add Screaming Frog, GSC procedures

### Missing Skills (Recommended)

1. **`analyze-competitors`** - Beyond basic research, deep analysis
2. **`create-report`** - Standard reporting skill
3. **`schedule-content`** - Content calendar management

### Meta-Skills Status ✅
All 4 meta-skills present and complete.

---
*Audit completed: {{date}}*
*Next recommended audit: {{date + 30 days}}*
```

## Output Format

```markdown
# KB Audit Report

## Scope
{{What was audited}}

## Summary Stats
- Total docs: X
- Categories: X
- Skills: X
- Playbooks: X

## Issues Found

### 🔴 Critical (X items)
{{List with file paths and issues}}

### 🟡 Important (X items)
{{List with file paths and issues}}

### 🟢 Nice to Have (X items)
{{List with file paths and issues}}

## Recommended New Content
{{Prioritized list of suggested additions}}

## Next Steps
{{Actionable items}}
```

## Suggested Audit Schedule
- **Weekly:** Quick scan for TODOs and broken links
- **Monthly:** Full content quality check
- **Quarterly:** Coverage gap analysis
