```bash
find [dirname] [flags]
```
## Flags
### Time period
`+` and `-` are used to mean greater than and less than respectfully.
`-amin n` - File was accessed n minutes ago.
`-cmin n` - File status was changed n minutes ago.
`-mmin n` - File was modified n minutes ago.
### File name
`-name "pattern"` - File name matches pattern.
`-regex "pattern"` - File name matches regular expression.
