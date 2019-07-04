# Strings Lab 2

Fork and clone this repo. On your fork, answer and commit the follow questions. When you are finished, submit the link to your repo on Canvas.

## Question 1

You are given a string stored in variable `problem`. Write code so that you print each word of the string on a new line.

```swift
var problem = "split this string into words and print them on separate lines"

let problemArray = problem.split(separator: " ")

for word in problemArray{
print(word)
}
```

Example

Input:
`var problem ="split this string into words and print them on separate lines"`

Output:
```swift
split
this
string
into
words
and
print
them
on
separate
lines
```


## Question 2

Given a string `testString` create a new variable called `condensedString` that has any consecutive spaces in `testString` replaced with a single space.

```swift
let testString = "  How   about      thesespaces  ?  "
//condensedString = " How about thesespaces ? "


let testStringArray = testString.components(separatedBy:" ")
var emptyArray =  [String]()
var empty = ""

for element in testStringArray {
    if element == empty{
        continue
}
    emptyArray.append(element)
}

for i in emptyArray {
    print(i + " ", terminator: "")
}
```


## Question 3

Given a string with multiple words. Reverse the string word by word.

Example:

Sample Input: `"Swift is the best language"`

Sample Output: `"language best the is Swift"`

```swift
let stringStuff = "wow cool nice wow awesome"
var stringStuffArray = stringStuff.components(separatedBy: " ")

for word in stringStuffArray.reversed(){
print(word, terminator: " ")
}
```

## Question 4

Given a string with multiple words. Write code that prints how many of them are palindromes.

Example:

Sample Input: `"danaerys dad cat civic bottle"`

Sample Output: `2`

```swift
let stringStuff = "danaerys dad cat civic bottle"
var stringStuffArray = stringStuff.components(separatedBy: " ")
var container1 = 0
var container2 = ""

for word in stringStuffArray{
    container2.append(word)
    if String(container2.reversed()) == container2{
        container1 += 1
}
    container2 = ""
}
print(container1)
```


## Question 5

You are given a string representing an **attendance record** for a student. The record only contains the following three characters:

`'A' : Absent.`

`'L' : Late.`

`'P' : Present.`

If a student has more than one 'A' or more than 2 continuous 'L's that student should not be rewarded. Print true if student is to be rewarded and False if they shouldn't.

Example:

Sample Input: `"PPALLP"`

Sample Output: `true`

```swift
let record = "PPALLP"
var absent = "A"
var aContainer = 0
var recordArray = Array(record)

for i in recordArray{
    if String(i) == absent {
        aContainer += 1
}
}

if record.contains("LLL") || aContainer > 1 {
    print(false)
} else {
    print(true)
}
```


## Question 6

Given a tuple with two strings. The first string is a **ransom note**, the second string being the characters from a magazine. Determine whether or not you can construct the ransom note using the characters from the magazine.

Each letter from the magazine can only be used once. You can assume all letters are lowercased.

Examples:

Sample Input1: `("a", "b")`

Sample Output1: `False`

Sample Input2: `("aa", "aab")`

Sample Output2: `True`
