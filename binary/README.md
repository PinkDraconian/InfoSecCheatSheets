# General
## Two's complement
Whenever negative numbers need to be converted to an address, it's probably in the [two's complement](https://en.wikipedia.org/wiki/Two's_complement). We can turn it back by doing `n + pow(2, [32|64])` or `(1<<[32|64]) + n`
## Checking security on binary
Checksec: `checksec binary`

## Security meaning
**NX**: Memory is either executable or writeable but not both

## Packed binaries
Binaries can be packed to reduce file size. These need to be unpacked for proper analysation
- Check packing: [PEiD](https://www.softpedia.com/get/Programming/Packers-Crypters-Protectors/PEiD-updated.shtml)
- Unpack UPX: `upx -d file.exe -o file_unpacked.exe`

When unpacked binaries don't behave properly, [this](https://www.sans.org/blog/dealing-with-aslr-when-analyzing-malware-on-windows-8-1/) might help

## 64 vs 32 bit
- Arguments to function calls
  - 64: Go in registers
  - 32: Go on stack

## Check the libraries a binary uses
`ldd file`

## Exploit not working on Ubuntu 18.04 remote?
Try to add or remove 8 bytes to fix the stack offset (https://youtu.be/E8Ykh-UC2f0?t=1156)


# Pwntools
## General command
`python -c "import pwn; print(STUFF)"`
## Addresses
`pwn.p32(0xdeadbeef)` becomes 0xefbeadde

`pwn.p32(0xdeadbeef, endian='big')` becomes 0xdeadbeef

## Cyclic
`cyclic(n)` generates a cyclic string of length n

`cyclic_find(b'bbbb')` finds the offset of the bytes

## Debug mode
`context.log_level = 'DEBUG'`

# GDB Peda
- Function address: `info functions <NAME>`
- Patterns: `pattern create <SIZE>` and `pattern search`

# Printf
## Format vulnerability
Whenever the user can input the first argument (`printf(user_input)`), we can leak memory using `%x` as input

See: [A simple Format String exploit example](https://www.youtube.com/watch?v=0WvrSfcdq1I) by LiveOverflow

# [ROP](https://github.com/PinkDraconian/InfoSecCheatSheets/blob/master/binary/ROP.md)
# [Race Condition](https://github.com/PinkDraconian/InfoSecCheatSheets/blob/master/binary/race%20condition.md)
# [Radare2](https://github.com/PinkDraconian/InfoSecCheatSheets/blob/master/binary/radare2.md)
