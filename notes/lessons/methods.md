# 🧩 Methods

- There are **no classes** in Go. 
- A **method** is a function with a **special receiver** argument: 

```go
// Define a struct
type Rectangle struct {
	Width  float64
	Height float64
}

// Method to calculate area of a Rectangle
func (r Rectangle) Area() float64 {
	return r.Width * r.Height
}

func main() {
	rect := Rectangle{Width: 10, Height: 5}

    // can call the method with rect.Area()
	fmt.Println("Area:", rect.Area())
}
```
As can be seen above, the receiver argument is the argument that is between the **func** keyword and the **method name**. 
- The receiver argument need not be a struct. 
- **You can only declare a method with a receiver whose type is defined in the same package**
- Even **pointers** can be receivers. These methods can modify the value to which the receiver points to. 
- If the receiver is a value, the method will operate on a copy of that value. 
- We would want to use a pointer as the receiver because it allows us to modify the value that it points to, and it avoids copying the value on each method call. 