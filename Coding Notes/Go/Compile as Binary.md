## Compile as dynamically linked binary
```bash
go build -o binary-file path/to/main.go
```
Relies on having `glibc` on your system.
## Compile as statically linked binary
```bash
CGO_ENABLED=0 GOOS=linux GOARCH=amd64 go build -o binary-file path/to/main.go
```