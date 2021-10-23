# SwiftDiary
* i'm learning swift on hackingwithswift
* https://www.hackingwithswift.com/100


## Day 1

### getting started with stuff

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

## day 2

### array

* array are, of course, 0 indexed
* it crash if you're out of bound


```swift
let beatles = ["john", "paul", "george", "ringo"]
beatles[0] #-> "john"

// type annotation 
// Shortened forms are preferred
var emptyDoubles: [Double] = []

// The full type name is also allowed
var emptyFloats: Array<Float> = Array()
```

If you need an array that is preinitialized with a fixed number of default values, use the Array(repeating:count:) initializer.
```swift
var digitCounts = Array(repeating: 0, count: 10)
#-> [0, 0, 0, 0, 0, 0, 0, 0, 0, 0]
```

### sets

Sets are collections of values just like arrays, except they have two differences:
* Items aren’t stored in any order; they are stored in what is effectively a random order.
* No item can appear twice in a set; all items must be unique.
* If you try to insert a duplicate item into a set, the duplicates get ignored. 

```swift
let colors = Set(["red", "green", "blue"])
# type annotation
let ingredients: Set = ["cocoa beans", "sugar", "cocoa butter", "salt"]
```


### tuples

Tuples allow you to store several values together in a single value. That might sound like arrays, but tuples are different:
* You can’t add or remove items from a tuple; they are fixed in size.
* You can’t change the type of items in a tuple; they always have the same types they were created with.
* You can access items in a tuple using numerical positions or by naming them, but Swift won’t let you read numbers or names that don’t exist.

```swift
var name = (first: "Taylor", last: "Swift")
name.0 #-> Tayloar
name.first #-> Taylot
```


### dictonnaries

a K/V type

```swift
let heights = [
    "Taylor Swift": 1.78,
    "Ed Sheeran": 1.73
]
heights["Taylor Swift"] #-> 1.78

//Type annotation
let heights: [String: Double] = [
    "Taylor Swift": 1.78,
    "Ed Sheeran": 1.73
]
```

You can also specify a default value if the key doesn't exist
```swift
let favoriteIceCream = [
    "Paul": "Chocolate",
    "Sophie": "Vanilla"
]
favoriteIceCream["Charlotte", default: "Unknown"]
//-> "Unknown"
```

### enums

define an enum that stores various kinds of activities:

```swift
enum Activity {
    case bored
    case running
    case talking
    case singing
}

//That lets us say that someone is talking, but we don’t know what they are talking about, 
// or we can know that someone is running, but we don’t know where they are running to.
// Enum associated values let us add those additional details:

enum Activity {
    case bored
    case running(destination: String)
    case talking(topic: String)
    case singing(volume: Int)
}

//Now we can be more precise – we can say that someone is talking about football:

let talking = Activity.talking(topic: "football")
```


