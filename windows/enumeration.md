# Enumeration scripts
- [WinPEAS](https://github.com/carlospolop/privilege-escalation-awesome-scripts-suite/tree/master/winPEAS)

# User info
- net username

# NTFS Multiple data streams
## Windows
- `Get-Item -Path "FILE" -Stream *`: Use to view streams in file
- `Get-Content -Path "FILE" -Stream Password`: Use to get data from stream
## Linux
- `smbclient -U <USERNAME> //<IP>/<SHARE> -c 'allinfo "<Path\To\File>"'`: Use to view streams in file
- In SMBClient: `get <FILE>:<STREAM>:$DATA`: Use to get data from stream
