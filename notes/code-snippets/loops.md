```go

package main

import "fmt"

func main() {
    // Print the numbers 0 through 4
    // The loop runs while the condition i < 5 is true
    for i := 0; i < 5; i++ {
        fmt.Println(i)
    }
}



// This is the equivalent of a while loop in other languages
func whileLoop() {
    i := 0

    // Note: This for loop omits the init and post statements,
    // so it behaves like a while loop
    for i < 5 {
        fmt.Println(i)
        i++
    }
}

// This will run forever 
func infiniteLoop() {
	for {
	}
}
```