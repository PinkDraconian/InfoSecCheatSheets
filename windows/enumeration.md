# Enumeration scripts
- [WinPEAS](https://github.com/carlospolop/privilege-escalation-awesome-scripts-suite/tree/master/winPEAS)

# User info
- net username

# NTFS Multiple data streams
- `Get-Item -Path "Debug Mode Password.txt" -Stream *`: Use to view streams in file
- `Get-Content -Path "Debug Mode Password.txt" -Stream Password`: Use to get data from stream
Note: This will only work on Windows machines since FAT doesn't allow multiple streams. Files downloaded using impacket/smbclient won't keep their alternate stream data either
