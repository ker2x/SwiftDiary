# SwiftDiary
i'm learning swift on hackingwithswift

## Day 1

### getting started with stuff

* https://www.hackingwithswift.com/100
* Start XCode, don't create a new project.
* File -> New -> Playground...
* Blank Playground
* shift+enter execute your stuff at the line you use it. Pretty much like Jupyter

### var & val

* "var" are mutable variable
* "let" are immutable constant
* it advised to use "let", unless you need a variable

```swift
var greeting = "Hello"
greeting = "Hi"
let magic = 42
magic = 43
```

```
error: day1.playground:26:1: error: cannot assign to value: 'magic' is a 'let' constant
magic = 43
^~~~~

day1.playground:25:1: note: change 'let' to 'var' to make it mutable
let magic = 42
^~~
```


### type safety & type annotation

```swift
var greeting = "Hello" // has been guessed by the compiler to be a "string", which is correct (aka : type inference"
greeting = 42          // This doesn't works because it change the type of "greeting" from string to int

var bignumber = 8_000_000  /// it works and is easier to read, but you can simply do 8000000 too
```

If you want to explicitely declare a type : 
```swift
let album: String = "Reputation"
let year: Int = 1989
let height: Double = 1.78
let taylorRocks: Bool = true
```


### strings

* Standard string use "double quote"
* multiline string use triple double quote

```swift
var stuff = """
this is a
multiline
string.
it works
"""
```
The result will be : "this is a\nmultiline\nstring.\nit works"

If you don't want the \n in your string you gotta use \\
```swift
var stuff = """
this is \
a single \
line
"""
```

-> "this is a single line"

### string interpolation

```swift
var score = 85
var str = "Your score was \(score)"
var results = "The test results are here: \(str)"
// -> "The test results are here: Your score was 85"
```

There is a limit to magic however
```swift
var score = 85
var str = "Your score was \(score)"
var results = "The test results are here: \(str)"
// -> "The test results are here: Your score was 85"
score=10
results
// -> "The test results are here: Your score was 85"
```



