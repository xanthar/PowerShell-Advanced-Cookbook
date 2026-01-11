# PowerShell Advanced Cookbook - Repository Enhancement Project

## Project Overview

This repository accompanies the book **"PowerShell Advanced Cookbook"** by Morten Elmstrøm Hansen, published by BPB Publications.

- **Original Repository**: https://github.com/bpbpublications/PowerShell-Advanced-Cookbook
- **Purpose**: Enhance the book's companion code repository with detailed, educational, and professional examples

## Project Goals

1. **Professionalize figure scripts**: Transform minimal one-liner examples into comprehensive, educational scripts that reinforce the book's teachings
2. **Add educational value**: Include detailed inline comments explaining *why* commands work, not just *what* they do
3. **Show expected output**: Include comment blocks demonstrating expected output so readers can verify their results
4. **Provide cleanup code**: For scripts that modify system state (registry, certificates), include cleanup sections
5. **Maintain book alignment**: Each figure file corresponds to a specific figure in the book chapter

## Script Standards

### File Header Format
Each script should have a minimal header:
```powershell
# Figure X.XX - [Brief Description]
# Chapter X: [Chapter Title]
# PowerShell Advanced Cookbook - BPB Publications
```

### Comment Style
- **Educational focus**: Explain concepts, not just commands
- **Inline comments**: Describe what each significant line does and why
- **Expected output**: Include sample output in comment blocks where helpful
- **Cleanup sections**: Clearly marked cleanup code for scripts that modify system state

### Code Conventions
- Use full cmdlet names (not aliases) for clarity: `Get-ChildItem` not `gci`
- Use named parameters for complex commands: `-Path "C:\Temp"` not positional
- Include practical, real-world examples where possible
- Demonstrate variations of commands where educational value exists

## Workflow

### Branching Strategy
- **Never commit directly to main**
- Create feature branches per chapter: `feat/chapter_01`, `feat/chapter_02`, etc.
- One PR per chapter to BPB's repository

### Chapter Update Process
1. Read the chapter content (from `/chapters/` folder)
2. Review existing figure files in the chapter folder
3. Map each figure in the book to its corresponding repo file
4. Enhance each figure file according to the standards above
5. Test scripts where possible (Windows environment required for some)
6. Commit with conventional commits: `docs(ch01): enhance Figure 1.11 with detailed PSProvider examples`

## Chapter Status

| Chapter | Status | Branch | Notes |
|---------|--------|--------|-------|
| 01 - Introduction to Advanced PowerShell Concepts | In Progress | `feat/chapter_01` | 13 figures (1.11-1.23) |
| 02 - Advanced PowerShell Functions | Pending | - | |
| 03 - TBD | Pending | - | |
| 04 - TBD | Pending | - | |
| 05 - TBD | Pending | - | |
| 06 - TBD | Pending | - | |
| 07 - TBD | Pending | - | |
| 08 - TBD | Pending | - | |
| 09 - TBD | Pending | - | |
| 10 - TBD | Pending | - | |
| 11 - TBD | Pending | - | |
| 12 - TBD | Pending | - | |
| 13 - TBD | Pending | - | |
| 14 - TBD | Pending | - | |
| 15 - TBD | Pending | - | |

## Figure Enhancement Checklist

For each figure script:
- [ ] Minimal header with figure number, description, chapter reference
- [ ] Educational inline comments explaining concepts
- [ ] Full cmdlet names (no aliases)
- [ ] Named parameters for clarity
- [ ] Expected output in comments (where applicable)
- [ ] Cleanup section (for scripts modifying system state)
- [ ] Tested or marked as Windows-only if platform-specific

## Dependencies

- **PowerShell 7+** (primary, cross-platform)
- **PowerShell 5.1** (Windows PowerShell, for Windows-specific features)
- Some figures require Windows (Registry, Certificate providers)

## Author

**Morten Elmstrøm Hansen**
- Book: PowerShell Advanced Cookbook (BPB Publications, 2024)
- ISBN: 978-93-55516-73-2
