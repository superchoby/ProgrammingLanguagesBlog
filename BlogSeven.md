# Pattern Matching vs If Statements

Pattern matching is a great coding concept that is in Haskell and comparisons can be made between pattern matching and if statements. 
When it comes to determining the behavior of functions, they are especially similar and let's take a look and compare them.

## The Example (Haskell and Python)
```hs
subtr O n = O
subtr n O = n
subtr (S n) (S m) = subtr n m
```
```py
def subtr(one, two):
  if one == 0 and two != 0:
    return 0
  elif one != 0 and n == 0:
    return one
  else:
    return subtr(one - 1, two - 1)
```

Here is an example of a subtraction function that only deals with 0 and positive numbers. The first uses pattern matching to determine what to return while the latter
uses if statements. 

## The usage of conditionals
The Haskell program does not use booleans while the Python program uses them to evaluate which value to return. The haskell program does compare values to determine which to run however it is not directly using booleans.

## The handling of the situation where the function needs to be called again
When the function needs to be called again, in the scenario where both the arguments are greater than 0, the way the arguments are handled is slightly different. Haskell is able to automatically subtract one from the parameter and set it equal to a new variable however in Python you have to explicity declare a statement that subtracts one from the argument and you either have to subtract it yourself and pass it as an argument or set it equal to a variable and pass that variable in the function call.


These are some of the differences between pattern matching and if else statements. I encourage you to do more functional programming in order to strengthen your knowledge of this great tool called pattern matching.
