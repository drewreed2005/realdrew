---
layout: page
title: Vocabulary
permalink: /vocab/
---

(Code cells are in Python.)

### [3.1 (Variables and Assignments)]({{site.baseurl}}/sections1-2notes/#Variables-and-Assignments)

Variables: abstractions within programs which represent a value

```
variable = 3 ['3' can be any valid value]
```

Booleans: a binary type of data which can be set to "True" or "False (can be output as a result of equality/inequality statements)

```
running = True
while running:
    process() #booleans can be used for things like this
```

### [3.2 (Data Abstraction)]({{site.baseurl}}/sections1-2notes/#Data-Abstraction)

List: a set of elements organized in a specific order (can be infinitely long)

```
list = [2, 3, True, "String", 3.14159] #can contain all sorts of data
```

Element: a unique, individual value in a list

```
list[0] == 2 #(output: true); 2 is the 0th (first) element in 'list'
```

Data Abstraction: the storage of data in abstract variables

```
winningscore = 100 #for a game where scoring 100 makes you win
```

### [3.3 (Mathematical Expressions)]({{site.baseurl}}/sections3-4notes/#3.3-Mathematical-Expressions)

Algorithm: a set of actions with a set of rules that tells a program what to do

```
def add_2(num): #it's important to name the algorithm (abstraction)
    return (num += 2)
```

### [3.4 (Strings)]({{site.baseurl}}/sections3-4notes/#3.4-Strings(Show-video-1))

Concatenation: combining strings using `+` (or sometimes `,`)

```
greeting = "Hello, " + "world!"
print(greeting) #(output: Hello, world!)
greeting2 = "How", "are", "you?"
print(greeting2) #(output: How are you?)
```

Length: the amount of elements in a list, characters in a string, etc. depending on the source in question

```
list = [1, 2, 3]
print(len(list)) #(output: 3)
string = "Hello"
print(len(string)) #(output: 5)
```

Substring: individual characters within a string

```
string = "word"
print(string[1]) #(output: o, the substring at index '1')
```

### [3.5 (Boolean Expressions)]({{site.baseurl}}/sections5-7notes/#3.5-Boolean-Expresssions)

(See "Booleans" in 3.1 vocabulary)

Logical operators:  `and`, `or` and `not`; operators that compare the state of multiple things

```
raining = True
cold = False
def rain_check():
    if raining and cold: #only active if raining AND cold
        wear("Rain Jacket")
def shorts_check():
    if not raining: #only active if raining == False
        wear("Shorts")
```

### [3.6 (Conditionals)]({{site.baseurl}}/sections5-7notes/#3.6-Conditionals)

(See "Algorithm" in 3.3 vocabulary)

Selection: the process that determines which parts of an algoritm is being executed based on a condition that is true or false

```
def hot_check():
    if temp > 90: #this part is running when (temp > 90) is True
        return True
    else: #this part runs otherwise
        return False
```

Conditional: reliant upon a certain variable condition to occur

```
#see like all of the functions above
```

### [3.7 (Nested Conditional Statements)]({{site.baseurl}}/sections5-7notes/#3.7-Nested-Conditional-Statements)

(See "Conditional" in 3.6 vocabulary)

Nested conditionals: conditionals within conditionals

```
def thing_check(this, that)
    if this:
        if that: #two conditionals????? INSIDE each other??????
            return "WOW!"
        else:
            return "Cool..."
    else:
        return "Not cool..."
```

### [3.9 (Developing Algorithms)]({{site.baseurl}}/sections9&11notes/#Developing-Algothims-(Python))

(See "Algorithm" in 3.3 vocabulary)

(See "Booleans" in 3.1 vocabulary)

(See "Conditional" in 3.6 vocabulary)

### [3.11 (Searching)]({{site.baseurl}}/sections9&11notes/#Searching-Introduction)

Sequential Search: a search method that requires a program to look at each instance in a series of information in order (which is generally inefficient compared to Binary Search)

```
def sequentialSearch(arr, target): #see this in the lesson itself
    N = len(arr)
    for i in range(N):
        if arr[i] == target:
            return i
            function call
    return -1
```

Binary Search: a search method that starts in the middle of a series of information, compares the information found to the target, then recenters with half of the remaining data cut off

