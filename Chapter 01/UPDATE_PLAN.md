# Chapter 01 - Figure Enhancement Plan

## Overview
Chapter 1 covers "Introduction to Advanced PowerShell Concepts" including:
- PowerShell scripting best practices
- IDE setup (VS Code)
- PowerShell versions (5.1, 6/Core, 7)
- PowerShell Providers (FileSystem, Registry, Certificate)

**Figures 1.1-1.10**: VS Code UI screenshots - no code updates needed
**Figures 1.11-1.23**: Code examples in repo - enhancement required

---

## Figure 1.11 - Get-PSProvider cmdlet and output

**Current State**: Single line `Get-PSProvider`

**Enhancement Plan**:
- Add header with figure reference
- Explain what PSProviders are and why they matter
- Show Get-PSProvider output structure
- Demonstrate filtering providers by name
- Explain capabilities (ShouldProcess, Filter, Credentials, etc.)
- Show how to see drives for each provider

**Expected Output**: Include sample output showing Name, Capabilities, Drives columns

---

## Figure 1.12 - Working with the Filesystem Provider

**Current State**: 3 basic commands (Set-Location, Get-ChildItem)

**Enhancement Plan**:
- Explain that filesystem is the default provider
- Demonstrate navigation with Set-Location
- Show Get-ChildItem with various parameters
- Include piping to ForEach-Object as shown in book
- Demonstrate path formats (relative vs absolute)

**Expected Output**: Sample directory listing output

---

## Figure 1.13 - Registry Provider - HKCU:\SOFTWARE

**Current State**: Single line `Get-ChildItem HKCU:\SOFTWARE\`

**Enhancement Plan**:
- Explain registry structure (HKCU vs HKLM)
- Show how to list software keys
- Demonstrate filtering and selecting specific keys
- Include safety warnings about registry modification
- Platform note: Windows-only

**Expected Output**: Sample registry key listing

---

## Figure 1.14 - Registry Provider - Specific Software Key

**Current State**: `Get-ChildItem HKCU:\SOFTWARE\7-Zip\` (assumes 7-Zip installed)

**Enhancement Plan**:
- Generalize to work with any installed software
- Show how to find what software keys exist first
- Demonstrate navigating to a specific key
- Include fallback example if specific key doesn't exist
- Explain subkeys vs properties

**Expected Output**: Sample software key properties

---

## Figure 1.15 - Create Registry Keys and Properties (Get-Item)

**Current State**: Creates TestKey, SubTestKey, sets properties, shows Get-Item

**Enhancement Plan**:
- Improve header documentation
- Add prerequisite check (verify HKCU:\Software accessible)
- Explain difference between keys and properties
- Better structured examples
- Add cleanup section to remove test keys

**Expected Output**: Show created keys and their properties

---

## Figure 1.16 - Get-ItemProperty for Registry Values

**Current State**: Creates keys, demonstrates Get-ItemProperty

**Enhancement Plan**:
- Focus on retrieving property values
- Show different ways to access property values
- Demonstrate the PSProvider and path metadata returned
- Explain dot notation access
- Add cleanup section

**Expected Output**: Property value retrieval examples

---

## Figure 1.17 - Remove Registry Keys and Properties

**Current State**: Creates keys, shows removal of key and property

**Enhancement Plan**:
- Add strong safety warnings
- Demonstrate -WhatIf for safety testing
- Show removing subkeys vs properties
- Verify removal with Get-Item
- Include complete cleanup

**Expected Output**: Before/after removal states

---

## Figure 1.18 - Certificate Store Structure (CurrentUser)

**Current State**: Single line `Get-ChildItem Cert:\CurrentUser`

**Enhancement Plan**:
- Explain certificate store architecture
- List common store locations (My, Root, CA, etc.)
- Explain difference between CurrentUser and LocalMachine
- Show folder meanings (My = Personal, Root = Trusted Root)
- Platform note: Windows-only

**Expected Output**: Certificate store folder listing

---

## Figure 1.19 - Personal Certificate Store Contents

**Current State**: `Get-ChildItem Cert:\CurrentUser\My | Format-Table -AutoSize`

**Enhancement Plan**:
- Explain the Personal (My) certificate store
- Show certificates with readable formatting
- Demonstrate filtering by various properties
- Explain thumbprint, subject, notafter columns
- Handle case where store is empty

**Expected Output**: Certificate listing with formatted output

---

## Figure 1.20 - Different Methods for Selecting a Certificate

**Current State**: Uses placeholders like `<CERTIFICATETHUMBPRINT>`

**Enhancement Plan**:
- Fix placeholders with dynamic examples
- Show index-based selection: `(Get-ChildItem Cert:\CurrentUser\My)[0]`
- Show thumbprint-based selection with actual example
- Show Subject (CN) matching with Where-Object
- Show FriendlyName matching
- Explain when to use each method

**Expected Output**: Certificate selection results

---

## Figure 1.21 - Certificate Properties

**Current State**: 2 lines selecting cert and piping to Select-Object *

**Enhancement Plan**:
- Show all available certificate properties
- Highlight important properties (NotAfter, Subject, Issuer, etc.)
- Demonstrate accessing specific properties
- Explain PSDrive and PSProvider metadata
- Show common property use cases (expiration checking)

**Expected Output**: Full certificate property list

---

## Figure 1.22 - Remove Certificate from Store

**Current State**: 3 lines - select, remove, verify

**Enhancement Plan**:
- Add strong safety warnings
- Demonstrate with test certificate (created in 1.23)
- Show -WhatIf for safety testing
- Verify removal
- Note about requiring elevation for LocalMachine store

**Expected Output**: Before/after removal verification

---

## Figure 1.23 - Create Self-Signed Certificate

**Current State**: 2 lines creating self-signed cert

**Enhancement Plan**:
- Explain self-signed certificate use cases
- Show more certificate creation parameters
- Demonstrate different certificate types (CodeSigning, etc.)
- Include KeyUsage and EnhancedKeyUsage options
- Add note about certificate expiration
- Include cleanup option

**Expected Output**: New certificate creation confirmation

---

## Implementation Order

Recommended order (builds knowledge progressively):
1. Figure 1.11 (PSProvider foundation)
2. Figure 1.12 (FileSystem - familiar ground)
3. Figures 1.13-1.17 (Registry - grouped)
4. Figures 1.18-1.23 (Certificates - grouped)

## Notes

- All registry and certificate examples are Windows-only
- Include platform compatibility notes in scripts
- Test on Windows 10/11 with PowerShell 5.1 and 7
- Cleanup sections should be clearly marked and optional
