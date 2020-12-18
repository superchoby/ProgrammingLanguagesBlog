# Haskell Performance vs Javascript Performance
Here we will benchmark some algorithms in Haskell and Javascript to see how they compare. We will start with simpler algorithms and move our way
up to more complex ones. To time our Haskell algorithms, we will use the ``:set +s`` command. To time out Python algorithms, we will the time library found in the Python standard library.
## Printing the numbers from 100000 to 0
### Haskell 
```hs
printToZero 0 = print 0
printToZero x = do
    print x
    printToZero (x - 1)
```
This took 1.58 seconds

### Python
```py
for i in range(100000):
    print(i)
```
This took .2359 seconds

## The ``map`` function in Javascript and Haskell
These programs will use the ``map`` function to multiply every number in a list of size 200000 by 5.
### Haskell 
```hs
multiplyArrayByFive array = map(*5) array
```
This took 3.21 seconds

### Python
```py
print(list(map(multiplyByFive, numbers)))
```
This took .075

## Concatenating Lists
These programs will concatenate two lists of size 100000
### Haskell 
```hs
[1..100000] ++ [1..100000]
```
This took 2.80 seconds

### Python
```py
print(list(range(1, 100000)) + list(range(1, 100000)))
```
This took .1237 seconds


## Breakdown
As you can clearly see, when it comes to functions requiring to do a lot of tasks, Python has the clear advantage here. Python is a much 
faster language than Haskell and although I am sure there are many factors, I believe that Python's efficient implementation in C is a big reason for it's speed.
The Python interpreter does a great job at optimizing things and making sure things are only calculated and evaluated when they really need to be which leads to a very fast language.


