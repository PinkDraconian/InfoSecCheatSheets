# Scanning
## Nikto
- [https://github.com/sullo/nikto](Nikto) is a web server scanner

# JavaScript
## Window object
- Gloabal functios and variables declared with `var` become the property of the global object
```js
pink = "draconian";
console.log(window.pink) // draconian
```
## JSFuck
Looks like: `[][(![]+[])[+[]]+([![]]+[][[]])[+!+[]+[+[]]]+(![]+[])[!+[]+!+[]]+(!!`

Can be deconfuscated: https://enkhee-osiris.github.io/Decoder-JSFuck/

# JWT tokens
## Attack vectors
### Asymetric RS -> HS ([example](https://www.nccgroup.trust/uk/about-us/newsroom-and-events/blogs/2019/january/jwt-attack-walk-through/))
The public key is used for verification and the algorithm can be switched from RS to HS
### JWKS Spoofing ([example](https://www.youtube.com/watch?v=KUyuvnez0ks))
Whenever the `jku` header is being used and can make remote requests, this can be a good attack vector

# Flask
## Crafting sessions tokens
When the SECRET_KEY is given (or bruteforced), these tokens can be maliciously crafted.

The tool [flask-unsign](https://github.com/Paradoxis/Flask-Unsign) provides us many useful functions.
- Crafting: `flask-unsign --legacy --sign --cookie '{"key":val}' --secret 'SECRET_KEY'`
- Decoding: `flask-unsign --decode --cookie 'cookie_val'`
- Bruteforcing: `flask-unsign --unsign --wordlist /path/to/wordlist --cookie 'cookie_val'`

# Wordpress
## WPSCAN
`wpscan --url URL`
