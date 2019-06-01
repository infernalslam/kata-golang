# kata-golang

inspire from learnxinyminutes!

learn struct in 10s

```go
package main

import "fmt"


type user struct {
	name string
	surname string
	age int
	id int
}


func main () {
	u := user{ "bar", "foo", 25, 1 }
	fmt.Println(u) // {bar foo 25 1}
}


```


learn interface in 10s

```go

package main

import "fmt"

type number struct {
	digit1 float64
	digit2 float64
	digit3 float64
}

type calculate interface {
	add() float64
}

// func (struct) interface() return_type {}

func (n number) add() float64 {
	return n.digit1 + n.digit2 + n.digit3
}


func main () {
	var c calculate
	c = number{1, 2, 3}
	fmt.Println(c.add()) // 6
}
```



run test interface 

```go
package main

import "testing"

func TestInterfacecalculate(t *testing.T) {
	var c Calculate
	c = NumberDigit{1, 1, 1}
	ans := c.Add()
	want := float64(3)
	if ans != want {
		t.Errorf("Sum was incorrect, got: %f, want: %f.", ans, want)
	}
}

```

main.go

```go
package main

import "fmt"

// NumberDigit must test
type NumberDigit struct {
	digit1 float64
	digit2 float64
	digit3 float64
}

// Calculate must test
type Calculate interface {
	Add() float64
}

// func (struct) interface() return_type {}

// Add must test
func (n NumberDigit) Add() float64 {
	return addDigit(n)
}

func addDigit(n NumberDigit) float64 {
	return n.digit1 + n.digit2 + n.digit3
}

func main() {
	var c Calculate
	c = NumberDigit{1, 2, 3}
	fmt.Println(c.Add())
}

```
