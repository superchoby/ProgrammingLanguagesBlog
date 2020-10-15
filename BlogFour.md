# Haskell Performance vs Javascript Performance
Here we will benchmark some algorithms in Haskell and Javascript to see how they compare. We will start with simpler algorithms and move our way
up to more complex ones. To time our Haskell algorithms, we will use the ``:set +s`` command. To time out Javascript algorithms, we will use a combination of 
``console.time()`` and  ``console.timeEnd()``.

## Printing the numbers from 100000 to 0
### Haskell 
```hs
printToZero 0 = print 0
printToZero x = do
    print x
    printToZero (x - 1)
```
This took 1.62 seconds

### Javascript
```js
for (let i = 100000; i >= 0; i--)
  console.log(i)
```
This took 21.28 seconds

## The ``map`` function in Javascript and Haskell
These programs will use the ``map`` function to multiply every number in a list of size 200000 by 5.
### Haskell 
```hs
multiplyArrayByFive array = map(*5) array
```
This took 3.54 seconds

### Javascript
```js
array.map(n => n * 5)
```
This took 15.63 seconds

## Concatenating Lists
These programs will concatenate two lists of size 100000
### Haskell 
```hs
[1..100000] ++ [1..100000]
```
This took 2.89 seconds

### Javascript
```js
/* before timing the functions
used this code to initialize the arrays
const arrayOne = []
const arrayTwo = []
for (let i = 1; i < 100000; i++) {
  arrayOne.push(i)
  arrayTwo.push(i)
}
*/
console.log(arrayOne.concat(arrayTwo))
```
This took 12.88 seconds


## Breakdown
As you can clearly see, when it comes to functions requiring to do a lot of tasks, Haskell's has the clear advantage here. Haskell is a much 
faster language than Javascript and although I am sure there are many factors, one of the biggest factors is that Haskell is strongly typed while
Javascript is loosely typed, causing errors to be checked during compile time vs run time.


