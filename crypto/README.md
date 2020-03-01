# [Hash](https://github.com/PinkDraconian/InfoSecCheatSheets/blob/master/crypto/hash.md)
# [Encode](https://github.com/PinkDraconian/InfoSecCheatSheets/blob/master/crypto/encode.md)
# [RSA](https://github.com/PinkDraconian/InfoSecCheatSheets/tree/master/crypto/rsa)
# [Prime Numbers](https://github.com/PinkDraconian/InfoSecCheatSheets/blob/master/crypto/prime%20numbers.md)
# XOR
## Attack vectors
### Repeating XOR key
Bruteforce keys: `https://github.com/laconicwolf/crypto-tools`

Manually finding keys:

  Find the most likely keylength (xortool) and for each iteration of that key (n * keylength), check what xor would result in that becoming a valid char. Do that for every one and then you could get a proper key.
