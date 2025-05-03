Start a simple http server
```go
import (
    "fmt"
    "net/http"
)

func main() {
    http.HandleFunc("/", func(w http.ResponseWriter, r *http.Request) {
        fmt.Fprintf(w, "Hello World!")
    })

    http.ListenAndServe(":3000", nil)
}
```

Serve static files
```go
http.Handle("/static/", http.StripPrefix(
	"/static/",
	http.FileServer(http.Dir("static"))
))
```

Respond with an error
```go
import (
    "fmt"
    "net/http"
)

func main() {
    http.HandleFunc("/", func(w http.ResponseWriter, r *http.Request) {
        http.Error(w, "Error Occured", http.StatusInternalServerError)
    })

    http.ListenAndServe(":3000", nil)
}
```
