# [Enumeration](https://github.com/PinkDraconian/InfoSecCheatSheets/blob/master/windows/enumeration.md)
# [Local File Inclusion](https://github.com/PinkDraconian/InfoSecCheatSheets/blob/master/windows/local%20file%20inclusion.md)
# [Exploitation](https://github.com/PinkDraconian/InfoSecCheatSheets/blob/master/windows/exploitation.md)
# SMB
## Setting up and using SMBshare with credentials
Local: 
```bash
impacket-smbserver -username Pink -password Draconian pink $(pwd)`
```
Remote: 
```powershell
$pass = "Draconian" | ConvertTo-SecureString -AsPlainText -Force
$cred = New-Object System.Management.Automation.PsCredential('Pink', $pass)
New-PS-Drive -Name pink -Root \\ip\pink -Credential $cred -PsProvider "filesystem"
cd pink:
```

## Get remote SMB share in Windows
`NET USE H: \\ip\share /USER:username password`
