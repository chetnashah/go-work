
## Strings are just byte slices i.e. []byte

## CodePoint

The Unicode standard uses the term “code point” to refer to the item represented by a single value. The code point U+2318, with hexadecimal value 2318, represents the symbol ⌘. The code point U+1F4A9, with hexadecimal value 1F4A9, represents the character 💩.

### How many bytes does a codepoint take?

U+0000 to U+007F are (correctly) encoded with one byte
U+0080 to U+07FF are encoded with 2 bytes
U+0800 to U+FFFF are encoded with 3 bytes
U+010000 to U+10FFFF are encoded with 4 bytes

with 4 bytes i.e. `2^32` there are roughli 2 billion codepoints.

## Runes are codepoints

The Go language defines the word rune as an alias for the type `int32` (which is equivalent to 32 bits or 4 bytes).

A rune literal is expressed as one or more characters enclosed in **single quotes**, such as 'x' or 'Ø'. 

A string literal, on the other hand, is expressed as one or more characters enclosed in double quotes, such as "hello" or "世界".

### Range loop iteration of strings is by rune

A for range loop, by contrast, decodes one UTF-8-encoded rune on each iteration. Each time around the loop, the index of the loop is the starting position of the current rune, measured in bytes, and the code point is its value. The iteration terminates when the index reaches the length of the string.

```go
const nihongo = "日本語"
for index, runeValue := range nihongo {
    fmt.Printf("%#U starts at byte position %d\n", runeValue, index)
}
// Output:
// U+65E5 '日' starts at byte position 0
// U+672C '本' starts at byte position 3
// U+8A9E '語' starts at byte position 6
```