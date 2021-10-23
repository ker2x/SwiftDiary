# SwiftDiary
i'm learning swift on hackingwithswift

## Day 1

### getting started with stuff

* https://www.hackingwithswift.com/100
* Start XCode, don't create a new project.
* File -> New -> Playground...
* Blank Playground
* shift+enter execute your stuff at the line you use it. Pretty much like Jupyter

### var

* "var" are mutable 

```swift
var greeting = "Hello"
greeting = "Hi"
```

### typesafe

```swift
var greeting = "Hello" // has been guessed by the compiler to be a "string", which is correct
greeting = 42          // This doesn't works because it change the type of "greeting" from string to int

var bignumber = 8_000_000  /// it works and is easier to read, but you can simply do 8000000 too
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

