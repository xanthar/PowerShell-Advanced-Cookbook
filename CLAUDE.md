# PowerShell Advanced Cookbook - Repository Enhancement Project

## Project Overview

This repository accompanies the book **"PowerShell Advanced Cookbook"** by Morten Elmstrøm Hansen, published by BPB Publications.

- **Original Repository**: https://github.com/bpbpublications/PowerShell-Advanced-Cookbook
- **Author's Fork**: https://github.com/xanthar/PowerShell-Advanced-Cookbook
- **Purpose**: Enhance the book's companion code repository with detailed, educational, and professional examples

## Project Goals

1. **Professionalize all scripts**: Transform minimal examples into comprehensive, educational scripts
2. **Add educational value**: Include detailed inline comments explaining *why* commands work
3. **Show expected output**: Include comment blocks demonstrating expected output
4. **Provide cleanup code**: For scripts that modify system state, include cleanup sections
5. **Maintain book alignment**: Each figure file corresponds to a specific figure in the book

---

## Script Standards

### Standard Header Format (ALL files must use this)

**For Figure files:**
```powershell
# Figure X.XX - [Brief Description]
# Chapter X: [Chapter Title]
# PowerShell Advanced Cookbook - BPB Publications
```

**For Recipe/Topic files (2.x_*.ps1):**
```powershell
# Recipe: [Recipe Name]
# Chapter X: [Chapter Title]
# PowerShell Advanced Cookbook - BPB Publications
#
# [Brief description of what this recipe demonstrates]
```

**For Snippet files (code fragments):**
```powershell
# [Topic] - Code Snippet
# Chapter X: [Chapter Title]
# PowerShell Advanced Cookbook - BPB Publications
#
# [Brief description of what this snippet shows]
```

### Comment Style Requirements

1. **Section Headers**: Use clear section dividers for logical groupings
   ```powershell
   # ============================================================================
   # SECTION NAME
   # ============================================================================
   ```

2. **Inline Comments**: Explain the *why*, not just the *what*
   ```powershell
   # Using ValidateSet ensures only valid abilities can be assigned
   [ValidateSet("Flying", "Invulnerability")]
   ```

3. **Expected Output**: Show what the user should expect
   ```powershell
   # Expected Output:
   # Name        Abilities       Powers
   # ----        ---------       ------
   # Comet       Flying          43
   ```

4. **Platform Notes**: Mark Windows-only features
   ```powershell
   # Platform: Windows only
   ```

### Code Conventions

- Use **full cmdlet names** (not aliases): `Get-ChildItem` not `gci`
- Use **named parameters** for clarity: `-Path "C:\Temp"` not positional
- Use **proper PowerShell verbs**: Add, Get, Set, Remove, New, etc.
- Include **practical examples** where educational value exists
- Add **cleanup sections** for scripts that modify system state

---

## Chapter Enhancement Checklist

For each script file:
- [ ] Standard header with figure/recipe reference
- [ ] Chapter title in header
- [ ] Educational inline comments
- [ ] Full cmdlet names (no aliases)
- [ ] Named parameters for clarity
- [ ] Expected output in comments (where applicable)
- [ ] Section dividers for logical groupings
- [ ] Cleanup section (for scripts modifying system state)
- [ ] Platform notes if Windows-only

---

## Workflow

### Branching Strategy
- **Never commit directly to main**
- Create feature branches per chapter: `feat/chapter_01`, `feat/chapter_02`, etc.
- Push branches to fork, then PR to BPB's repository

### Commit Message Format
```
docs(chXX): [brief description]

[Detailed description of changes]

Co-Authored-By: Claude Opus 4.5 <noreply@anthropic.com>
```

---

## Chapter Status

| Chapter | Branch | Status | Files |
|---------|--------|--------|-------|
| 01 - Introduction to Advanced PowerShell | `feat/chapter_01` | Complete | 13 figures |
| 02 - Advanced PowerShell Functions | `feat/chapter_02` | Complete | 41 files |
| 03 - Working with Objects | `feat/chapter_03` | Complete | 24 figures, 3 recipes |
| 04 - Error Handling | `feat/chapter_04` | Complete | 20 figures, 4 recipes |
| 05 - Working with Scripts | `feat/chapter_05` | Complete | 35 figures, 4 recipes, 3 module files |
| 06 - PowerShell Remoting | `feat/chapter_06` | Complete | 22 figures, 4 recipes |
| 07 - TBD | - | Pending | - |
| 08 - TBD | - | Pending | - |
| 09 - TBD | - | Pending | - |
| 10 - TBD | - | Pending | - |
| 11 - TBD | - | Pending | - |
| 12 - TBD | - | Pending | - |
| 13 - TBD | - | Pending | - |
| 14 - TBD | - | Pending | - |
| 15 - TBD | - | Pending | - |

---

## Chapter 2 File Categories

### Figure Files (Figures from the book)
- Figure 2.1 - 2.33 (with some gaps for screenshots)

### Recipe Files (Complete working examples)
- 2.1_CreateAnAdvancedFunction.ps1
- 2.3_AddingDynamicParametersToFunction.ps1
- 2.4_AddingParameterSets_Alignment.ps1
- 2.5_LifeCycleEvents.ps1
- 2.6_PipelineHandling.ps1
- 2.7_ShouldProcess.ps1
- 2.8_CreateClasses.ps1

### Snippet Files (Code fragments for explanation)
- 2.3_DynamicParameterBlock.ps1
- 2.4_ParameterSetLogic.ps1
- 2.6_PipelineExamples.ps1
- cmdletbinding.ps1

### Data Files (No enhancement needed)
- HeroMap.csv
- Figure_2.21_HeroMap.csv
- Superheroes.txt

---

## Author

**Morten Elmstrøm Hansen**
- Book: PowerShell Advanced Cookbook (BPB Publications)
