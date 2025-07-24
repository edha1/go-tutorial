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
```