
## The context Interface

```go
Context {
    Get(key) -> value
    Set(key, value) -> Context // return a new Context
}
```

## Create a context

```go
ctx := context.WithValue(context.Background(), "key", "value")
```


