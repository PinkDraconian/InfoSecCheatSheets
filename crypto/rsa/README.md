# RSA Keys
## Public key
Consists of 2 values:
  - The modulus n (a product of two secretly chosen large primes p and q)
  - the public exponent e (which can be the same for many keys and is typically chosen to be a small odd prime, most commonly either 3 or 216+1 = 65537).
## Private key
Consists of 2 values:
  - The modulus n (same as in the public key), and
  - The private exponent d (calculated from the public exponent e and the factors p and q of the modulus).
