Serve HTML file 
```go
import (
    "html/template"
    "net/http"
)

func main() {
    http.HandleFunc("/", func(w http.ResponseWriter, r *http.Request) {
        tmpl := template.Must(template.ParseFiles("file.html"))
        tmpl.Execute(w, nil)
    })
}
```

Serve HTML from template
```html
{{define "tmplname"}}
<h1>Hello World</h1>
{{end}}
```

```go
import (
    "html/template"
    "net/http"
)

func main() {
    http.HandleFunc("/", func(w http.ResponseWriter, r *http.Request) {
        tmpl := template.Must(template.ParseFiles("file.html"))
        tmpl.ExecuteTemplate(w, "tmplname", nil)
    })
}
```

Serve HTML from multiple template
```html
{{define "index"}}
<body>
    {{template "header"}}
    {{template "main"}}
</body>
{end}
{{define "header"}}
<header></header>
{{end}}
{{define "main"}}
<main></main>
{{end}}
```

```go
import (
    "html/template"
    "net/http"
)

func main() {
    http.HandleFunc("/", func(w http.ResponseWriter, r *http.Request) {
        tmpl := template.Must(template.ParseGlob("*.html"))
        tmpl.ExecuteTemplate(w, "index", nil)
    })
}
```

Pass data to templates
```html
{{define "index"}}
<body>
    <h1>Insert text into this {{.Data}}</h1>
    {{template "main" .}}
</body>
{{end}}
{{define "main"}}
<main>
    {{.Main}}
</main>
{{end}}
```

```go
import (
    "html/template"
    "net/http"
)

type Index struct {
    Data string
    Main string
}

func main() {
    http.HandleFunc("/", func(w http.ResponseWriter, r *http.Request) {
        tmpl := template.Must(template.ParseGlob("*.html"))
        indexData := Index{Data: "Example"}
        tmpl.ExecuteTemplate(w, "index", indexData)
    })
}
```

Use map in template
```html
{{define "index"}}
<ul>
    {{range $key, $value := .Data}}
    <li>{{$key}} : {{$value}}</li>
    {{end}}
</ul>
{{end}}
```

```go
import (
    "html/template"
    "net/http"
)

type Index struct {
    Data map[string]string
}

func main() {
    http.HandleFunc("/", func(w http.ResponseWriter, r *http.Request) {
        tmpl := template.Must(template.ParseGlob("*.html"))
        indexData := Index {
            Data: map[string]string {
                "one": "first",
                "two": "second",
            },
        }
        tmpl.ExecuteTemplate(w, "index", indexData)
    })
}
```

Use slice in template
```html
{{define "index"}}
<ul>
    {{range .Data}}
    <li>{{.}}</li>
    {{end}}
</ul>
{{end}}
```

```go
import (
    "html/template"
    "net/http"
)

type Index struct {
    Data []string
}

func main() {
    http.HandleFunc("/", func(w http.ResponseWriter, r *http.Request) {
        tmpl := template.Must(template.ParseGlob("*.html"))
        indexData := Index {
            Data: []string {
                "one",
                "two",
            },
        }
        tmpl.ExecuteTemplate(w, "index", indexData)
    })
}
```

Use function in template
```html
{{define "index"}}}
<p>{{toUpper .Data}}</p>
{{end}}
```
```go
import (
    "html/template"
    "net/http"
    "strings"
)

type Index struct {
    Data string
}

func main() {
    http.HandleFunc("/", func(w http.ResponseWriter, r *http.Request) {
        funcMap := template.FuncMap {
            "toUpper": strings.ToUpper,
        }
        tmpl := template.Must(template.New("Example").Funcs(funcMap).ParseGlob("*.html"))
        indexData := Index {
            Data: "To be capitalised."
        }
        tmpl.ExecuteTemplate(w, "index", indexData)
    })
}
```
