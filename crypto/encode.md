# Caesar
## [Keyed caesar](http://rumkin.com/tools/cipher/caesar-keyed.php)
Caesar with a key where the key modifies the used alphabet


# [UU encoding](https://en.wikipedia.org/wiki/Uuencoding)
Example: 
```
begin 644 root-me_challenge_uudeview
B5F5R>2!S:6UP;&4@.RD*4$%34R`](%5,5%)!4TE-4$Q%"@``
`
end
```
Decoding: 
```python
"""begin 644 root-me_challenge_uudeview
B5F5R>2!S:6UP;&4@.RD*4$%34R`](%5,5%)!4TE-4$Q%"@``
`
end
""".decode('uu')
```
