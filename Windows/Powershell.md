# PowerShell & Active Directory Commands

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
