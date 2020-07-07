# [Enumeration](https://github.com/PinkDraconian/InfoSecCheatSheets/blob/master/windows/enumeration.md)
# [Local File Inclusion](https://github.com/PinkDraconian/InfoSecCheatSheets/blob/master/windows/local%20file%20inclusion.md)
# [Exploitation](https://github.com/PinkDraconian/InfoSecCheatSheets/blob/master/windows/exploitation.md)
# SMB
## Mount share on Linux
`mount -t cifs -o username=guest '//10.10.10.192/profiles$' /mnt/profiles`
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

## Get password-policy
`crackmapexec smb --pass-pol 10.10.10.169`

## Check permissions
`smbcacls -N '//172.31.3.6/SHARE' 'Directory'`
