# Analysing memory dumps
## Volatility
**Getting processes**:

`volatility -f dump-file.elf --profile Win7SP1x64 --output-file ps.dot --output dot psscan`

**Getting file list**:

`volatility -f dump-file.elf --profile Win7SP1x64 --output-file files filescan`

**Dumping a file**:

`volatility -f dump-file.elf --profile Win7SP1x64 dumpfiles -Q 0x000000001e1f6200 --dump-dir resumedump`
