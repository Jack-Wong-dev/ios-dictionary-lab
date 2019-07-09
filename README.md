# Dictionaries lab

Fork and clone this repo. On your fork, answer and commit the follow questions. When you are finished, submit the link to your repo on Canvas.


## Question 1

- Create an instance of a dictionary called `citiesDict` that maps 3 countries to their capital cities.

- Add two more countries to your dictionary.

- Translate at least 3 of the capital names into another language.

```swift

//1A
var citiesDict: [String:String] = ["Japan":"Tokyo","China":"Beijing","Germany":"Berlin"]

//1B
citiesDict["France"] = "Paris"
citiesDict["United States"] = "Washington D.C"

//1C
citiesDict["Japan"] = "東京"
citiesDict["China"] = "北京"
citiesDict["France"] = "パリ"
```

## Question 2

`var someDict:[String:Int] = ["One": 1, "Two": 4, "Three": 9, "Four": 16, "Five": 25]`

- Using `someDict`, add together the values associated with "Three" and "Five" and print the result.

- Add values to the dictionary for the keys "Six" and "Seven".

- Make a key called `productUpToSeven` and set its value equal to the product of all the values.

- Make a key called `sumUpToSix` and set its value equal to the sum of the keys "One", "Two", "Three", "Four", "Five" and "Six".

- Remove the new keys made in the previous two steps

- Add 2 to every value inside of `someDict`.

```swift
//2.1
var someDict:[String:Int] = ["One": 1, "Two": 4, "Three": 9, "Four": 16, "Five": 25]

if let three = someDict["Three"], let five = someDict["Five"]{
    print(three+five) //prints 34
} 

//2.2
someDict["Six"] = 60
someDict["Seven"] = 70

//2.3
var product = 1

for (_,value) in someDict{
    product *= value
}

someDict["productUpToSeven"] = product

//2.4
//someDict["sumUpToSix"]

var sum = 0

for (key,value) in someDict{
    if key == "Seven" || key == "productUpToSeven"{
        continue
    }else{
        sum += value
    }
}
print(sum)

//2.5
someDict.removeValue(forKey: "productUpToSeven")
someDict.removeValue(forKey: "sumUpToSix")

print(someDict)

//2.6
for (key, value) in someDict{
    someDict[key] = value+2
}
print(someDict)

//2.6 another way
for (key, var value) in someDict{
    value += 2
    someDict[key] = value
}
print(someDict)
```


## Question 3

Create a variable that is explicitly typed as a dictionary that maps strings to floating point numbers. Initialize the variable to the data shown in the table below which lists an author name and their comprehensibility score.

| Author Name |	Score |
| :--: | :--: |
| Mark Twain |	8.9 |
| Nathaniel Hawthorne	| 5.1 |
| John Steinbeck	| 2.3 |
| C.S. Lewis | 9.9 |
| Jon Krakauer | 6.1 |

Using the dictionary created in the previous problem, do the following:

- Print out the floating-point score for “John Steinbeck”.

- Add an additional author named “Erik Larson” with an assigned score of 9.2.

- Write an if/else statement that compares the score of John Krakaur with Mark Twain. Print out the name of the author with the highest score.

- Use a for-loop to iterate through the dictionary you created at the beginning of the problem, and print out the content in the form of key: value, one entry per line.


## Question 4

You are given a dictionary code of type [String:String] which has values for all lowercase letters. The code dictionary represents a way to encode a message. For example if code["a"] = "z" and code["b"] = "x" the encoded version if "ababa" will be "zxzxz". You are also given a message which contains only lowercase letters and spaces. Use the `code` dictionary below to encode the message and print it.

