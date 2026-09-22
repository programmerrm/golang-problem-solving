# Go — Day One: Variables & Problem Solving

> **Goal:** Learn Go variables by solving problems instead of memorizing syntax.

This is my **Go Day One** learning journey.

I will learn the different types of variables, declarations, data types, type conversion, constants, scope, zero values, and related concepts **through practical problem solving**.

The main idea is:

> **Learn → Understand → Solve Problems → Make Mistakes → Debug → Refactor → Record What I Learned**

---

## 🎯 Day One Goal

By the end of Day One, I should be able to:

* Understand what a variable is
* Declare variables in Go
* Understand Go's static type system
* Use `var`
* Use `:=`
* Declare multiple variables
* Initialize variables
* Reassign variables
* Understand zero values
* Understand constants
* Work with different primitive data types
* Understand type inference
* Perform type conversion
* Understand variable scope
* Understand local and package-level variables
* Understand when to use each variable declaration style
* Solve beginner-level problems using variables
* Read and debug variable-related errors
* Explain my code without depending on memorization

---

# 🧠 Learning Philosophy

I will **not** learn Go variables by reading all syntax first and then trying to memorize it.

Instead, I will learn through problems.

### Learning cycle

```text
Problem
   ↓
Think
   ↓
Write a solution
   ↓
Run the program
   ↓
Get error / unexpected output
   ↓
Understand why
   ↓
Fix it
   ↓
Refactor
   ↓
Write what I learned
   ↓
Solve the next problem
```

The objective is not just:

> "I can write the syntax."

The objective is:

> "I understand why this variable is needed, what type it should have, and how Go handles it."

---

# 📚 Day One Topics

## 1. What is a Variable?

A variable is a named location used to store a value.

Example:

```go
var age int = 21
```

Here:

```text
age   → variable name
int   → data type
21    → value
```

---

# 2. `var` Declaration

Basic syntax:

```go
var name string
```

With initialization:

```go
var name string = "Rasel"
```

Go can also infer the type:

```go
var name = "Rasel"
```

### Problems to solve

* Store a person's name
* Store age
* Store salary
* Store city
* Store whether a user is active

---

# 3. Short Variable Declaration `:=`

Go provides a shorter way to declare and initialize variables:

```go
name := "Rasel"
age := 21
```

This is called **short variable declaration**.

### Important

`:=` is generally used inside functions.

Example:

```go
func main() {
    name := "Rasel"
    age := 21

    fmt.Println(name)
    fmt.Println(age)
}
```

### Problems to solve

* Create variables for a student
* Create variables for a product
* Calculate total price
* Calculate age
* Store user information

---

# 4. Variable Reassignment

A variable can receive a new value after declaration.

```go
age := 21

age = 22
```

But the new value must be compatible with the variable's type.

Example:

```go
age := 21

age = 25
```

---

# 5. Go's Static Type System

Go is statically typed.

Example:

```go
age := 21
```

Go understands:

```text
age → int
```

This will not work:

```go
age = "twenty one"
```

because `age` is an `int`.

### Problem-solving objective

Learn to identify:

```text
What is the variable?
What type should it be?
What values can it contain?
```

---

# 6. Basic Go Data Types

I will learn the data types through problems.

## Integer Types

```go
int
int8
int16
int32
int64

uint
uint8
uint16
uint32
uint64
```

Example:

```go
age := 21
```

---

## Floating-Point Types

```go
float32
float64
```

Example:

```go
price := 99.99
```

---

## Boolean

```go
bool
```

Example:

```go
isActive := true
```

---

## String

```go
string
```

Example:

```go
name := "Rasel"
```

---

## Complex Numbers

```go
complex64
complex128
```

Example:

```go
number := complex(10, 5)
```

These will be introduced through appropriate problems instead of memorizing them separately.

---

# 7. Zero Values

One important Go concept is **zero value**.

When a variable is declared without an explicit value, Go gives it a default zero value.

Examples:

