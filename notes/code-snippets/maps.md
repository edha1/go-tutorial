```go 
// map with string keys and int elements 
ages := map[string]int{
    "Alice": 30,
    "Bob":   25,
}
fmt.Println(ages["Alice"]) // Output: 30

// map with String key and Person elem 
type Person struct {
    Name string
    Age  int
}

people := map[string]Person{
    "john": {Name: "John Doe", Age: 28},
    "jane": {Name: "Jane Smith", Age: 32},
}

fmt.Println(people["jane"].Name) // Output: Jane Smith


```