```swift
var code = [
    "a" : "b",
    "b" : "c",
    "c" : "d",
    "d" : "e",
    "e" : "f",
    "f" : "g",
    "g" : "h",
    "h" : "i",
    "i" : "j",
    "j" : "k",
    "k" : "l",
    "l" : "m",
    "m" : "n",
    "n" : "o",
    "o" : "p",
    "p" : "q",
    "q" : "r",
    "r" : "s",
    "s" : "t",
    "t" : "u",
    "u" : "v",
    "v" : "w",
    "w" : "x",
    "x" : "y",
    "y" : "z",
    "z" : "a"
]

var message = "hello world"
```
```swift
//Q4
var code = [
"a" : "b",
"b" : "c",
"c" : "d",
"d" : "e",
"e" : "f",
"f" : "g",
"g" : "h",
"h" : "i",
"i" : "j",
"j" : "k",
"k" : "l",
"l" : "m",
"m" : "n",
"n" : "o",
"o" : "p",
"p" : "q",
"q" : "r",
"r" : "s",
"s" : "t",
"t" : "u",
"u" : "v",
"v" : "w",
"w" : "x",
"x" : "y",
"y" : "z",
"z" : "a"
]

var message = "hello world"

//4.1
var messageOutput = String()

for c in message{
    if c == " "{
        messageOutput.append(" ")
    }
    if let encodeC = code[String(c)]{
        messageOutput.append(encodeC)
    }
}; print(messageOutput)

//4.2
var encodedMessage = "uijt nfttbhf jt ibse up sfbe"
var decodedMessage = String()

for char in encodedMessage{
    if char == " "{
        decodedMessage.append(" ")
    }
    for(key, value) in code{
        if String(char) == value{
            decodedMessage.append(key)
        }
    }
}; print(decodedMessage)
```

You are also given an `encodedMessage` which contains only lowercase letters and spaces. Use the `code` dictionary to decode the message and print it.
`var encodedMessage = "uijt nfttbhf jt ibse up sfbe"`


## Question 5

You are given an array of dictionaries. Each dictionary in the array contains exactly 2 keys `“firstName”` and `“lastName”`. Create an array of strings called `firstNames` that contains only the values for `“firstName”` from each dictionary.

```swift
var people: [[String:String]] = [
    [
        "firstName": "Calvin",
        "lastName": "Newton"
    ],
    [
        "firstName": "Garry",
        "lastName": "Mckenzie"
    ],
    [
        "firstName": "Leah",
        "lastName": "Rivera"
    ],
    [
        "firstName": "Sonja",
        "lastName": "Moreno"
    ],
    [
        "firstName": "Noel",
        "lastName": "Bowen"
    ]
]
```

Now, create an array of strings called `fullNames` that contains the values for `“firstName”` and `“lastName”` from the dictionary separated by a space.

```
//Q5
var people: [[String:String]] = [
[
"firstName": "Calvin",
"lastName": "Newton"
],
[
"firstName": "Garry",
"lastName": "Mckenzie"
],
[
"firstName": "Leah",
"lastName": "Rivera"
],
[
"firstName": "Sonja",
"lastName": "Moreno"
],
[
"firstName": "Noel",
"lastName": "Bowen"
]
]

//5.1
var firstNames: [String] = []

for person in people{
    if let fName = person["firstName"]{
        firstNames.append(fName)
    }
}
print(firstNames) //["Calvin", "Garry", "Leah", "Sonja", "Noel"]

//5.2
var fullNames: [String] = []

for person in people{

    if let firstName = person["firstName"], let lastName = person["lastName"]{
        fullNames.append("\(firstName) \(lastName)")
    }
}; print(fullNames)
//["Calvin Newton", "Garry Mckenzie", "Leah Rivera", "Sonja Moreno", "Noel Bowen"]
```

## Question 6

You are given an array of dictionaries. Each dictionary in the array describes the score of a person. Find the person with the best score and print his full name.

```swift
var peopleWithScores: [[String: String]] = [
    [
        "firstName": "Calvin",
        "lastName": "Newton",
        "score": "13"
    ],
    [
        "firstName": "Garry",
        "lastName": "Mckenzie",
        "score": "23"
    ],
    [
        "firstName": "Leah",
        "lastName": "Rivera",
        "score": "10"
    ],
    [
        "firstName": "Sonja",
        "lastName": "Moreno",
        "score": "3"
    ],
    [
        "firstName": "Noel",
        "lastName": "Bowen",
        "score": "16"
    ]
]
```

Print out the dictionary above in the following format:  **full name - score**

