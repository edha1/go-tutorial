# 🧩 Variables 

- **var** declares a list of variables. The type is last: 
```go 
var x, y, z int 
```
- We can initialise variables as such: 
```go 
var x, y int = 1, 2 // type can be ommitted 
```
- Inside a function, **:=** can be used in place of var with an implicit type.

*See variable-declaration.md for an example!* 

## 🐣 Basic types 

- Go has the following **basic types**: 
    - bool 
    - string
    - int
    - int8 (integer of 8 bits)
    - int16
    - int32 
    - int64
    - uint (unsigned integer)
    - uint8
    - uint16
    - uint32
    - uint64
    - uintptr (unsigned integer type that is large enough to store the bit pattern of any pointer value) 
    - byte (same as uint8)
    - rune (same as int32)
    - float32
    - float64 
    - complex64
    - complex128

    The size of int and uint depends on the system. If you are running on 32-bit system, it is 32 bits. If you are running on a 64 bit system, it will be 64 bits. 

### ⚠️ Type Conversion 

- The expression **T(v)** will convert the value **v** to the type **T**. 

**In Go, you must explicitly convert between different types, even if they are both numbers or even when there is no loass of precision. This is enforced for clarity and safety.**


### 🧠 Type inference 

- When declaring a variable, if there is no explicit type, the type is **inferred** by the right hand side. 

### 🔒 Constants 

- **Constants** are declared via **const** and they cannot be declared using :=. 
- **Numeric** constants are **high precision values**. This means that they are not immediately tied to a fixed type. They can represent very large integers or very precise floating point numbers without losing accuracy at the constant stage. When you write a constant **without explicitly giving it a type**, it is **untyped**. Then, the constant will automatically assume a type based on how you use it. If you assign it to an int variable, it will convert the constant to an int. 
