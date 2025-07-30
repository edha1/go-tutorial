# 📖 Readers 

- The **Reader** interface is defined in Go’s **io** package.  
- The **io.reader** interface requires a single method:

```go
  func (T) Read(b []byte) (n int, err error)
```

- This method reads data into the provided byte slice b, returning the number of bytes read (n) and an error value if one occurs.


# 🖼️ Images 

- The **Image** interface is defined by the **image Package**. 

```go
package image

type Image interface {
    ColorModel() color.Model
    Bounds() Rectangle
    At(x, y int) color.Color
}
```