```swift
//Q6
var peopleWithScores: [[String: String]] = [
[
"firstName": "Calvin",
"lastName": "Newton",
"score": "13"
],
[
"firstName": "Garry",
"lastName": "Mckenzie",
"score": "23"
],
[
"firstName": "Leah",
"lastName": "Rivera",
"score": "10"
],
[
"firstName": "Sonja",
"lastName": "Moreno",
"score": "3"
],
[
"firstName": "Noel",
"lastName": "Bowen",
"score": "16"
]
]

//6.1 Find the person with the best score and print his full name.
var bestScore = 0
var firstName = ""
var lastName = ""

for person in peopleWithScores{

    if let score = person["score"]{
        if let scoreInt: Int = Int(score){
            if scoreInt > bestScore{
            bestScore = scoreInt
                if let fName = person["firstName"], let lname = person["lastName"]{
                    firstName = fName
                    lastName = lname
                }           
            }
        }
    }
}
print("\(firstName) \(lastName) has the best score: \(bestScore)")

//6.2 Print out the dictionary above in the following format:  **full name - score**

for person in peopleWithScores{

    if let firstName = person["firstName"], let lastName = person["lastName"], let score = person["score"]{

        print("\(firstName) \(lastName) - \(score)")
    }

}

```


## Question 7

`var numbers = [1, 2, 3, 2, 3, 5, 2, 1, 3, 4, 2, 2, 2]`

You are given an array of integers. The frequency of a number is the number of times it appears in the array. Find out the frequency of each one.

Print the numbers in ascending order followed by their frequency.

```swift
//Q7
var numbers = [1, 2, 3, 2, 3, 5, 2, 1, 3, 4, 2, 2, 2]

var numDict: [Int:Int] = [:]

//7.1
for i in numbers{

if numDict.keys.contains(i){
    numDict.updateValue(numDict[i]! + 1, forKey: i)
    }else{
        numDict[i] = 1
    }
}

print(numDict)

//7.2
var array: [Int] = []

for (key,_) in numDict{
    array.append(key)
}
    array.sort()
 // print(array)

for i in 0...array.count-1{
    print("\(array[i]) appears \(numDict[i+1]!) times")
}
```


## Question 8

Print the most common letter in the string below:

`var myString = "We're flooding people with information. We need to feed it through a processor. A human must turn information into intelligence or knowledge. We've tended to forget that no computer will ever ask a new question."`

```swift
var myString = "We're flooding people with information. We need to feed it through a processor. A human must turn information into intelligence or knowledge. We've tended to forget that no computer will ever ask a new question."

var charArray = Array(myString)
var charDict : [Character:Int] = [:]
var alphabet = "abcdefghijklmnopqrstuvwxyz"

for char in charArray{

    if alphabet.contains(char){

        if charDict.keys.contains(char){
            charDict.updateValue(charDict[char]! + 1, forKey: char)
        }else{
        charDict[char] = 1
        }   
    }
}

print(charDict)

var frequency: Int = 0
var letter = String()
for (key, value) in charDict{

if value > frequency{
    frequency = value
    letter = String(key)
}

}
print("Letter '\(letter)' occurs the most: \(frequency) times")
```

## Question 9

Write code that creates a dictionary where the keys are Ints between 0 and 20 inclusive, and each key's value is its cube.

```swift
//Q9 Write code that creates a dictionary where the keys are Ints between 0 and 20 inclusive, and each key's value is its cube.

var dict: [Int:Int] = [:]

for i in 0...20{
    dict[i] = (i*i*i)
}

print(dict)
```


## Question 10

Write code that iterates through `testStates` and prints out whether or not that key is in `statePop`.

```swift
let statePop = ["Alabama": 4.8, "Alaska": 0.7, "Arizona": 6.7, "Arkansas": 3.0]
let testStates = ["California","Arizona", "Alabama", "New Mexico"]
```
```swift
//Q10 Write code that iterates through `testStates` and prints out whether or not that key is in `statePop`.

let statePop = ["Alabama": 4.8, "Alaska": 0.7, "Arizona": 6.7, "Arkansas": 3.0]
let testStates = ["California","Arizona", "Alabama", "New Mexico"]

for state in testStates{
    if statePop.keys.contains(state){
        print("\(state) exists in statePop")
    }else{
    print("\(state) doesn't exist in statePop")
    }
}

```


## Question 11

You are given the dictionary `deposits`, which maps a persons name to an array of deposits that have been made to their account.

a) Write code to to print the name and total amount deposited of the person who recieved the most money.

b) Create an array called `stolenCents`, iterate over deposits for each person and steal their cents! ... like Office Space or Superman 3. Calculate the decimal part of each value, add it to the `stolenCents` array and round down the value in the dict.

c) How much money did you steal?

