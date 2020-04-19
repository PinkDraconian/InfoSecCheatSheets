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

# Attack vectors
## Multiple public keys
### Common divisor
In a strong key situation, we have `n1 = a * b` and `n2 = c * d`.
In the case where all of these primes are unique, `gcd(n1, n2) = 1`.
If this is not the case, then one of the primes from both keys are equal! So `n1 = a * b` and `n2 = b * c`.
Now this gcd is b and using that we can calculate a and c and use those (p, q)
In python it looks like this:
```python
n1 = ...
n2 = ...
greatest_common_divisor = math.gcd(n1, n2)
q = greatest_common_divisor
p = n2 // greatest_common_divisor
phi = (p - 1) * (q - 1)
```
## Small exponent
### No mod because of small cipher
When the ciphertext and exponent are small, and n is very big, `pow(c, e)` might be equal to `pow(c, e, n)`, meaning that you can bruteforce character per character.

# Unique features
## Multiprime RSA
When the modulus (n) defactors into more than 2 primes, we can still calculate phi / Eulers totient using: https://www.alpertron.com.ar/ECM.HTM

