# Find remote libc version
When you have a leaked address, the lowest 12 bits can give away which libs is being used

Leaked: `\x90\x76\x27\x30\x79\x7f\x00\x00`

Lowest 12 bits: `690`

Find libc: `/opt/libc-database/find puts 690`

Or use webinterface: https://libc.blukat.me/

# Find addresses
- In binary: `objdump -D ropme | grep puts`
- From libc: `readelf -s libc.so.6 | grep puts`

# Find strings
- In libc: `strings -a -t x libc.so.6 | grep /bin/sh`
 
# Get gadgets
- In r2: `/R pop rdi`
