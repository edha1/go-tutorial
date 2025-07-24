```go 

// This code snippet is from short-variable-declarations in 'A Tour of Go' (linked in README)

package main

import "fmt"

func main() {
	var i, j int = 1, 2
	k := 3
	c, python, java := true, false, "no!"

	fmt.Println(i, j, k, c, python, java)
}


```