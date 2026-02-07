---
name: create-playbook
title: Create Playbook
description: Generate a comprehensive step-by-step playbook for any business goal or process.
version: 1.0.0
authors: [Agent]
tags: [meta, documentation, process, playbooks]
---

# Create Playbook

## Purpose
Transform a goal or process description into a detailed, actionable playbook that anyone can follow. Playbooks are the operational backbone of the KB—they turn tribal knowledge into repeatable procedures.

## Inputs
*   `goal` (required): What the playbook should accomplish (e.g., "onboard a new trade customer")
*   `category` (required): Where it belongs (e.g., `sales`, `operations`, `marketing`)
*   `audience` (optional): Who will use this (default: "team member")
*   `tools` (optional): Specific tools/systems involved
*   `existing_docs` (optional): Related docs to reference

## Procedure

### 1. Research Phase
Before writing, gather context:

**a) Search existing KB:**
```bash
# Use find-knowledge skill
grep -rnil --include="*.md" "{goal keywords}" docs/
```

**b) Identify related content:**
- What skills might this playbook use?
- What templates exist that could help?
- Are there partial docs to build on?

**c) List prerequisites:**
- What access/permissions are needed?
- What tools must be set up?
- What knowledge is assumed?

### 2. Outline the Steps
Break the goal into logical phases:
1. **Preparation** - What to gather/check first
2. **Core Actions** - The main steps
3. **Verification** - How to confirm success
4. **Follow-up** - What happens after

Aim for 5-12 steps. If more, consider splitting into multiple playbooks.

### 3. Write Each Step
For every step, include:
- **What** to do (clear action verb)
- **How** to do it (specific instructions)
- **Why** it matters (brief context)
- **Watch out** for common pitfalls

### 4. Apply the Template

```markdown
---
layout: default
title: {{TITLE}}
parent: Playbooks
nav_order: {{NAV_ORDER}}
---

# {{TITLE}}

## Overview
{{One paragraph describing what this playbook accomplishes and when to use it.}}

## Who This Is For
{{Target audience and their role}}

## Prerequisites
- [ ] {{Required access or permission}}
- [ ] {{Tool or system needed}}
- [ ] {{Knowledge or training required}}

## Estimated Time
{{X minutes/hours}}

## Steps

### Step 1: {{Action Verb + Object}}
**Goal:** {{What this step accomplishes}}

{{Detailed instructions. Be specific.}}

**Tools:** {{Software, links, resources}}

**Watch out:** {{Common mistakes or edge cases}}

---

### Step 2: {{Action Verb + Object}}
**Goal:** {{What this step accomplishes}}

{{Detailed instructions.}}

{{Include screenshots or examples where helpful:}}
> Example: "Navigate to Settings → Integrations → Add New"

---

### Step 3: {{Continue pattern...}}

---

## Success Criteria
How do you know the playbook worked?
- [ ] {{Measurable outcome 1}}
- [ ] {{Measurable outcome 2}}
- [ ] {{Verification step}}

## Troubleshooting

### {{Common Problem 1}}
**Symptom:** {{What you observe}}
**Cause:** {{Why it happens}}
**Fix:** {{How to resolve}}

### {{Common Problem 2}}
**Symptom:** {{What you observe}}
**Fix:** {{How to resolve}}

## Related Resources
- [{{Related Doc 1}}]({{link}})
- [{{Related Skill}}]({{link}})

## Changelog
| Date | Change | Author |
|------|--------|--------|
| {{TODAY}} | Initial version | {{Author}} |
```

### 5. Validate the Playbook
Quality checklist:
- [ ] Can a new team member follow this without asking questions?
- [ ] Are all tools/links/credentials referenced?
- [ ] Is there a way to verify success?
- [ ] Are edge cases addressed?
- [ ] Is it the right length (not too brief, not overwhelming)?

### 6. Save Using update-kb Skill
Use the `update-kb` skill to:
1. Save to correct location
2. Update parent index
3. Commit changes

## Example

**Input:**
```
goal: "Set up a new supplier in the system"
category: "operations"
tools: ["Inventory System", "Accounting Software"]
```

**Output:**

```markdown
---
layout: default
title: New Supplier Setup Playbook
parent: Playbooks
nav_order: 3
---

# New Supplier Setup Playbook

## Overview
This playbook walks through adding a new supplier to our systems, from initial vetting through first order placement. Use this whenever procurement identifies a new vendor.

## Who This Is For
Operations team members with system admin access.

## Prerequisites
- [ ] Admin access to Inventory System
- [ ] Accounting Software login
- [ ] Supplier's W-9 or tax documentation
- [ ] Signed supplier agreement

## Estimated Time
30-45 minutes

## Steps

### Step 1: Verify Supplier Documentation
**Goal:** Ensure we have all required paperwork before system entry.

Check that you have received:
1. Completed W-9 form
2. Signed supplier agreement
3. Bank details for payment
4. Primary contact information

**Watch out:** Missing tax docs will block payments later.

---

### Step 2: Create Supplier in Inventory System
**Goal:** Add supplier to product ordering system.

1. Navigate to Suppliers → Add New
2. Enter company details exactly as on W-9
3. Add payment terms (default: Net 30)
4. Upload signed agreement as attachment

---

[...continues...]
```

## Output
- Complete playbook in markdown format
- Ready to save via `update-kb` skill

## Playbook Categories Reference

| Category | Example Playbooks |
|----------|------------------|
| sales | Lead qualification, Quote creation, Contract renewal |
| operations | Supplier setup, Inventory count, Shipping exception |
| marketing | Campaign launch, Content publishing, Email sequence |
| onboarding | New hire, New customer, New tool |
| customer-service | Complaint resolution, Refund processing |
