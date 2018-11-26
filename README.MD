# mdl

# Hosted files
```html

  <link rel="stylesheet" href="https://fonts.googleapis.com/icon?family=Material+Icons">
  <link rel="stylesheet" href="https://stevenzack.github.io/mdl/mdl.min.css">
  <script defer src="https://stevenzack.github.io/mdl/mdl.min.js"></script>
 ```
# Usage

main.go
```go
package main

import (
	"fmt"
	"github.com/StevenZack/mdl"
	"net/http"
)

func main() {
	http.HandleFunc("/", home)
	http.HandleFunc("/material.min.js", mdl.JsHandler)
	http.HandleFunc("/material.min.css", mdl.CssHandler)
	e := http.ListenAndServe(":8080", nil)
	if e != nil {
		fmt.Println(e)
	}
}
func home(rw http.ResponseWriter, req *http.Request) {
	http.ServeFile(rw, req, "./index.html")
}
```

index.html
```html
<!DOCTYPE html>
<html>
<head>
	<title></title>
	<link rel="stylesheet" href="/material.min.css">
	<script src="/material.min.js"></script>
</head>
<body>
<!-- Accent-colored raised button with ripple -->
<button class="mdl-button mdl-js-button mdl-button--raised mdl-js-ripple-effect mdl-button--accent">
  Button
</button>

</body>
</html>
```