```go
var age int
```

Result:

```text
0
```

```go
var price float64
```

Result:

```text
0
```

```go
var name string
```

Result:

```text
""
```

```go
var active bool
```

Result:

```text
false
```

### Problems

Find the default value of:

* `int`
* `float64`
* `bool`
* `string`
* pointers
* slices
* maps
* interfaces

---

# 8. Multiple Variable Declaration

Go allows multiple variables.

```go
var name, city string
```

Or:

```go
name, age := "Rasel", 21
```

### Problems

Create a student profile using multiple variables.

Example:

```go
name := "Rasel"
age := 21
city := "Sherpur"
```

---

# 9. Multiple Assignment

Go supports multiple assignment.

```go
a, b := 10, 20
```

And:

```go
a, b = b, a
```

This can be used to swap values without a temporary variable.

### Problem

Given:

```text
a = 10
b = 20
```

Swap them so:

```text
a = 20
b = 10
```

---

# 10. Type Inference

Go can determine the type from the assigned value.

Example:

```go
age := 21
```

Go infers:

```text
int
```

Example:

```go
price := 99.99
```

Go infers:

```text
float64
```

Example:

```go
name := "Rasel"
```

Go infers:

```text
string
```

### Problems

Predict the type before running the program.

---

# 11. Type Conversion

Go does not automatically convert many numeric types.

Example:

```go
var age int = 21
var price float64 = float64(age)
```

Conversion:

```go
float64(age)
```

Another example:

```go
var x float64 = 10.5
var y int = int(x)
```

### Important

Type conversion can cause loss of information.

Example:

```go
x := 10.9
y := int(x)
```

Result:

```text
10
```

### Problems

* Convert `int` → `float64`
* Convert `float64` → `int`
* Convert numeric values for calculations
* Understand what happens to decimal values

---

# 12. Constants

Constants are values that cannot be changed after declaration.

```go
const pi = 3.14159
```

Example:

```go
const daysInWeek = 7
```

Trying to change it:

```go
daysInWeek = 8
```

will produce an error.

### Problems

Use constants for:

* PI
* Days in a week
* Hours in a day
* Fixed tax rate
* Fixed application configuration values

---

# 13. Typed and Untyped Constants

Go has an important distinction between typed and untyped constants.

Example:

```go
const age = 21
```

And:

```go
const age int = 21
```

I will understand the difference through problems rather than memorizing definitions.

---

# 14. Variable Scope

Scope determines where a variable can be accessed.

Example:

```go
func main() {
    age := 21

    fmt.Println(age)
}
```

`age` exists inside `main`.

### Problems

Understand:

* Local variables
* Function scope
* Package-level variables
* Block scope
* Shadowing

---

# 15. Package-Level Variables

Example:

```go
package main

var appName = "My Application"

func main() {
    fmt.Println(appName)
}
```

This variable exists outside the function.

---

# 16. Variable Shadowing

Example:

```go
var age = 30

func main() {
    age := 21

    fmt.Println(age)
}
```

The local `age` shadows the package-level `age`.

I will learn this by debugging problems where the output is not what I initially expect.

---

# 17. Blank Identifier `_`

Go uses `_` when a returned value is intentionally ignored.

Example:

```go
_, err := someFunction()
```

This concept will be introduced when solving problems involving multiple return values.

---

# 🧩 Problem-Solving Structure

Every problem will follow this structure.

## Problem

Clearly understand what the program needs to do.

## Step 1 — Understand the Input

Ask:

```text
What values do I have?
```

## Step 2 — Identify Variables

Ask:

```text
What information needs to be stored?
```

## Step 3 — Select Data Types

Ask:

```text
Should this be int?
float64?
string?
bool?
```

## Step 4 — Write the Smallest Solution

Do not over-engineer the first solution.

## Step 5 — Run

```bash
go run .
```

## Step 6 — Debug

If there is an error:

```text
Read the error
↓
Find the line
↓
Understand the reason
↓
Fix it
```

