# 🧬 Interfaces 


- An **interface type** is a set of method signatures. 
- A **value** of interface type can hold any value that implements those methods. 
- A type implements an interface by implementing its methods. 
- A type does **not need to declare** that it implements an interface. 
- If a type has all the methods that an interface requires, it **automatically implements that interface**. 

*See interfaces.md in code snippets for an example!*

- An **interface value** is a variable of an interface type. 
- When you assign a **concrete value** to an interface variable, it is stored as a **tuple**: (value, *type*), which is the **actual value** and the **concrete type**. 
- An interface value that holds a nil value is itself non-nil: 
```go 
var c *Circle = nil      // a nil *Circle pointer
var s Shape = c          // assign it to the interface
```
Now, s holds: **(type: *Circle, value: nil)**, so the interface itself is not nil. 
- A true **nil interface value** holds neither value nor concrete type. Calling a method on a nil interface is a **runtime error**. 
- The **empty interface** is that which specifies zero methods. It can hold values of any types. 

## 🚀 Type assertions 

- A **type assertion** provides access to an interface value's **underlying concrete value**.

*See interfaces.md in code snippets for an examples and further explanations!*

### 🔦 Type switches

- A **type switch** is a construct that permits several type assersions in series. 
- It is similar to a regular switch statement. 

*See interfaces.md in code snippets for an example and further explanations!*

## 🐝 Stringer 

- **Stringer** is an interface that is defined by the fmt package: 
```go 
type Stringer interface {
    String() string
}
```
- A Stringer type is a type that can describe itself as a **string**. 




