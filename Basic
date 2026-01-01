# Hello World

In Go, every source file **must declare a package** at the top. This tells Go how the file is organized and which executable or library it belongs to.

---

## Program Structure

```go
package main

import "fmt"

func main() {
	fmt.Println("Hello world")
}
```

### Explanation

* `package main` → entry package for executable programs
* `import "fmt"` → standard library for formatted I/O
* `main()` → program entry point

---

## Run the Program

```bash
go run main.go
```

---

## Multiple Imports Example

```go
package main

import (
	"fmt"
	"math/rand"
)

func main() {
	fmt.Println("Random number:", rand.Int31n(10))
}
```

### Notes

* Parentheses allow grouping imports
* Package names are used directly (no namespaces)

---

# Variables and Constants

## Simple Data Types

* Numbers (int, float64)
* Boolean (bool)
* String (string)

```go
var a int = 42
var b float64 = 3.14
var c bool = true
var d string = "Hello, Go!"
```

---

## Shorthand Syntax (Inside Functions Only)

```go
a := 42
b := 3.14
c := true
d := "Hello, Go!"
```

### Rules

* `:=` **cannot** be used outside functions
* Go automatically infers the type

---

## Multiple Variable Declaration

```go
var x, y, z int = 1, 2, 3

name, age := "Niyaf", 22
```

---

## Zero Values

If a variable is declared but not initialized:

```go
var a int      // 0
var b bool     // false
var c string   // ""
```

---

## Constants

```go
const pi = 3.14
const isReady = true
```

### Rules

* Constants cannot be changed
* Must be known at compile time

---

## iota (Auto Increment Constants)

```go
const (
	Low = iota
	Medium
	High
)
```

Values:

* Low = 0
* Medium = 1
* High = 2

---

# Control Flow

## For Loop

### Standard Loop

```go
sum := 0
for i := 1; i < 10; i++ {
	sum += i
}
```

---

### Range Loop

```go
sum := 0
for i := range 10 {
	sum += i
}
```

---

### While-style Loop

```go
i := 0
for i < 5 {
	i++
}
```

---

### Infinite Loop

```go
for {
	println("running")
}
```

---

## break and continue

```go
for i := 0; i < 10; i++ {
	if i == 5 {
		break
	}
	if i%2 == 0 {
		continue
	}
	println(i)
}
```

---

## If / Else

```go
a := 2
if a%2 == 0 {
	println("Even")
} else {
	println("Odd")
}
```

---

### Else If

```go
if a > 10 {
	println("Big")
} else if a > 5 {
	println("Medium")
} else {
	println("Small")
}
```

---

## Switch

```go
gender := "male"

switch gender {
case "male":
	println("You are male")
case "female":
	println("You are female")
default:
	println("Other")
}
```

---

### Switch Without Expression

```go
x := 10
switch {
case x < 5:
	println("Small")
case x < 15:
	println("Medium")
default:
	println("Large")
}
```

---

# Printing Output

## fmt vs println

```go
fmt.Println("Hello")  // recommended
println("Hello")     // low-level, not for production
```

---

# Common Beginner Mistakes

❌ `fmt.println()`

✅ `fmt.Println()`

❌ Using `:=` outside function

❌ Unused variables (Go will not compile)

---

# Key Takeaways

* Go is strict but simple
* One entry point: `main()`
* No unused variables allowed
* Clear, readable control flow

---

✅ **This completes Go basics fully**
