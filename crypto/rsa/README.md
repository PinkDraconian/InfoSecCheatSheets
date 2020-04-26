# In python
```python
#!/usr/bin/env python3

from Crypto.Util.number import inverse, long_to_bytes


def main():
	n = 
	e = 65537
	ct = 

	# Defactorize n
	p =
    q =

	# Calculate d
	phi = (p - 1) * (q - 1)
	d = inverse(e, phi)

	# Decrypt ciphertext
	pt = pow(ct, d, n)
	decrypted = long_to_bytes(pt)
	print(decrypted)


if __name__ == '__main__':
	main()
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

## Oracle
### [Chosen Ciphertext Attack](https://crypto.stackexchange.com/questions/2323/how-does-a-chosen-plaintext-attack-on-rsa-work)
When an oracle decrypts messages for us, we can do the following to decrypt any given message:
```python
n =
e =
ct = 
ct_a = pow(2, e, n)
ct_b = ct * ct_a
print(ct_b)
result = int(input('Result by server: '))
print(long_to_bytes(result // 2).decode())
```


# Unique features
## Multiprime RSA
When the modulus (n) defactors into more than 2 primes, we can still calculate phi / Eulers totient using: https://www.alpertron.com.ar/ECM.HTM

