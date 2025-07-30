```go 
package main

import (
	"fmt"
	"math"
)

// Define the interface
type Shape interface {
	Area() float64
	Perimeter() float64
}

// Rectangle type
type Rectangle struct {
	Width  float64
	Height float64
}

// Circle type
type Circle struct {
	Radius float64
}

// Implement Shape interface for Rectangle
func (r Rectangle) Area() float64 {
	return r.Width * r.Height
}

func (r Rectangle) Perimeter() float64 {
	return 2 * (r.Width + r.Height)
}

// Implement Shape interface for Circle
func (c Circle) Area() float64 {
	return math.Pi * c.Radius * c.Radius
}

func (c Circle) Perimeter() float64 {
	return 2 * math.Pi * c.Radius
}

// Function that works with any Shape
func printShapeDetails(s Shape) {
	fmt.Printf("Area: %.2f\n", s.Area())
	fmt.Printf("Perimeter: %.2f\n", s.Perimeter())
}

func main() {
	r := Rectangle{Width: 10, Height: 5}
	c := Circle{Radius: 7}

	fmt.Println("Rectangle:")
	printShapeDetails(r)

	fmt.Println("\nCircle:")
	printShapeDetails(c)
}

// Understanding interface values: 

package main

import (
    "fmt"
    "math"
)

// Define an interface
type Shape interface {
    Area() float64
}

// Concrete type: Circle
type Circle struct {
    Radius float64
}

// Implement the Area() method for Circle
func (c Circle) Area() float64 {
    return math.Pi * c.Radius * c.Radius
}

func main() {
    var s Shape          
    c := Circle{5}      
    s = c                // Assigning Circle to interface variable. 

    fmt.Println(s.Area()) 
}

```
When s = c, this is stored inside s: (value: Circle{Radius: 5}, type: Circle)

## Type Assertions 
```go
t := i.(T)
```
This says that: **i** is an interface value, and we are asserting that i holds a value of **concrete type T**. If this is not the case, it will cause a panic, therefore the safe version is: 
```go
t, ok := i.(T)
```
If i does hold T, then **ok is true** and t gets the value. Otherwise, **ok is false** and t gets the zero value of the type. 

## Type Switches 

```go 
func describe(i interface{}) {
    switch v := i.(type) { // Notice that we use the type keyword
    case int:
        fmt.Printf("Type is int, value = %d\n", v)
    case string:
        fmt.Printf("Type is string, value = %q\n", v)
    case bool:
        fmt.Printf("Type is bool, value = %v\n", v)
    default:
        fmt.Printf("Unknown type %T\n", v)
    }
}
```
In the above code snippet, i is an empty interface and the switch will: 
- Extract the **concrete type** of the value inside i. 
- Bind it to *8v**. 
- Choose the appropriate case block. 