```swift
var deposits: [String: [Double]] = [
 "Williams" : [300.65, 270.45, 24.70, 52.00, 99.99],
 "Cooper" : [200.56, 55.00, 600.78, 305.15, 410.76, 35.00],
 "Davies" : [400.98, 56.98, 300.00],
 "Clark" : [555.23, 45.67, 99.95, 80.76, 56.99, 46.50, 265.70],
 "Johnson" : [12.56, 300.00, 640.50, 255.60, 26.88]
]
```
```swift
//Q11
var deposits: [String: [Double]] = [
"Williams" : [300.65, 270.45, 24.70, 52.00, 99.99],
"Cooper" : [200.56, 55.00, 600.78, 305.15, 410.76, 35.00],
"Davies" : [400.98, 56.98, 300.00],
"Clark" : [555.23, 45.67, 99.95, 80.76, 56.99, 46.50, 265.70],
"Johnson" : [12.56, 300.00, 640.50, 255.60, 26.88]
]

//11a
var mostMoney: Double = 0.0
var person = String()

for (key,value) in deposits{
    var total: Double = 0.0

    for i in value{
        total += i
    }

    if total > mostMoney{
        mostMoney = total
        person = key
    }
}; print("\(person) has the most money: \(mostMoney)")

//11b
var stolenCents: [Double] = []

for (_,value) in deposits{

for i in value{
    let difference = i - floor(i)
        stolenCents.append(difference)
    }
}
//print(stolenCents)
var totalCentsStolen: Double = 0.0

for cent in stolenCents{
    totalCentsStolen += cent
}
print(stolenCents)

//11c
print("I stole a total of \(Int(floor(totalCentsStolen*100))) cents")
```


## Question 12

Print the second most common letter in the string below:

`var myString = "We're flooding people with information. We need to feed it through a processor. A human must turn information into intelligence or knowledge. We've tended to forget that no computer will ever ask a new question."`

```swift

var myString = "We're flooding people with information. We need to feed it through a processor. A human must turn information into intelligence or knowledge. We've tended to forget that no computer will ever ask a new question."

var charArray = Array(myString)
var charDict : [Character:Int] = [:]
var alphabet = "abcdefghijklmnopqrstuvwxyz"

for char in charArray{

    if alphabet.contains(char){

        if charDict.keys.contains(char){
            charDict.updateValue(charDict[char]! + 1, forKey: char)
        }
        else{
            charDict[char] = 1
        }
    }
}

print(charDict)

var frequency: Int = 0
var frequency2: Int = 0
var letter = String()
var secondLetter = String()
for (key, value) in charDict{

    if value > frequency{
        frequency2 = frequency
        frequency = value
        secondLetter = letter
        letter = String(key)
    }
}
print("Letter '\(letter)' occurs the most: \(frequency) times")
print("Letter '\(secondLetter)' occurs the second most: \(frequency2) times")
```

## Question 13

Given the below 4 arrays of Ints,

a) create a new array, sorted in ascending order, that contains all the values without duplicates.

b) create another new array that contains unique values that appear in all 4 arrays.

```swift
let arr1 = [2, 4, 5, 6, 8, 10, 12]
let arr2 = [1, 2, 3, 4, 5, 6]
let arr3 = [5, 6, 7, 8, 9, 10, 11, 12]
let arr4 = [1, 3, 4, 5, 6, 7, 9]
```
```swift

//Q13
let arr1 = [2, 4, 5, 6, 8, 10, 12]
let arr2 = [1, 2, 3, 4, 5, 6]
let arr3 = [5, 6, 7, 8, 9, 10, 11, 12]
let arr4 = [1, 3, 4, 5, 6, 7, 9]

//13a
var arrAll: [Int] = []

var numDict: [Int:Int] = [:]

func addition(array: [Int]) -> (){
    for i in array{
        if numDict.keys.contains(i){
            numDict.updateValue(numDict[i]! + 1, forKey: i)
        }else{
            numDict[i] = 1
        }
    }
}
addition(array: arr1)
addition(array: arr2)
addition(array: arr3)
addition(array: arr4)

//print(numDict)

for (key,_) in numDict{
    arrAll.append(key)
}
//print(arrAll)

//13b create another new array that contains unique values that appear in all 4 arrays.

var newArray: [Int] = []

func uniqueForAll4Arrays(array: [Int]){
    for i in array{
        if numDict.keys.contains(i){
        newArray.append(i)
        }
    }
}

for (key,_) in numDict{

    if arr1.contains(key)&&arr2.contains(key)&&arr3.contains(key)&&arr4.contains(key){
        newArray.append(key)
    }

}

print(newArray)
```


