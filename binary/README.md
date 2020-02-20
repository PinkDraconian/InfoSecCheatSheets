# General
## Checking security on binary
Checksec: `checksec binary`

## Packed binaries
Binaries can be packed to reduce file size. These need to be unpacked for proper analysation
- Check packing: [PEiD](https://www.softpedia.com/get/Programming/Packers-Crypters-Protectors/PEiD-updated.shtml)
- Unpack UPX: `upx -d file.exe -o file_unpacked.exe`

When unpacked binaries don't behave properly, [this](https://www.sans.org/blog/dealing-with-aslr-when-analyzing-malware-on-windows-8-1/) might help

# Pwntools
## General command
`python -c "import pwn; print(STUFF)"`
## Addresses
`pwn.p32(0xdeadbeef)` becomes 0xefbeadde

`pwn.p32(0xdeadbeef, endian='big')` becomes 0xdeadbeef

# [Race Condition](https://github.com/PinkDraconian/InfoSecCheatSheets/blob/master/binary/race%20condition.md)
# [Radare2](https://github.com/PinkDraconian/InfoSecCheatSheets/blob/master/binary/radare2.md)
