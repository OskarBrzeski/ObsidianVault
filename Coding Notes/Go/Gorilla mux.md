Include package in file
```go
import (
	"github.com/gorilla/mux"
)
```

Create endpoint router
```go
router := mux.NewRouter()
```

Create endpoint
```go
router.HandleFunc("/endpoint", handlerFunc).Methods("GET")
router.HandleFunc("/endpoint", handlerFunc).Methods("PUT", "PATCH")
router.HandleFunc("/endpoint/{id}", handlerFunc)
```

Pass router to http server
```go
http.ListenAndServe(":3000", router)
```

Get variables from endpoint
```go
func handlerFunc(w http.ResponseWriter, r *http.Request) {
	vars := mux.Vars(r)
	id := vars["id"]
}
```