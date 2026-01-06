# 🧵 Goroutines in Go

## 📌 What is a Goroutine?

A **goroutine** is a lightweight thread managed by the **Go runtime**.

> Goroutines allow Go programs to run multiple functions **concurrently**.

They are:
- Very cheap to create
- Faster than OS threads
- Managed by Go scheduler

---

## 🧠 Why Goroutines?

Without goroutines, programs run **sequentially**:

```bash
Task 1 → Task 2 → Task 3
# 🧵 Goroutines in Go

## 🔄 Concurrency with Goroutines

With goroutines, tasks can run **concurrently**:

```bash
Task 1 ──┐
Task 2 ──┼── running together
Task 3 ──┘
```



Creating a Goroutine

Use the go keyword to start a goroutine.

go functionName()

✅ Example
package main

import (
	"fmt"
	"time"
)

func sayHello() {
	fmt.Println("Hello from goroutine")
}

func main() {
	go sayHello()
	time.Sleep(time.Second)
}


📌 time.Sleep is used so the program doesn’t exit before the goroutine runs.

⚠️ Important Rule

When the main function exits, all goroutines stop immediately.

🔄 Goroutine vs Normal Function Call
sayHello()     // normal call (blocking)
go sayHello()  // goroutine (non-blocking)


Normal function waits until execution finishes

Goroutine runs independently

📦 Anonymous Goroutines

You can run anonymous functions as goroutines.

go func() {
	fmt.Println("Running anonymous goroutine")
}()

🔗 Goroutines + Channels

Goroutines communicate using channels.

Example
package main

import "fmt"

func worker(ch chan int) {
	ch <- 10
}

func main() {
	ch := make(chan int)
	go worker(ch)
	fmt.Println(<-ch)
}


📌 Channels block until data is sent or received.

🧪 Multiple Goroutines Example
package main

import (
	"fmt"
	"time"
)

func task(name string) {
	for i := 1; i <= 3; i++ {
		fmt.Println(name, i)
		time.Sleep(time.Millisecond * 500)
	}
}

func main() {
	go task("A")
	go task("B")
	task("C")
}


📌 Output order is not guaranteed.

🧠 Goroutine Scheduling

Managed by Go scheduler

Uses M:N scheduling model

Thousands of goroutines run on a few OS threads

🧨 Common Problem: Race Condition

Occurs when multiple goroutines access shared data without synchronization.

count := 0

go func() { count++ }()
go func() { count++ }()


❌ Result is unpredictable.

🔒 Solution: sync.Mutex
var mu sync.Mutex
count := 0

mu.Lock()
count++
mu.Unlock()


Ensures only one goroutine modifies shared data at a time.

🛠 Debugging Goroutines

Use Go race detector:

go run -race main.go

🧠 Goroutine vs Thread
Feature	Goroutine	Thread
Memory	KBs	MBs
Creation Time	Very fast	Slow
Managed By	Go runtime	OS
✅ Best Practices

Prefer channels over shared memory

Avoid goroutine leaks

Synchronize shared data properly

Don’t start goroutines blindly

🧠 One-Line Summary

Goroutines are lightweight concurrent functions managed by the Go runtime.

📚 Related Topics

Channels

select

Mutex

Worker Pools

Context cancellation

Happy Coding 🚀


---

If you want next, I can:
- 📄 Write `channels.md`
- 🔥 Worker pool pattern
- 🧠 Concurrency vs Parallelism
- 📌 Goroutine leaks & context usage

Just tell me 👍
