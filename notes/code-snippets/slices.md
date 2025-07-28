 ```go 
s := make([]int, 3, 3) // len=3, cap=3, capacity is not necessary to sepcify. 
```  

## Append function: 

```go 
    slice = append(slice, elem1, elem2, ...) // slice is the original slice, and the elems are what will be added to the original slice. 
```

```go 
a := []int{1, 2}
b := []int{3, 4}
a = append(a, b...)
fmt.Println(a) // Output: [1 2 3 4]
```

# Range over a String: 

```go 
s := "hello"
for i, ch := range s {
    fmt.Printf("Index %d, Rune %c\n", i, ch)
}
```

# Range over a map: 

```go 
m := map[string]int{"a": 1, "b": 2}
for key, value := range m {
    fmt.Printf("Key: %s, Value: %d\n", key, value)
}
```

If we don't want to use the index or element, we 
can replace it with _ in the loop: 

```go 
for _, v := range nums {
    fmt.Println("Value:", v)
}
```