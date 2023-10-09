
## Why Context?

Context is used to pass request scoped values, cancellation signals, deadlines across API boundaries and goroutines.

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


