# Go Cheat sheet

- This is my version of [Derek Banas' cheat sheet](https://www.newthinktank.com/2015/02/go-programming-tutorial/) from his [youtube channel](https://youtu.be/CF9S4QZuV30)

![go muscot](https://upload.wikimedia.org/wikipedia/commons/thumb/0/05/Go_Logo_Blue.svg/800px-Go_Logo_Blue.svg.png)

- Welcome to my Go Programming Tutorial. Go provides the best of both worlds by striking a balance between dynamic and statically compiled languages. The code is easy to read. The specification is short, but even so it includes a built in web server.

## Extentions to download

- [Go by Go Team at Google](https://marketplace.visualstudio.com/items?itemName=golang.Go)

## Common Commands

- Initialize go project/module
  `go mod init <project name or github repo>`
- Run go file
  `go run <file>`
- Read Docs
  `godoc <package name> <function>`
  _example_
  `godoc fmt Println`

## Intro, Data Types & Arithmetic

```go
// Every Go program starts with a package declaration which provides a way for
// use to reuse code
package main

// import allows use to use code from other packages
// The format package provides formatting for input and output
import "fmt"

// A comment

/*
Multiline Comment
*/

// Functions start with func and surround the code with { }
// main is the function that is executed when you execute your program -> entry point of the program

func main() {

	// Println is a function in the fmt package that outputs a string, which
	// is surrounded by double quotes and a newline to the screen

	fmt.Println("Hello World")

	// You can get a description of a function by typing godoc fmt Println
	// for example in the terminal

	// You execute Go programs like this in the terminal go run main.go

	// Variables are statically typed, which means their type can't change
	// Variable names must start with a letter and may contain letters, numbers
	// or the _

	// An int is a positive or negative number without decimals
	// Versions
	// uint8 : unsigned  8-bit integers (0 to 255)
	// uint16 : unsigned 16-bit integers (0 to 65535)
	// uint32 : unsigned 32-bit integers (0 to 4294967295)
	// uint64 : unsigned 64-bit integers (0 to 18446744073709551615)
	// int8 : signed  8-bit integers (-128 to 127)
	// int16 : signed 16-bit integers (-32768 to 32767)
	// int32 : signed 32-bit integers (-2147483648 to 2147483647)
	// int64 : signed 64-bit integers (-9223372036854775808 to
	// 9223372036854775807)

	var age int64 = 40

	// A float is a number with decimals
	// Versions : float32, float64

	var favNum float64 = 1.61803398875

	// You don't need to define the data type, nor do you need a semicolon
	// but you can use them

	randNum := 1;
	fmt.Println(randNum);

	// You can't however assign a non-compatible type later

	// randNum = "Hello"

	// You can use variables in Println (Space is automatically added)

	fmt.Println(age, " ", favNum)

	var numOne = 1.000
	var num99 = .999

	// You can perform arithmetic in Println (Note that floats aren't accurate)

	fmt.Println(numOne - num99)

	// Arithmetic Operators : +, -, *, /, %

	fmt.Println("6 + 4 =", 6 + 4)
	fmt.Println("6 - 4 =", 6 - 4)
	fmt.Println("6 * 4 =", 6 * 4)
	fmt.Println("6 / 4 =", 6 / 4)
	fmt.Println("6 % 4 =", 6 % 4)

}
```

## Const, Strings, Booleans, Printf

```go
package main

import "fmt"

func main() {

// A constant is a variable with a value that can't be changed

	const pi float64 = 3.14159265359

	// You can declare multiple variables like this

	var (
		varA = 2
		varB = 3
	)

	fmt.Println(varA, varB)

	// Strings are a series of characters between " or `

	var myName string = "Derek Banas"

	// Get string length

	fmt.Println(len(myName))

	// You can combine strings with + (concatenation

	fmt.Println(myName + " is a robot")

	// Strings between " can contain escape symbols like \n for newline

	fmt.Println("I like \n \n")

	fmt.Println("Newlines")

	// Booleans can be either true or false

	var isOver40 bool = true

	fmt.Println(isOver40)

	// Printf is used for format printing (%f is for floats) but it doesnt add a new line at the end

	fmt.Printf("%f \n", pi)

	// You can also define the decimal precision of a float

	fmt.Printf("%.3f \n", pi)

	// %T prints the data type

	fmt.Printf("%T \n", pi)

	// %t prints booleans

	fmt.Printf("%t \n", isOver40)

	// %d is used for integers

	fmt.Printf("%d \n", 100)

	// %b prints in binary representation

	fmt.Printf("%b \n", 100)

	// %c prints the character associated with a keycode

	fmt.Printf("%c \n", 44)

	// %x prints in hexcode

	fmt.Printf("%x \n", 17)

	// %e prints in scientific notation

	fmt.Printf("%e \n", pi)

}
```

## Logical Operators, For Loops

```go
package main

import "fmt"

func main() {

	// Logical Operators

	fmt.Println("true && false =", true && false) //false
	fmt.Println("true || false =", true || false) // true
	fmt.Println("!true =", !true) // false

	// For loops

	i := 1

	for i <= 10 {
		fmt.Println(i)

		// Shorthand for i = i + 1

		i++

		// i-- decrement
	}

	// Relational Operators include ==, !=, <, >, <=, and >=

	// You can also define a for loop like this, but you need semicolons

	for j := 0; j < 5; j++ {

		fmt.Println(j);

	}

}
```

# If, Else, Else If, Switch

```go
package main

import "fmt"

func main() {

	// If Statement

	yourAge := 18

	if yourAge >= 16 {
		fmt.Println("You Can Drive")
	} else {
		fmt.Println("You Can't Drive")
	}

	// You can use else if perform different actions, but once a match
	// is reached the rest of the conditions aren't checked

	if yourAge >= 16 {
		fmt.Println("You Can Drive")
	} else if yourAge >= 18 {
		fmt.Println("You Can Vote")
	} else {
		fmt.Println("You Can Have Fun")
	}

	// Switch statements are used when you have limited options

	switch yourAge {
		case 16: fmt.Println("Go Drive")
		case 18: fmt.Println("Go Vote")
		default: fmt.Println("Go Have Fun")
	}

}
```

## Arrays, Slices

```go
package main

import "fmt"

func main() {

	// An Array holds a fixed number of values of the same type

	var favNums2[5] float64

	favNums2[0] = 163
	favNums2[1] = 78557
	favNums2[2] = 691
	favNums2[3] = 3.141
	favNums2[4] = 1.618

	// You access the value by supplying the index number

	fmt.Println(favNums2[3])

	// Another way of initializing an array

	favNums3 := [5]float64 { 1, 2, 3, 4, 5 }

	// How to iterate through an array (Use _ if a value isn't used)

	// for _, value := range favNums3 {
	for i, value := range favNums3 {

		fmt.Println(value, i)

	}

	// Slices are like arrays but you leave out the size

	numSlice := []int {5,4,3,2,1}

	// You can create a slice by defining the first index value to
	// take through the last

	numSlice2 := numSlice[3:5] // numSlice3 == [2,1]

	fmt.Println("numSlice2[0] =", numSlice2[0])

	// If you don't supply the first index it defaults to 0

	fmt.Println("numSlice[:2] =", numSlice[:2])

	// If you don't supply the last index it defaults to max

	fmt.Println("numSlice[2:] =", numSlice[2:])

	// You can also create an empty slice and define the data type,
	// length (how many receive value of 0), capacity (max size)

	numSlice3 := make([]int, 5, 10)

	// You can copy a slice to another

	copy(numSlice3, numSlice)

	fmt.Println(numSlice3[0])

	// Append values to the end of a slice
   // append(slice to append to ,value to append,value to append)
	numSlice3 = append(numSlice3, 0, -1)

	fmt.Println(numSlice3[6])

}
```

## Maps

```go
package main

import "fmt"

func main() {

	// A Map is a collection of key value pairs
	// Created with varName := make(map[keyType] valueType)

	presAge := make(map[string] int)

	presAge["TheodoreRoosevelt"] = 42

	fmt.Println(presAge["TheodoreRoosevelt"])

	// Get the number of items in the Map

	fmt.Println(len(presAge))

	// The size changes when a new item is added

	presAge["John F. Kennedy"] = 43
	fmt.Println(len(presAge))

	// We can delete by passing the key to delete

	delete(presAge, "John F. Kennedy")
	fmt.Println(len(presAge))

}
```

# Maps in Maps

```go
package main

import "fmt"

func main() {

	// We can store multiple items in a map as well

	superhero := map[string]map[string]string{
		"Superman": map[string]string{
			"realname":"Clark Kent",
			"city":"Metropolis",
		},

		"Batman": map[string]string{
			"realname":"Bruce Wayne",
			"city":"Gotham City",
		},
	}

	// We can output data where the key matches Superman

	if temp, hero := superhero["Superman"]; hero {
		fmt.Println(temp["realname"], temp["city"])
	}

}
```

## Functions, Recursion, Recover, Defer, Panic

```go
package main

import "fmt"

func main() {

	listOfNums := []float64{1,2,3,4,5}

	fmt.Println("Sum :", addThemUp(listOfNums))

	// Get 2 values from a function

	num1, num2 := next2Values(5)

	fmt.Println(num1, num2)

	// Send an undefined number of values to a function (Variadic Function)

	fmt.Println(subtractThem(1,2,3,4,5))


	// You can create a function in a function. It has access to the
	// local variables of the containing function
	// A function like this with no local variables is a closure

	num3 := 3

	doubleNum := func() int {

		num3 *= 2
		return num3

	}

	fmt.Println(doubleNum());
	fmt.Println(doubleNum());

	// Calling a recursive function

	fmt.Println(factorial(3))

	// Defer executes a function after the inclosing function finishes
	// Defer can be used to keep functions together in a logical way
	// but at the same time execute one last as a clean up operation
	// Ex. Defer closing a file after we open it and perform operations
// will run printone after main is done
	defer printTwo()
	printOne()

	// Use recover() to catch a division by 0 error
    // it continues execution even afterr fatal errors have occured
	fmt.Println(safeDiv(3, 0))
	fmt.Println(safeDiv(3, 2))

	// We can catch our own errors and recover with panic & recover

	demPanic()

}

// Functions allow us to reuse code and provide structure
// func funcName(parametersPassed) returnType
// Functions don't have access to any variables aside from those
// passed into it

func addThemUp(numbers []float64) float64 {

	sum := 0.0

	for _, val := range numbers {

		// Shorthand for sum = sum + val
		sum += val

	}

	return sum

}

// Go functions can return multiple values

func next2Values(number int) (int, int){

	return number+1, number+2

}

// You can receive an undefined number of values with args ...int

func subtractThem(args ...int) int{

	finalValue := 0

	for _, value := range args {
		finalValue -= value
	}

	return finalValue

}

// Example of recursion : Function calls itself
// factorial(3)
// 3 * factorial(2) == 3 * 2
// 2 * factorial(1) == 2 * 1
// factorial(0) == 1

func factorial(num int) int {
	if num == 0 {
		return 1
	}
	return num * factorial(num - 1)
}

// Used to demonstrate defer

func printOne(){ fmt.Println(1)}

func printTwo(){ fmt.Println(2)}

// If an error occurs we can catch the error with recover and allow
// code to continue to execute

func safeDiv(num1, num2 int) int {
    defer func() {
        fmt.Println(recover())
    }()
    solution := num1 / num2
    return solution
}

// Demonstrate how to call panic and handle it with recover

func demPanic(){

	defer func() {

		// If I didn't print the message nothing would show

		fmt.Println(recover())

	}()
	panic("PANIC")

}
```

## Go Pointers

```go
package main

import "fmt"

// POINTERS

func main() {

	// We pass the value of a variable to the function
	x := 0
	changeXVal(x)
	fmt.Println("x =",x)

	// If we pass a reference to the variable we can change the value
	// in a function
	changeXValNow(&x)
	fmt.Println("x =",x)

	// Get the address x points to with &
	fmt.Println("Memory Address for x =", &x)

	// We can also generate a pointer with new

	yPtr := new(int)
	changeYValNow(yPtr)
	fmt.Println("y =", *yPtr)

}

func changeXVal(x int) {

	// Has no effect on the value of x in main()
	x = 2

}

// * signals that we are being sent a reference to the value
func changeXValNow(x *int){

	// Change the value at the memory address referenced by the pointer
	// * gives us access to the value the pointer points at

	*x = 2 // Store 2 in the memory address x refers to

}

func changeYValNow(yPtr *int){

	*yPtr = 100

}
```

## Structs

```go
package main

import "fmt"

// STRUCTS

func main() {

// Define a rectangle
rect1 := Rectangle{leftX: 0, TopY: 50, height: 10, width: 10}

// Leave off attribute names if we know the order
 rect2 := Rectangle{0, 50, 10, 10}

// We access values with the dot operator
fmt.Println("Rectangle is", rect1.width, "wide")

// Call the method area for Rectangle
fmt.Println("Area of the rectangle =", rect1.area())

}

// We can define our own types using struct
type Rectangle struct{
	leftX float64
	TopY float64
	height float64
	width float64
}

// We can define methods for our Rectangle by adding the receiver
// rect *Rectangle between func and the function name so we can
// call it with the dot operator
func (rect *Rectangle) area() float64{

	return rect.width * rect.height

}
```

## Go Structs & Interfaces

```go
package main

import "fmt"
import "math"

// STRUCTS AND INTERFACES

func main() {

	rect := Rectangle{20, 50}
	circ := Circle{4}

	fmt.Println("Rectangle Area =", getArea(rect))
	fmt.Println("Circle Area =", getArea(circ))

}

// An interface defines a list of methods that a type must implement
// If that type implements those methods the proper method is executed
// even if the original is referred to with the interface name

type Shape interface {
	area() float64
}

type Rectangle struct{
	height float64
	width float64
}

type Circle struct{
	radius float64
}

func (r Rectangle) area() float64 {
	return r.height * r.width
}

func (c Circle) area() float64 {
	return math.Pi * math.Pow(c.radius, 2)
}

func getArea(shape Shape) float64{

	return shape.area()

}
```

## Strings, File I/O, Excepting Input, Casting

```go
package main

import ("fmt"
"strings"
"sort"
"os"
"log"
"io/ioutil"
"strconv")

func main() {

	// STRING FUNCTIONS

	sampString := "Hello World"

	// Returns true if phrase exists in string
	fmt.Println(strings.Contains(sampString, "lo"))

	// Returns the index for the match
	fmt.Println(strings.Index(sampString, "lo"))

	// Returns the number of matches for the string
	fmt.Println(strings.Count(sampString, "l"))

	// Replaces the first letter with the second as many times as you define
	fmt.Println(strings.Replace(sampString, "l", "x", 3))

	// Return a list separating with the defined separator
	csvString := "1,2,3,4,5,6"
	fmt.Println(strings.Split(csvString, ","))

	listOfLetters := []string{"c", "a", "b"}
	sort.Strings(listOfLetters)
	fmt.Println("Letters:", listOfLetters)

	// Returns a string using the values passed in separated with separator
	listOfNums := strings.Join([]string{"3", "2", "1"}, ", ");

	fmt.Println(listOfNums);

	// FILE I/O

	// Create a file
	file, err := os.Create("samp.txt")

	// Output any errors
	if err != nil {
		log.Fatal(err)
	}

	// Write a string to the file
	file.WriteString("This is some random text")

	// Close the file
	file.Close()

	// Try to open the file
	stream, err := ioutil.ReadFile("samp.txt")

	if err != nil {
		log.Fatal(err)
	}

	// Convert into a string
	readString := string(stream)

	fmt.Println(readString)

	// EXCEPTING INPUT

	fmt.Println("What is your name? ")

	var name string

	fmt.Scan(&name)

	fmt.Println("Hello", name)

	// CASTING

	randInt := 5
	randFloat := 10.5
	randString := "100"
	randString2 := "250.5"

	// Convert numbers types
	fmt.Println(float64(randInt))
	fmt.Println(int(randFloat))

	// Convert a string into an int
	newInt, _ := strconv.ParseInt(randString, 0, 64)
    fmt.Println(newInt)

    // Convert a string into a float
    newFloat, _ := strconv.ParseFloat(randString2, 64)
    fmt.Println(newFloat)

}
```

## Create HTTP Server

```go
package main

import (
    "fmt"
    "net/http"
)

// CREATE A HTTP SERVER

// http.ResponseWriter assembles the servers response and writes to
// the client
// http.Request is the clients request
func handler(w http.ResponseWriter, r *http.Request) {

	// Writes to the client
    fmt.Fprintf(w, "Hello World\n")
}

func handler2(w http.ResponseWriter, r *http.Request) {
    fmt.Fprintf(w, "Hello Earth\n")
}

func main() {

	// Calls for function handlers output to match the directory /
    http.HandleFunc("/", handler)

    // Calls for function handler2 output to match directory /earth
    http.HandleFunc("/earth", handler2)

    // Listen to port 8080 and handle requests
    http.ListenAndServe(":8080", nil)
}
```

## Go Routines

```go
package main

import "fmt"
import "time"

// GO ROUTINES

func count(id int) {
	for i := 0; i < 10; i++ {
		fmt.Println(id, ":", i)

		// Pause the function for 1 second to allow other functions to execute
		time.Sleep(time.Millisecond * 1000)
	}
}

func main() {

	// A go routine is a function that runs in parallel with other functions
	// We define one by using go followed by the function name

	for i := 0; i < 10; i++ {
		go count(i)
	}

	// Wait for the timer to make sure the go routine has time to
	// finish otherwise the program would end before that happens
	time.Sleep(time.Millisecond * 11000)
}
```

## Go Channels

```go
package main

import "fmt"
import "time"
import "strconv"

// CHANNELS
// Channels allow us to pass data between go routines

var pizzaNum = 0
var pizzaName = ""

func makeDough(stringChan chan string){

	pizzaNum++

	// Convert int into a string
	pizzaName = "Pizza #" + strconv.Itoa(pizzaNum)

	fmt.Println("Make Dough and Send for Sauce");

	// Send the pizzaName onto the channel for the next
	stringChan <- pizzaName

	time.Sleep(time.Millisecond * 10)

}

func addSauce(stringChan chan string){

	// Receive the value passed on the channel
	pizza := <- stringChan

	fmt.Println("Add Sauce and Send", pizza, "for Toppings")

	// Send the pizzaName onto the channel for the next
	stringChan <- pizzaName

	time.Sleep(time.Millisecond * 10)

}

func addToppings(stringChan chan string){

	// Receive the value passed on the channel
	pizza := <- stringChan

	fmt.Println("Add Toppings to", pizza, "and Ship")

	time.Sleep(time.Millisecond * 10)

}

func main() {

	// Make creates a channel that can hold a string
	// int channel intChan := make(chan int)
	stringChan := make(chan string)

	// Cycle through and make 3 pizzas
	for i := 0; i < 3; i++{

		go makeDough(stringChan)
		go addSauce(stringChan)
		go addToppings(stringChan)

		time.Sleep(time.Millisecond * 5000)

	}

}
```
