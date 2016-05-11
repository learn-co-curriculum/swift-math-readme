# Math



## Learning Objectives - The student should be able to..

* Set variables where the value's are of type `Int` and then perform math operations on those variables, like so:

```swift
let combinedAgesOfFamily = 30 + 29 + 64 + 65
// 188

let myAge = 30
let brothersAge = 29
let momsAge = 64
let dadsAge = 65
let combinedAgesOfFamily2 = myAge + brothersAge + momsAge + dadsAge
// 188
```

* Create variables of type `Double`. 
* Create a function like this on their own:

```swift
func addTwoNumbers(first: Int, second: Int) -> Int {
    return first + second
}
```
* Explain the various amount of math operations
	* Addition (+)
	* Subtraction (-)
	* Multiplication (*)
	* Division (/)
	* Remainder Operator (%)




## What the student can do at this point 

* Create variables and constants
* Is familiar with type annotations, type inference and string interpolation. 
* Has just learned how to create functions with return types.
* The only types they know at this point are String and Int.



## Outline / Notes

*  Build up slowly, first having the student see that you can type 5 + 5 in the playground file and see to the right that it prints 10.
* Then have them type something like 30 / 3
* I like the idea of showing them something like this:

```swift
let numberOfStudents = 30
let numberOfTeachers = 3
let classroomsNeeded = numberOfStudents / numberOfTeachers
```

* When they type something like that, have them option click the variable `numberOfStudents` to remind that this variable is of type Int. Because of this, we can perform math operations on it. Make sure that you provide an example for each operation.
	* Addition (+)
	* Subtraction (-)
	* Multiplication (*)
	* Division (/)
	* Remainder Operator (%)
	
* Have them piece together their new knowledge of these various operators into creating various functions that perform math operations like so. You can structure this how you like (wrote this fast as an example). Talk in depth (again as this would be the second explanation of the return keyword) about return.

```swift
func addTwoNumbers(first: Int, second: Int) -> Int {
    return first + second
}
```
* I think this would be a good idea to introduce to them the `Double` type for the first time. I imagine a student messing around and trying to type something like `25 / 3` and seeing that its output is displaying as `8`.
* Possibly have them type something like the following then asking them to option click the variable to see what its type is (where they will then see that it states `Double`).

```swift
let funNumber = 25.0
```
 

<a href='https://learn.co/lessons/Math' data-visibility='hidden'>View this lesson on Learn.co</a>
