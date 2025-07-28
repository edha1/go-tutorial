# 〚〛Arrays 

*See arrays.md in code-snippets for examples!* 

- Defining var x [n]T is an array named **x** with **n** values and all the values are of type **T.**
- Arrays have a fixed size (like in Java). 


# ◖ Slices 

- A slice is a dynamically sized array. 
- It is defined by specifying two indicies: a **lower bound** and an **upper bound**. 
- The default lower bound is **zero** and the default upper bound is the **length of the slice.** 

For example: 

```go 
x[3:7] // this will create a slice with the elements at indices 3,4,5,6 (the higher bound is not included). 
```

- A slice only describes a **section of an underlying array.**
- Changing elements of the slice will also modify the elements of the underlying array. 
- Zero value of a slice is **nil**
- Can create slices of slices (to make a 2d array, for example)

```go 
[]int{1,2,3,4} // This creates an array and a slice which references the array
```

- The **length** of a slice is the number of elements it contains (len(s)). 
- The **capacity** of a slice is the number of elements in the underlying array (cap(s)). 
- If you access or slice beyond capacity, it will cause a Go **panic**. 
- If you append beyond capacity, a **new array** will be allocated. (More on this below...)

# ❗ Dynamically sized arrays (make function)

*See slices.md in code-snippets for examples!* 

- Slices can be created with the **make** function. 
- The function allocates a zeroed array and returns a slice that refers to that array: 
 
 ## 🔗 Append function 
 
 - Used to **add** elements to a slice. 
 Syntax: 
 - The **...** operator can be used to append all elements of another slice: 
 - Append does not modify the original slice unless you assign the result back.
 - If the underlying array is too small, a **bigger array** will be allocated. 

# ♺ Range 

*See slices.md in code-snippets for examples!* 

- Used to **iterate over a slice** or a map. 
- Returns the **index** and a **copy of the element** at that index.  

# 🗺️ Maps

*See maps.md in code-snippets for examples!* 

- Maps **keys** to **values** 
- Zero value is **nil**
- **make** function cna return a map of the given type: 

```go 
m := make(map[KeyType]ValueType) // can also optionally pre-specify the capacity
```

### Map functions:
- **m[key] = elem** // set the value at a key 
- **elem = m[key]** // retrieve a value 
- **delete(m, key)** // delete an element based on key 
- **elem, ok = m[key]** // if the key is present, then ok is true. If not, then ok is false and elem is the zero value for the type of element stored in map.  

 
