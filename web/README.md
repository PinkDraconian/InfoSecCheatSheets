# JavaScript
## JSFuck
Looks like: `[][(![]+[])[+[]]+([![]]+[][[]])[+!+[]+[+[]]]+(![]+[])[!+[]+!+[]]+(!!`

Can be deconfuscated: https://enkhee-osiris.github.io/Decoder-JSFuck/

# JWT tokens
## Attack vectors
### Asymetric RS -> HS ([example](https://www.nccgroup.trust/uk/about-us/newsroom-and-events/blogs/2019/january/jwt-attack-walk-through/))
The public key is used for verification and the algorithm can be switched from RS to HS

# Flask
## Crafting sessions tokens
When the SECRET_KEY is given (or bruteforced), these tokens can be maliciously crafted.

The tool [flask-unsign](https://github.com/Paradoxis/Flask-Unsign) provides us many useful functions.
- Crafting: `flask-unsign --legacy --sign --cookie '{"key":val}' --secret 'SECRET_KEY'`
- Decoding: `flask-unsign --decode --cookie 'cookie_val'`
- Bruteforcing: `flask-unsign --unsign --wordlist /path/to/wordlist --cookie 'cookie_val'`
