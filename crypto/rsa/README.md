# In python
```python
from pwn import *


def egcd(a, b):  # https://stackoverflow.com/questions/4798654/modular-multiplicative-inverse-function-in-python
    if a == 0:
        return (b, 0, 1)
    else:
        g, y, x = egcd(b % a, a)
        return (g, x - (b // a) * y, y)

def modinv(a, m):
    g, x, y = egcd(a, m)
    if g != 1:
        raise Exception('modular inverse does not exist')
    else:
        return x % m


ciphertext = ...
n = ...
e = 65537  # COULD BE SOMETHING ELSE
phi = ...


d = modinv(e, phi)
m = pow(ciphertext, d, n)
plain = unhex(hex(m)[2:])
```

# RSA Keys
## Public key
### Consists of 2 values:
  - The modulus n (a product of two secretly chosen large primes p and q)
  - the public exponent e (which can be the same for many keys and is typically chosen to be a small odd prime, most commonly either 3 or 216+1 = 65537).
### Getting components from public key:
`openssl rsa -pubin -inform PEM -text -noout < pubkey.pem`
## Private key
Consists of 2 values:
  - The modulus n (same as in the public key), and
  - The private exponent d (calculated from the public exponent e and the factors p and q of the modulus).

# Unique features
## Multiprime RSA
When the modulus (n) defactors into more than 2 primes, we can still calculate phi / Eulers totient using: https://www.alpertron.com.ar/ECM.HTM