## Question 14

Given the following exert from the Declaration of Independence, find the most frequent word that is longer than 5 characters.

 - use `components(separatedBy:)` to break up the string into an array.

 - use `CharacterSet.punctuationCharacters` in union with any other characters you don't want in your array, like spaces and new lines.

 ```swift
let declarationOfIndependence = """
When in the Course of human events, it becomes necessary for one people to dissolve the
political bands which have connected them with another, and to assume among the powers of the
earth, the separate and equal station to which the Laws of Nature and of Nature's God entitle
them, a decent respect to the opinions of mankind requires that they should declare the causes
which impel them to the separation.

We hold these truths to be self-evident, that all men are created equal, that they are endowed by
their Creator with certain unalienable Rights, that among these are Life, Liberty and the pursuit
of Happiness. That to secure these rights, Governments are instituted among Men, deriving
their just powers from the consent of the governed, That whenever any Form of Government
becomes destructive of these ends, it is the Right of the People to alter or to abolish it, and to
institute new Government, laying its foundation on such principles and organizing its powers in
such form, as to them shall seem most likely to effect their Safety and Happiness. Prudence,
indeed, will dictate that Governments long established should not be changed for light and
transient causes; and accordingly all experience hath shewn, that mankind are more disposed to
suffer, while evils are sufferable, than to right themselves by abolishing the forms to which they
are accustomed. But when a long train of abuses and usurpations, pursuing invariably the same
Object evinces a design to reduce them under absolute Despotism, it is their right, it is their duty,
to throw off such Government, and to provide new Guards for their future security. Such has
been the patient sufferance of these Colonies; and such is now the necessity which constrains
them to alter their former Systems of Government. The history of the present King of Great
Britain is a history of repeated injuries and usurpations, all having in direct object the
establishment of an absolute Tyranny over these States. To prove this, let Facts be submitted to a
candid world.
"""
```
```swift

let declarationOfIndependence = """
When in the Course of human events, it becomes necessary for one people to dissolve the
political bands which have connected them with another, and to assume among the powers of the
earth, the separate and equal station to which the Laws of Nature and of Nature's God entitle
them, a decent respect to the opinions of mankind requires that they should declare the causes
which impel them to the separation.

We hold these truths to be self-evident, that all men are created equal, that they are endowed by
their Creator with certain unalienable Rights, that among these are Life, Liberty and the pursuit
of Happiness. That to secure these rights, Governments are instituted among Men, deriving
their just powers from the consent of the governed, That whenever any Form of Government
becomes destructive of these ends, it is the Right of the People to alter or to abolish it, and to
institute new Government, laying its foundation on such principles and organizing its powers in
such form, as to them shall seem most likely to effect their Safety and Happiness. Prudence,
indeed, will dictate that Governments long established should not be changed for light and
transient causes; and accordingly all experience hath shewn, that mankind are more disposed to
suffer, while evils are sufferable, than to right themselves by abolishing the forms to which they
are accustomed. But when a long train of abuses and usurpations, pursuing invariably the same
Object evinces a design to reduce them under absolute Despotism, it is their right, it is their duty,
to throw off such Government, and to provide new Guards for their future security. Such has
been the patient sufferance of these Colonies; and such is now the necessity which constrains
them to alter their former Systems of Government. The history of the present King of Great
Britain is a history of repeated injuries and usurpations, all having in direct object the
establishment of an absolute Tyranny over these States. To prove this, let Facts be submitted to a
candid world.
"""

var array = declarationOfIndependence.components(separatedBy: CharacterSet.punctuationCharacters).joined().components(separatedBy: .whitespacesAndNewlines)

//print(array)

var dictionary: [String:Int] = [:]

for word in array{

    if dictionary.keys.contains(word){
        dictionary.updateValue(dictionary[word]! + 1, forKey: word)
    }else{
    dictionary[word] = 1
    }

}

//print(dictionary)

var highestFrequency = 0
var wordAppearsMost = String()

for (key, value) in dictionary where key.count > 5{
    if (value > highestFrequency){
        highestFrequency = value
        wordAppearsMost = key
    }
}

print("'\(wordAppearsMost)' is the word (more than 5 characters) that appears the most: \(highestFrequency) times")
```
