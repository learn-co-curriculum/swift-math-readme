# Maths

## Objectives

1. Perform mathematical operations on integer values
1. Describe the `Double` data type
1. Learn how to create functions performing mathematical operations
1. Introduce the full set of mathematical operators

## Arithmetic operators

You have already learned about the type `Int` which can be used to create variables and constants holding single integer numbers:

```swift
let myAge = 30
let brothersAge = 29
let momsAge = 64
let dadsAge = 65
```

Commonly, once we have numbers, we want to perform mathematical operations on them, for example summing them up. For doing this, Swift provides *operators*, special symbols that you use to check, combine or change one or more values. 

The symbols used are similar to the ones you would use on paper, like `+` for performing additions:

```swift
let sum = 5 + 5 // 10
```

We can also sum up more than two values by chaining them and use variables as the *operands* (the subjects of an *operand*):

```swift
let combinedAgeOfFamily = myAge + brothersAge + momsAge + dadsAge // 188
```

Subtraction works similarly, using the `-` operator:

```swift
let ageDifference = myAge - brothersAge // 1
```

You should try typing those expressions in a Playground, just to get a feel for them. You already learned about type inference in an earlier lesson and also about type annotations to explicitly specify types to the compiler. In case you want to see what the infered type of an expression or a variable is, you can Option-Click on it inside the Playground and will see the result in a popup inside the Playground.

Two numbers can be multiplied using `*`:

```swift
let numberOfPeoplePerHouse = 5
let numberOfHouses = 120
let villagePopulation = numberOfPeoplePerHouse * numberOfHouses // 600
```

For dividing two numbers, there is the `/` operator, which can be used like this:

```swift
let numberOfStudents = 30
let numberOfTeachers = 3
let classroomsNeeded = numberOfStudents / numberOfTeachers // 10
```

Now try out what happens if the result ends up in a fraction, e.g. by using 25 as `numberOfStudents`. You will notice that the result will still be an integer value:

```swift
let numberOfStudents = 25
let numberOfTeachers = 3
let classroomsNeeded = numberOfStudents / numberOfTeachers // 8
```

You can determine the remainder of the same calculation using the `%` operator, revealing again that the result should be fractional:

```swift
let numberOfStudentsWithoutAClassroom = numberOfStudents % numberOfTeachers // 1
```

## Floating point numbers

We need to do something to help that poor student who does not have a classroom. Let's change the value of `numberOfStudents` again to 25.0 and inspect the type inside the Playground.

You will see that the type changed to `Double`, but also that there is now an error in the code, which will read somewhat like this:

```
note: overloads for '/' exist with these partially matching parameter lists: (Int, Int), (Double, Double)
```

The reason for this is Swift's focus on *type safety*, which means in this case that no automatic conversion between integer and floating-point numbers is performed. Since the `/` operator only works on two `Double` values or two `Int` values, there is no matching operator that can be used here. Can you think of a way to fix this?

We can fix this with *type annotations*, like this:

```swift
let numberOfStudents = 25.0
let numberOfTeachers: Double = 3
let classroomsNeeded = numberOfStudents / numberOfTeachers // 8.3333333333333339
```

or alternatively perform an explicit *type conversion*:

```swift 
let numberOfStudents = 25.0
let numberOfTeachers = Double(3)
let classroomsNeeded = numberOfStudents / numberOfTeachers // 8.3333333333333339
```

Finally, we could have also solved the initial problem by making use of *type inference* and directly specify the result type we are expecting from our division:

```swift
let classroomsNeeded: Double = 25 / 3 // 8.3333333333333339
```

However, type inference is performed for each line individually, so it is not possible for the compiler to change the type of `numberOfStudents` or `numberOfTeachers` after the fact in order to fulfill an explicit type annotation on our `classroomsNeeded` result.

Note: Floating-point types can represent a much wider range of values than integer types, and can store numbers that are much larger or smaller than can be stored in an `Int`. Because of how those numbers are stored internally, they don't have a fixed range of values, but rather a number of decimal digits they can represent with precision, in the case of `Double` this is at least 15 decimal digits.

## Creating your own arithmetic functions

You already learned about declaring functions and returning values from them in a previous lesson:

```swift
func twentyThree() -> Int {
	return 23
}

twentyThree() // 23
```

Use this and your newly acquired knowledge about mathematical operators to create a function that adds two values.

The function you have created should look somewhat like this:

```swift
func addNumber(first: Int, to second: Int) -> Int {
    return first + second
}

let result = addNumber(5, to: 3) // 8
```

Note that we are giving the second parameter of the function two labels, an *external* one (`to`) and an *internal* one (`second`). This makes it possible to make the calling code more readable, almost feeling like a sentence, while also being able to easily distinguish the parameters inside the body of the function.

The `return` statement is used to exit a function and return its value to the expression calling it. You can think of it as a way to extract a piece of code into its own environment and giving it a descriptive name, while hiding the details. Calling a function can be seen as inserting that piece of code back, so another way to express the code block above is:


```swift
let result = 5 + 3 // 8
```

In this case, extracting the code into a function did not make much sense, because our code became neither more descriptive, nor did we make it shorter.

Try to write another function, which computes the area of a circle (two times Pi times r²).

The function you have created should look somewhat like this:

```swift
func areaOfCircleWithRadius(radius: Double) -> Double {
	let pi = 3.14159
	let area = 2 * pi  * r * r
	return area
}

let radius = 7.0
let area = areaOfCircleWithRadius(radius) // 307.87582
```

In this case, the function makes a lot of sense, because we have abstracted the calculation away and gave it a descriptive name. In the future, we only need to remember the function's name (or autocomplete it :)), but do not have to know how exactly the result is calculated.

<a href='https://learn.co/lessons/Math' data-visibility='hidden'>View this lesson on Learn.co</a>