## Step 7 — Refactor

Ask:

```text
Can I make this simpler?
Can I make this clearer?
Am I using the correct type?
```

## Step 8 — Record Learning

For every important problem, write:

```text
What did I learn?
What mistake did I make?
Why did the error happen?
How did I fix it?
```

---

# 🧪 Problem Levels

## Level 1 — Basic Variables

### Problem 01

Store and print:

```text
Name
Age
City
```

### Problem 02

Store:

```text
Product name
Price
Quantity
```

Calculate total price.

### Problem 03

Store a student's:

```text
Name
Age
Marks
Passed/Failed
```

---

# Level 2 — Variable Operations

Problems involving:

* Addition
* Subtraction
* Multiplication
* Division
* Remainder
* Increment
* Decrement

Example:

```text
Given:
price = 100
quantity = 5

Find:
total = 500
```

---

# Level 3 — Type Conversion

Problems involving:

```text
int → float64
float64 → int
```

And understanding data loss.

---

# Level 4 — Multiple Variables

Problems involving:

* Multiple declarations
* Multiple assignment
* Swapping values
* Calculations using multiple variables

---

# Level 5 — Constants

Problems involving fixed values:

```text
PI
Tax rate
Days in week
Hours in day
```

---

# Level 6 — Scope

Problems involving:

* Local variables
* Package variables
* Shadowing
* Block scope

---

# Level 7 — Debugging Problems

Instead of writing the solution from scratch, I will receive broken code.

Example:

```go
func main() {
    age := 21

    age = "twenty one"

    fmt.Println(age)
}
```

My task:

1. Find the error
2. Explain the error
3. Fix it
4. Explain why the fix works

---

# 📝 Learning Log

For every problem I solve, I will record something like this:

```text
Problem:
Calculate total price.

Variables:
price   → float64
quantity → int
total   → float64

What I learned:
Go is statically typed.

Mistake:
I tried to assign a string to an int variable.

Error:
cannot use "5" as int value

Fix:
Convert the input/value to the correct type.

Important lesson:
A variable's type determines what kind of value it can store.
```

---

# 📂 Suggested Folder Structure

```text
day-01-variables/
│
├── README.md
│
├── 01-basic-variables/
│   ├── problem-01.go
│   ├── problem-02.go
│   └── problem-03.go
│
├── 02-var/
│   ├── problem-01.go
│   └── problem-02.go
│
├── 03-short-declaration/
│   ├── problem-01.go
│   └── problem-02.go
│
├── 04-data-types/
│   ├── integer.go
│   ├── float.go
│   ├── string.go
│   └── boolean.go
│
├── 05-zero-values/
│   └── problems.go
│
├── 06-type-conversion/
│   └── problems.go
│
├── 07-constants/
│   └── problems.go
│
├── 08-scope/
│   └── problems.go
│
├── 09-debugging/
│   └── problems.go
│
└── 10-final-problems/
    ├── problem-01.go
    ├── problem-02.go
    └── problem-03.go
```

---

# 📊 Day One Checklist

## Variable Basics

* [ ] What is a variable?
* [ ] `var`
* [ ] `:=`
* [ ] Variable initialization
* [ ] Variable reassignment
* [ ] Multiple variables
* [ ] Multiple assignment
* [ ] Variable naming

## Data Types

* [ ] `int`
* [ ] `int8`
* [ ] `int16`
* [ ] `int32`
* [ ] `int64`
* [ ] `uint`
* [ ] `uint8`
* [ ] `uint16`
* [ ] `uint32`
* [ ] `uint64`
* [ ] `float32`
* [ ] `float64`
* [ ] `bool`
* [ ] `string`
* [ ] `complex64`
* [ ] `complex128`

## Go Concepts