def binarySearch(array, target):
    low = 0
    high = len(array)-1
    while high >= low:
        mid = (high + low) // 2 #floor division, see below
        if array[mid] == target:
            return mid
        elif array[mid] > target:
            high = mid-1
        else:
            low = mid+1
    return False   

Floor division: division that automatically rounds down non-integer quotients

```
mid = (high + low) // 2 #floor division, rounds it down to the nearest int
```

### [3.12 Calling Procedures]({{site.baseurl}}/sections12-13notes/#Calling-Procedures-(Python))

Procedure: a named group of programming instructions that may have parameters and return values

```
def procedure(parameter): #name of procedure and parameter
    if this: #conditional
        return "Uh-huh" #returned value
    else:
        return "Uh-uh-uh"
```

Parameters: input values of a procedure, specified by arguments

```
add_2(5) #returns 7 because parameter was 5
```

Arguments: specify the values of the parameters when a procedure is called

```
add_2(5) #specifying 7 based on the parameter 5
```

### [3.13 Developing Procedures]({{site.baseurl}}/sections12-13notes/#Developing-Procedures)

Modularity: separating a program's functions into independent pieces or blocks, each containing all the parts needed to execute a single aspect of the functionality

```
def brush_teeth():
    toothpaste() #various functions specifying the rest of the process
    brush("bottom")
    brush("top")
    brush("tongue")
    floss()
    return "Teeth are squeaky-clean!"
```

Procedural Abstraction: providing a name for a process that allows a procedure to be used only knowing WHAT it does, not HOW it does it

```
brush_teeth() #take a wild guess at what this does...thanks, procedural abstraction
```

### [3.14 Libraries]({{site.baseurl}}/sections14-15notes/#Libraries)

Library: a digital code library full of methods that serve specific purposes, imported through packages

```
import pygame
```

Packages: collections of methods from libraries

```
random.randint(1, 10)
random.choice(['Red', 'Blue'])
#various other methods provided in the packages
```

Documentation: written explanations of the use of various methods in libraries (Example: here's [Pygame's documentation](https://www.pygame.org/docs/).)

### [3.15 Random Values]({{site.baseurl}}/sections14-15notes/#Random-Values)

(no new vocabulary)

### [3.16 Simulations]({{site.baseurl}}/section16notes/)

Simulations: abstractions that mimic more complex objects or phenomena from the real world. (The purpose is drawing inferences without the contraints of the real world.)

```
from random import * #we need this for the example
def lottery():
    draw = randint(1, 13983816)
    lucky = randint(1, 13983816)
    if draw == lucky:
        return "You won $100,000,000!!!!!!!!!"
    else:
        return "You're a sucker who lost. :("
```

Variance: random chance, simulated through random number generation in simulations.

```
import random #it's all in here, see the lottery sim above
```

### [3.17 Algorithmic Efficiency]({{site.baseurl}}/sections17-18notes/#3.17-Algorithmic-Efficiency)

(Also found within the notes linked above)

Problem: A general description of a task that can or cannot be solved algorithmically

Decision Problem: A problem with a yes or no answer

Organization Problem: A problem with a goal of finding the best answer

```
#problem: is the user input more than 3?
num = int(input("Input a number"))
if num > 3:
    print("Input is greater than 3!")
else:
    print("Input is not greater than 3.")

#this is a decision problem
```

Efficiency: Amount of computing needed to solve a problem

Polynomial Efficiency (Good): More work takes a proportional amount of time (1 job is +2 time)

Exponential Efficiency (Bad): More work takes an exponential amount more time (1 job is 2x time)

Heuristic Approach: When optimal solutions are inefficient, look for a possibly optimal solution that is more efficient

```
"""
For the finding the fastest route homework,
it was best to have it look through the data
procedurally rather than check every possible
route for the most efficient one.
"""
```

Decidable Problem: A decision problem that has a clear solution that will always make a correct output

Undecidable Problem: A decision problem with no solution that is not guarenteed to produce the correct output

```
num = int("Hello")
if num > 3:
    return "Yep"

#would return an error
```

### [3.18 Undecidable Problems]({{site.baseurl}}/sections17-18notes/#3.18-Undecidable-Problems)

The Halting Problem: the problem of determining whether or not a program should stop trying to run if it will end up running forever

(see notes for code example)