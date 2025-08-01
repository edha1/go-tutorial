# 🐹 Goroutines 

- A Goroutine is a **thread** which is managed by the Go runtime. 

```go 
go f(x, y, z)
```
- The above code will start a new goroutine running the function f. 
- The evaluation will occur in the **current goroutine**, but the execution will occur in the **new goroutine**.
- Goroutines **share address space**, so access to the memory must be **synchronised.**  

# 📺 Channels 

- A **channel** is a pipe (or **conduit**) that allows goroutines to communicate with each other by **sending and receiving** values of a **specific type**. 
- A **typed conduit** is a channel that allows only **values of a certain type**. 
- Channels must be created before use: 
```go 
ch := make(chan int)
```
- In the above code, a channel of integers has been created. 

## 🔹 Channel Operator 
- The channel operator is **<-**. 
- It is used to **send** and **receive** values: 

```go 
ch <- value // sending a value to the channel 
value := <- ch // receiving a value from the channel
```
- Communication is blocked until the other side is ready. This allows for synchronisation. 
- Passing messages through channels is a concept called **communicating sequential processes**. 

*See channels.md in code snippets for an example!* 


- Channels can be **closed** and the receiver can use an **Ok** variable to check if the channel is closed. 
- Channels **must** be closed by the **sender** (never the receiver).

## 🫵 Selects
- A **select** is a statement that lets a goroutine **wait on multiple communcation operations.**

*See goroutines.md in code-snippets for examples*

# ✨ Mutual Exclusion 

- **Mutual exclusion** is the concept of making sure only **one goroutine can access a variable at a given time.**
- **Mutex** is the data structure that provides mutual exclusion. It gives us two methods: **Lock** and **Unlock**. 
- Defining a block of code to be executed in mutual exclusion should be surrounded by Unlock or Lock. 


