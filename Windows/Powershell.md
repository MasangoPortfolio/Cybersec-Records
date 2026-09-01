# PowerShell & Active Directory Commands

# PowerShell Fundamentals

## Launching PowerShell

PowerShell can be launched from several places:

```text
Start Menu       → Search "PowerShell"
Run              → Win + R → powershell
File Explorer    → Type powershell in the address bar
Task Manager     → File → Run new task → powershell
Command Prompt   → Type powershell
```

When launched, the prompt changes to:

```powershell
PS C:\Users\username>
```

`PS` indicates that you are currently using **PowerShell**.

---

## Cmdlets & Verb-Noun Syntax

PowerShell commands are called **cmdlets** (command-lets).

Cmdlets follow a consistent:

```text
Verb-Noun
```

The **Verb** describes the action, while the **Noun** describes the object being acted upon.

```powershell
Get-Content       # Get the contents of a file
Set-Location      # Change the current directory
Get-Date           # Get the current date/time
```

This naming convention makes commands easier to understand and discover.

---

## Get-Command

Lists commands available in the current PowerShell session, including **cmdlets, functions, aliases, and scripts**.

```powershell
Get-Command
```

Filter commands by type:

```powershell
Get-Command -CommandType "Function"
```

Other command types include:

```text
Cmdlet
Function
Alias
Application
Script
```

---

## Get-Help

Used to learn how a cmdlet works, including its **syntax, parameters, description, and examples**.

```powershell
Get-Help Get-Date
```

Useful options:

```powershell
Get-Help Get-Date -Examples
Get-Help Get-Date -Detailed
Get-Help Get-Date -Full
Get-Help Get-Date -Online
```

**Remember:** `Get-Help` is your built-in PowerShell documentation.

---

## Aliases

PowerShell provides **aliases** as shortcuts for commands, making it easier for users familiar with other command-line environments.

```powershell
Get-Alias
```

Common examples:

```text
cd      → Set-Location
dir     → Get-ChildItem
cat     → Get-Content
clear   → Clear-Host
```

You can also check a specific alias:

```powershell
Get-Alias cd
```

---

## Installing Additional Cmdlets

PowerShell functionality can be extended through **modules** containing additional cmdlets.

### Find a Module

```powershell
Find-Module -Name "PowerShell*"
```

`*` is a **wildcard** used to match multiple names.

### Install a Module

```powershell
Install-Module -Name "PowerShellGet"
```

> These commands require an internet connection when searching or downloading modules from online repositories such as the **PowerShell Gallery**.

---

## Quick Reference

| Command                               | Purpose                 |
| ------------------------------------- | ----------------------- |
| `Get-Command`                         | Find available commands |
| `Get-Help`                            | Get help/documentation  |
| `Get-Alias`                           | View command aliases    |
| `Find-Module`                         | Search for modules      |
| `Install-Module`                      | Install a module        |
| `Get-Command -CommandType "Function"` | List functions          |


### PowerShell Basics

```powershell
# Verb-Noun syntax
Get-Help Get-Noun
Get-Help Set-Noun

# List available commands
Get-Command

Get-Alias

# List commands by type
Get-Command -CommandType "Function"
```

### Active Directory — Password Reset

```powershell
Set-ADAccountPassword <username> -Reset -NewPassword (Read-Host -AsSecureString -Prompt 'New Password') -Verbose

Set-ADUser -ChangePasswordAtLogon $true -Identity <username> -Verbose
```

### Group Policy

```powershell
gpupdate /force
```
