# How Functional Programming has Helped me Improve with Javascript
Javascript is a language that has some functional programming aspects but I never utilized them until I started getting exposure to
functional programming. Now I use those features whenever I get the chance and I would like to just showcase some of them. 

## Pattern Matching

Previously, if I wanted to grab the 3 values from an array of length three I would do this. 
```js
function getArrayValues(array) {
  first = array[0]
  second = array[1]
  third = array[2]
}
```

When learning functional programming I have come to realize how great pattern matching is through code snippets like this:
```hs
getArrayValues [first, second, third] = -- etc
```

I am glad to now be able to utilize this feature in Javascript as I can right code much more concice now.
```js
function getArrayValues(array) {
  [first, second, third] = array
}
```

## Higher Order Functions

Before, if I wanted to increase every value in an array by an integer, I would do it as such
```js
function increaseValuesByThree(array) {
  for (let i = 0; i < array.length; i++){
    array[i] = array[i] + 3
  }
}
```

Thanks to the concept of higher order functions, functions that can take a function as a parameter and return a function, I have learned how to
do the same function in a much more concise way. Let's take a popular higher order function called ``map`` which is used for lists.
```hs
increaseValuesByThree list = map (+3) list
```

I know take advantage of higher order functions thanks to functional programming. Now when I want to increase every value in an array in Javascript I do:
```js
array.map(n => n + 3)
```

These are just some of the functional programming features I now take advantage of in Javascript and I would suggest
anyone to try to gain proficiency in a functional programming language because it can help you think in different ways and solidify concepts that
can help you when you are doing object oriented programming.
