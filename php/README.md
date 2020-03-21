# [Deserialization](https://github.com/PinkDraconian/InfoSecCheatSheets/blob/master/php/deserialization.md)

# Characters not allowed
- `_`:  Dots and spaces in variable names are converted to underscores. For example `<input name="a.b" />` becomes `$_REQUEST["a_b"]`. 
- `array["key"]`: Can use `array{key}`

# Dangerous function calls
- exec
- shell_exec
- system
- passthru
- eval
- popen
- unserialize
- include
- file_put_contents
- $_COOKIE | if

# Exploiting function
## [ereg ( string $pattern , string $string \[, array &$regs \]) : int](https://www.php.net/manual/en/function.ereg.php)
```php
$input = urldecode("a%00$");
if (ereg("^[a-zA-Z0-9]+$", $input) === FALSE) {
    echo 'Only Alphanumeric accepted';
} else {
    echo "Got past the check!";
}
```
When our input is being urldecoded, (`$_GET['key']` performs an `urldecode()`), using the null byte (`%00`) we can pass the check!
