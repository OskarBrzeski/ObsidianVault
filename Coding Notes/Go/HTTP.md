Start a simple HTTP server
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

Use a mux
```go
import (
	"fmt"
	"net/http"
)

func main() {
	mux := http.NewServeMux()
	
	mux.HandleFunc("/", HandleMainPage)
	
	mux.Handle(
		"/static/",
		http.StripPrefix(
			"/static/",
			http.FileServer(http.Dir("static"))
		)
	)
	
	http.ListenAndServe(":3000", mux)
}

func HandleMainPage(w http.ResponseWriter, r *http.Request) {
	fprintf(w, "Hello World")
}
```