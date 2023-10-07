
## Channels are unidirectional

Channels are unidirectional, meaning that if you want to send and receive data from the same channel, you need to create two channels.

```go
func main() {
    ch := make(chan int)
    go func() {
        ch <- 42
    }()
    fmt.Println(<-ch)
}
```

