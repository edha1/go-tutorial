```go

package main

import "fmt"

// If statement 
func main() {
    x := 10

    if x > 5 {
        fmt.Println("x is greater than 5")
    }
}

// If-else statement 
func else() {
    x := 3

    if x > 5 {
        fmt.Println("x is greater than 5")
    } else {
        fmt.Println("x is 5 or less")
    }
}

func declaring() {

    // Note: x is declared within the statement. 
    // Scope of x is limited to these code blocks. 
    if x := 10; x > 5 {
        fmt.Println("x is greater than 5")
    } else {
        fmt.Println("x is 5 or less")
    }
}
```