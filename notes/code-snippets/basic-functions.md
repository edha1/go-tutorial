```go

// A basic function. Notice that the type is after the variable name. This left to right style is due to its ease of reading, specifically for more complex types. 
func add(x int, y int) int {
	return x + y
} 

// We can also name return variables: 
func switch(x int, y int) (right, left int) {
	right = y
	left = x  
	return 
}

// Assigning a function to a variable 
package main

import "fmt"

func greet(name string) {
    fmt.Println("Hello,", name)
}

func main() {
    f := greet // assign function to variable
    f("Alice") // call it like a regular function
}


// Passing a function as an argument
package main

import "fmt"

func doTwice(f func(int) int, x int) int {
    return f(f(x))
}

func square(n int) int {
    return n * n
}

func main() {
    result := doTwice(square, 2)
    fmt.Println(result) // Output: 16 (square(square(2)) = square(4) = 16)
}

// Returning a function from a function 
package main

import "fmt"

func multiplier(factor int) func(int) int {
    return func(x int) int {
        return x * factor
    }
}

func main() {
    double := multiplier(2)
    triple := multiplier(3)

    fmt.Println(double(5)) // Output: 10
    fmt.Println(triple(5)) // Output: 15
}
```

## Closure example (taken from A Tour of Go, Function Closures:[A Tour of Go](https://go.dev/tour/moretypes/25)) 

```go 
package main

import "fmt"

func adder() func(int) int {
    sum := 0
    return func(x int) int {
        sum += x
        return sum
    }
}

func main() {
    pos := adder()
    neg := adder()

    fmt.Println(pos(1))  // Output: 1
    fmt.Println(pos(2))  // Output: 3
    fmt.Println(pos(3))  // Output: 6

    fmt.Println(neg(-1)) // Output: -1
    fmt.Println(neg(-2)) // Output: -3
}
```

**Explanation:** 

*func adder() func(int) int*
- This function returns another function (a closure).
- It defines a local variable sum := 0.
- The returned function has access to sum and modifies it when called.

*pos := adder()*
- Creates a new closure with its own sum.
- Calling pos(1), pos(2), etc., keeps updating that specific sum.

*neg := adder()*
- Another independent closure with its own separate sum.