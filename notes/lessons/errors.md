# ❌ Errors 

- In Go, errors are represented using error values. The error type itself is a built-in interface defined as:

```go 
type error interface {
    Error() string
}
```
- Many functions return an error value alongside their regular results. To handle errors properly, the calling code typically checks if the returned error is nil. If it’s not nil, it indicates that something went wrong and needs to be addressed.