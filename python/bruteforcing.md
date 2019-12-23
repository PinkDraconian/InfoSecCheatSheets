# Useful libraries
- **[pwntools](http://docs.pwntools.com/en/stable/)** -- Useful for making connections and receiving and sending data
  - Connection
    - `conn = remote('ip', port)`
  - Receiving:
    - `conn.recvuntil('text')`
    - `conn.recvline()`
  - Sending
    - `conn.sendline('text')`
  - Dealing with EOF
```python
try:
  conn.recvline()
except EOFError:
  pass
```
  
