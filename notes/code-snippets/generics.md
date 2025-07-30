```go 

package main

import "fmt"

// Generic function that returns the first element of a slice of any type
func FirstElement[T any](slice []T) T {
    return slice[0]
}

func main() {
    nums := []int{10, 20, 30}
    words := []string{"apple", "banana", "cherry"}

    fmt.Println(FirstElement(nums))   // Output: 10
    fmt.Println(FirstElement(words))  // Output: apple
}

```
In the above code, the function **FirstElement** is a generic functiona dn the type parameter is **T**. 
- **T any** means that T can be of any type. 
- We could also have for example, **T comparable** which would indicate that the type must be a comparable. 
- The slice that is passed as an argument must be that type and same as the output value. 

*Note:* \\
*comparable makes it possible to use == and != operators on values of the type*. 

## Generic singly linked list: 

```go
package main

import "fmt"

// Node represents a node in a singly-linked list holding a value of type T
type Node[T any] struct {
    Value T
    Next  *Node[T]
}

// Linked list holds Nodes
type LinkedList[T any] struct {
    Head *Node[T]
}

// Insert a new element to front of the list 
func (list *LinkedList[T]) Add(value T) {
    newNode := &Node[T]{Value: value, Next: list.Head}
    list.Head = newNode
}

// Output all elements in the list 
func (list *LinkedList[T]) Print() {
    current := list.Head
    for current != nil {
        fmt.Printf("%v -> ", current.Value)
        current = current.Next
    }
    fmt.Println("nil")
}
```