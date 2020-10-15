# Valid Parentheses Algorithm in Haskell
There is a very popular algorithm question that is often suggested you study when it comes to coding interviews and we even had an assignment in
the Data Structures course here at Chapman that requires us to develop an algorithm very similar to it. It can be viewed here 
https://leetcode.com/problems/valid-parentheses/. Essentially what the algorithm does is check if a string of brackets, {}[](), is valid. Valid means that
all open brackets are closed by the same type of brackets and that they are clsoed in the correct order. I have tackled this problem numerous times in 
Python but this time I would like to implement it in Haskell and discuss some key differences.

## Examples
* () is valid
* ()[]{} is valid
* (] is invalid
* {)}) is invalid

## My Python Solution
```py
def balancedBrackets(string):
    # Write your code here.
    stack = []
	openBrackets = '{[('
	closeBrackets = '}])'
	matchingBracket = {'}': '{', ']': '[', ')': '('}
	for char in string:
		if char in openBrackets:
			stack.append(char)
		elif char in closeBrackets:
			if len(stack) == 0 or stack.pop() != matchingBracket[char]:
				return False
	
	return len(stack) == 0
```

## My Haskell Solution

```hs
import Data.Map (Map)
import qualified Data.Map as Map

balancedBrackets brackets = balancedBracketsHelper [] brackets 0

balancedBracketsHelper stack brackets index = do
    let openBrackets = "{[("
    let closeBrackets = "}])"
    let matchingBracket = Map.fromList []

    Map.insert "}" "{" 
    Map.insert "]" "["
    Map.insert ")" "(" 
    if (isContained openBrackets (brackets!!index))
        then balancedBracketsHelper (stack ++ [brackets!!index]) brackets (index + 1)
    else 
        if (isContained closeBrackets (brackets!!index))
            then 
                if ((length stack) > 0) && ((last stack) /= (lookup matchingBracket (brackets!!index)))
                    then False
                else 
                    balancedBracketsHelper (stack ++ [brackets!!index]) brackets (index + 1)
        else
            balancedBracketsHelper (stack ++ [brackets!!index]) brackets (index + 1)

isContained c [] = False
isContained c (x:xs)
    | c == x = True
    | otherwise = isContained c xs
```

## Some Key Differences