* [ ] Static typing
* [ ] Type inference
* [ ] Zero values
* [ ] Type conversion
* [ ] Constants
* [ ] Typed constants
* [ ] Untyped constants
* [ ] Variable scope
* [ ] Package-level variables
* [ ] Local variables
* [ ] Block scope
* [ ] Variable shadowing
* [ ] Blank identifier `_`

## Problem Solving

* [ ] Basic variable problems
* [ ] Calculation problems
* [ ] Type conversion problems
* [ ] Multiple assignment problems
* [ ] Constant problems
* [ ] Scope problems
* [ ] Debugging problems
* [ ] Mixed problems
* [ ] Final challenge

---

# 🏆 Final Day One Challenge

At the end of Day One, I will solve problems without looking at previous solutions.

The problems should combine multiple concepts.

For example:

```text
Create a simple employee salary calculator.

Input:
Employee name
Basic salary
Bonus
Tax percentage

Calculate:
Gross salary
Tax amount
Net salary
```

The solution should require:

```text
Variables
↓
Data types
↓
Arithmetic
↓
Type conversion
↓
Constants
↓
Output
```

---

# 🔍 Questions I Should Be Able to Answer

Before moving to Day Two, I should be able to explain:

### 1.

What is the difference between:

```go
var age int = 21
```

and:

```go
age := 21
```

### 2.

What is the zero value of:

```go
int
float64
bool
string
```

### 3.

Why does this fail?

```go
age := 21
age = "21"
```

### 4.

What happens here?

```go
x := 10.9
y := int(x)
```

### 5.

What is the difference between:

```go
const age = 21
```

and:

```go
var age = 21
```

### 6.

Why does this work?

```go
a, b := 10, 20
a, b = b, a
```

### 7.

What is variable scope?

### 8.

What is variable shadowing?

### 9.

When should I use `var`?

### 10.

When should I use `:=`?

If I cannot explain these concepts clearly, I should solve more problems before moving forward.

---

# 📈 Progress

| Topic               | Status |
| ------------------- | ------ |
| Variables           | ⬜      |
| `var`               | ⬜      |
| `:=`                | ⬜      |
| Reassignment        | ⬜      |
| Multiple variables  | ⬜      |
| Multiple assignment | ⬜      |
| Integer types       | ⬜      |
| Float types         | ⬜      |
| Boolean             | ⬜      |
| String              | ⬜      |
| Complex numbers     | ⬜      |
| Zero values         | ⬜      |
| Type inference      | ⬜      |
| Type conversion     | ⬜      |
| Constants           | ⬜      |
| Typed constants     | ⬜      |
| Untyped constants   | ⬜      |
| Scope               | ⬜      |
| Shadowing           | ⬜      |
| Blank identifier    | ⬜      |
| Problem solving     | ⬜      |
| Debugging           | ⬜      |
| Final challenge     | ⬜      |

---

# 💡 Rules for Myself

### Rule 1

Don't memorize code without understanding it.

### Rule 2

For every new concept, solve at least one problem.

### Rule 3

When I get an error, don't immediately search for the answer.

First ask:

```text
What is the compiler telling me?
```

### Rule 4

Try to solve the problem myself before checking a solution.

### Rule 5

After solving a problem, explain the solution in my own words.

### Rule 6

If I make a mistake, record the mistake.

Mistakes are part of the learning process.

### Rule 7

Don't move to the next topic just because I can copy the syntax.

Move forward when I can **explain + implement + debug** the concept.

---

# 🚀 Day One Definition of Done

Day One is complete when I can:

```text
Understand
    ↓
Declare
    ↓
Initialize
    ↓
Modify
    ↓
Convert
    ↓
Scope
    ↓
Debug
    ↓
Solve Problems
    ↓
Explain
```

without depending heavily on notes.

---

## Final Goal

The goal of this Day One is **not to finish a list of Go variable syntax**.

The goal is to build the habit of thinking like a Go programmer:

> **Understand the problem → identify the required data → choose the correct type → write the simplest solution → run → debug → understand → improve.**

This same problem-solving process will be used throughout the rest of my Go learning journey.
