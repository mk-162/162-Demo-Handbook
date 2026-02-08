# Prompt: Update Handbook

## Trigger Phrases

- "Update the docs"
- "Change the handbook"
- "Fix a typo"
- "Update pricing"
- "Change the company description"
- "Edit the brand guidelines"

## Example Input

```
We need to update the pricing page. The Professional tier 
is now £2,000/month instead of £1,500.
```

## Expected Output

Updated file with:
- Correct pricing information
- Descriptive commit message
- Pull Request opened

## Context Required

- [brand.md](../../01-context/brand.md) — Style guide
- File being modified — Latest version

## Tools Required

- github-api — To commit changes

## Notes

- Always fetch latest before editing
- Never commit directly to main
- Use descriptive commit messages
