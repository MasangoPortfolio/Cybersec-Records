Verb-Noun
Get-Help Get-noun or Set-noun command
Get-Command
Get-Command -CommandType "Function"



Set-ADAccountPassword <username> -Reset -NewPassword (Read-Host -AsSecureString -Prompt 'New Password') -Verbose
Set-ADUser -ChangePasswordAtLogon $true -Identity <username> -Verbose

gpupdate /force   //Force Update Group Policy once change has been made
