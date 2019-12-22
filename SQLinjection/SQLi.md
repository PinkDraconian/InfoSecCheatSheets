# SQLMAP
## Testing SQLi
- GET Request: `sqlmap -u "http://ip/?param1=param1&param2=param2"`
- POST Request: `sqlmap -r path/to/burp-request -p param1,param2`

## Exploiting SQLi
- Show schemas: `--dbs`
- Show tables: `-D schema_name --tables`
- Show columns: `-D schema_name -T table_name --columns`
- Dumping: `--dump`

# No HTTP SQLMap
https://haqpl.github.io/Introducing-sqlmap-into-non-HTTP-services
