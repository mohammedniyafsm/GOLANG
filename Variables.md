Go (Golang) Variables – Beginner Notes

Simple and clean explanation of variables in Go.

What is a Variable?

A variable is a named storage location used to store data.

In Go, every variable has:

a name

a type

a value

Variable Declaration
Using var
var age int
age = 21


Assign immediately:

var age int = 21

Type Inference

Go automatically infers the type.

var name = "Niyaf"
var score = 100

Short Variable Declaration (:=)

Most common way (inside functions only).

name := "Niyaf"
age := 21
isDeveloper := true


Notes

Works only inside functions

Type is inferred

Multiple Variables
Same type
var x, y, z int = 1, 2, 3

Different types
var (
    name string = "Niyaf"
    age  int    = 21
    city string = "Calicut"
)

Zero Values

Uninitialized variables get default values.

Type	Zero Value
int	0
float	0.0
string	""
bool	false
pointer	nil
var count int
var title string
var active bool

Constants

Constants cannot be changed.

const pi = 3.14
const appName = "GoApp"


❌ Not allowed:

pi = 3.1415

Typed vs Untyped Constants
const a = 10
const b int = 10


Untyped constants are more flexible.

Variable Scope
Local
func main() {
    x := 10
}

Global (Package-level)
package main

var appVersion = "1.0.0"

Naming Rules

✅ Valid:

camelCase → userName

meaningful names → totalScore

❌ Invalid:

starts with number → 1value

keywords → var, func

Example Program
package main

import "fmt"

func main() {
    name := "Niyaf"
    age := 21
    isDev := true

    fmt.Println("Name:", name)
    fmt.Println("Age:", age)
    fmt.Println("Developer:", isDev)
}

Key Takeaways

Go is strongly typed

Prefer := inside functions

Zero values prevent bugs

Constants are immutable

