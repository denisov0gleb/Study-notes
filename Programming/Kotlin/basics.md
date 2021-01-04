# Kotlin basics #

Created 10.12.20 by **DGL**

Modified 11.12.20 by **DGL**

[Source](https://kotlinlang.org/docs/reference/basic-types.html)

# Table of Content: #
<!-- vim-markdown-toc GFM -->

1. [Numbers](#numbers)
	1. [Integer numbers](#integer-numbers)
	1. [Floating point numbers](#floating-point-numbers)
	1. [NaN](#nan)
	1. [Other information about numbers](#other-information-about-numbers)
1. [Operations with numbers](#operations-with-numbers)
	1. [Floating point numbers comparison](#floating-point-numbers-comparison)
	1. [Convertion between numbers](#convertion-between-numbers)
1. [Booleans](#booleans)
1. [Characters](#characters)
	1. [Convertion Char to Integer](#convertion-char-to-integer)
1. [Arrays](#arrays)
	1. [Create array](#create-array)
	1. [Primitive type arrays](#primitive-type-arrays)
1. [Strings](#strings)
	1. [Escaped strings](#escaped-strings)
	1. [Raw strings](#raw-strings)
1. [Packages](#packages)
	1. [Default imports](#default-imports)
	1. [Imports](#imports)
1. [Flow control](#flow-control)
	1. [If statement](#if-statement)
	1. [When statement](#when-statement)
	1. [For loops](#for-loops)
	1. [While loops](#while-loops)

<!-- vim-markdown-toc -->

____
> **Everything is an object, so we can call member functions and properties on any variable.**
____

## Numbers ##
[Table of Content](#table-of-content)

### Integer numbers ###

| Type  | Size (bits) | Min value       | Max value          |
| ---   | ---         | ---             | ---                |
| Byte  | 8           | -128            | 127                |
| Short | 16          | -32768          | 32767              |
| Int   | 32          | -2<sup>31</sup> | 2<sup>31</sup> - 1 |
| Long  | 64          | -2<sup>63</sup> | 2<sup>63</sup> - 1 |


By default integers are used:

```kotlin
val one = 1 // Int
val threeBillion = 3000000000 // Long
val oneLong = 1L // Long
val oneByte: Byte = 1 // Byte
```

### Floating point numbers ###

| Type   | Size (bits) | Significant bits | Exponent bits | Decimal digits |
| ---    | ---         | ---              | ---           | ---            |
| Float  | 32          | 24               | 8             | 6-7            |
| Double | 64          | 53               | 11            | 15-16          |


By default Double are used:

```kotlin
val pi = 3.14 //Double
val e = 2.7182 // Double
val eFloat = 2.7182f // Float
val eFloat = 2.7182F // Float
```

### NaN ###

* `NaN` is equal to itself
* `NaN` in greater than any element including **POSITIVE_INFINITY**
* `-0.0` in less than `0.0`


### Other information about numbers ###

*underscores* can be used to make numbers more readable:

```kotlin
val oneMillion = 1_000_000
val creditCardNumber = 1234_5678_9012L
```

## Operations with numbers ##
[Table of Content](#table-of-content)

Usual operations:

`+ - * / %`

**Division operation always returns floor integer result if something is divided by integer!**

```kotlin
val x = 5 / 2 // x = 2
val x = 5L / 2 // x = 2L
val x = 5 / 2.toDouble() // x = 2.5 (double)
```

### Floating point numbers comparison ###

* `a == b` and `a != b`
* `a < b`m `a > b`, `a <= b`, `a >= b`
* range: `a..b`, `x in a..b`, `x !in a..b`

### Convertion between numbers ###

**There are no automatical conversion between types!!! (As in C)**

Special conversion for every type:

* toByte()
 
* toShort()
 
* toInt()
 
* toLong()
 
* toFloat()
 
* toDouble()
 
* toChar()

```kotlin
val b: Byte = 1
val i: Int = b.toInt()
```

## Booleans ##

[Table of Content](#table-of-content)

`true` and `false`

Usual boolean orepations:
* `||` lazy disjuntion
* `&&` lazy conjunction
* `!` negation


## Characters ##
[Table of Content](#table-of-content)

`Char` isn't a number.

Defined in two single quotes: `'i'` or in Unicode: `'\uFF00'`.


### Convertion Char to Integer ###

```kotlin
fun decimalDigitValue(c: Char): Int
{
	if (c !in '0'..'9')
		throw IllegalArgumentException("Out of digital range!")
	return c.toInt() - '0'.toInt()
}
```

## Arrays ##
[Table of Content](#table-of-content)

`Array` class with `get` and `set` functions.

`Array` cannot change it type!

Counting starts from `0`.

### Create array ###

Use `arrayOf()` library function:

```kotlin
val arr1 = arrayOf(1, 2, 3) // arr1 = [1, 2, 3]
```

Or use `Array` constructor:

```kotlin
val arr2 = Array(5) { i -> (i * i),toString() }
arr2.forEach ( println(it) }
```

### Primitive type arrays ###

`ByteArray`, `ShortArray`, `IntArray` and so on. Each has it's own factory.

```kotlin
val x: IntArray = intArrayOf(1, 2, 3)
x[0] = x[1] + x[2]

val arr1 = IntArray(5) // array of int of size 5 with values [0, 0, 0, 0, 0]

val arr2 = IntArray(5) {42} // array of int of size 5 [42, 42, 42, 42, 42]

val arr3 = IntArray(5) {it * 1} // Initialize array using lambda [0, 1, 2, 3, 4]
```

## Strings ##
[Table of Content](#table-of-content)

Strings are immutable!


```kotlin
// Iterate over string:
for (c in str)
{
	println(c)
}
```

```language
// Concatenate strings with '+'
val s = "abc" + 1

println(s + "def")
```

Templates in strings:

```kotlin
val i = 10
println("i = $i") // => "i = 10"

val s = "abc"
println("$s.length is ${s.length}") // => "abc.length is 3"
```


### Escaped strings ###

**Escaped strings** may have escaped characters:

```kotlin
val s = "Hello, world!\n"
```

### Raw strings ###

**Raw string** can contain newlines and any characters:

```kotlin
val text = """
	for (c in "foo")
		print(c)
		"""
```

You can remove leading whitespace with `trimMargin()` function:

```kotlin
val text = """
	|Tell me and I forget.
	|Teach me and I remember.
	|Involve me and I learn.
	|(Benjamin Franklin)
	""".trimMargin()
```

`|` is default character as margin prefix, but other symbols can be: `trimMargin(">")`.


## Packages ##
[Table of Content](#table-of-content)

```kotlin
package org.example

fun printMessage() { /* */ }
class Message { /* */ }
```
### Default imports ###

* kotlin.\*
* kotlin.annotation.\*
* kotlin.collections.\*
* kotlin.comparisons.\*
* kotlin.io.\*
* kotlin.ranges.\*
* kotlin.sequences.\*
* kotlin.text.\*

### Imports ###

```kotlin
import org.example.Message

import org.example.*

import org.test.Message as testMessage
```

## Flow control ##
[Table of Content](#table-of-content)

Typical flow control (`if` and `else`, `when` (= `switch`), `while` and `do ... while`, `break`,
`continue`). 

### If statement ###

```kotlin
var max = a
if (a < b) max = b

var max: Int
if (a > b)
{
	max = a
}
else
{
	max = b
}

val max = if (a > b) a else b
```

### When statement ###

Like `switch` in C language:

```kotlin
when(x)
{
	1 -> print("x == 1")
	2 -> print("x == 2")
	else -> {
		print("x is neither 1 nor 2")
	}
}
```


Use `else` if not found:

```kotlin
when (x)
{
	0, 1 -> print("x == 0 or x == 1")
	else -> print("otherwise")
}
```


We can check value for being `in` or `!in` a range or collection:

```kotlin
when (x) {
	in 1..10 -> print("x is in the range")
	in validNumbers -> print("x is valid")
	!in 10..20 -> print("x is outside the range")
	else -> print("none of the above")
}
```

### For loops ###

```kotlin
for (item in collection) print(item)

for (item: Int in ints)
{
	// ...
}
```


`for` in collections:

```kotlin
for (i in 1..3)
{
	println(i)
}

for (i in 6 downTo 0 step 2)
{
	println(i)
}
```

### While loops ###

`while` and `do ... while` as usual:

```kotlin
while (x > 0)
{
	x--
}

do
{
	val y = retrieveData()
}
while (y != null) // y is visible here!
```


