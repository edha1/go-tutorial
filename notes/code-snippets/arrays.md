```go 
// One way of defining an array: 
package main

import "fmt"

func main() {
    // Define an array of 5 integers
    var numbers [5]int

    // Assign values to the array
    numbers[0] = 10
    numbers[1] = 20
    numbers[2] = 30
    numbers[3] = 40
    numbers[4] = 50

    // Print the array
    fmt.Println("Array:", numbers)
}


// We could also do: 
numbers := [5]int{10, 20, 30, 40, 50}
```