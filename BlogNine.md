# Haskell Performance vs C Performance
Here we will benchmark some algorithms in Haskell and C to see how they compare. We will start with simpler algorithms and move our way
up to more complex ones. To time our Haskell algorithms, we will use the ``:set +s`` command. To time our C algorithms, we will use the time library found in the C standard library.
## Printing the numbers from 100000 to 0
### Haskell 
```hs
printSqrtToZero 0 = print 0
printSqrtToZero x = do
    print (sqrt (fromIntegral  x))
    printSqrtToZero (x - 1)
```
This took 4.67 seconds

### C
```c
for (int i = 0.0; i < 100000; i++) {
    printf("%.17lf", sqrt(i));
}
```
This took .128919 seconds

## Printing Elements in an array
These programs will print 10 times every element in a list of size 200000. 
### Haskell 
```hs
printSqrtToZero 199999 arr = do
    print (arr!!199999);
    print (arr!!199999);
    print (arr!!199999);
    print (arr!!199999);
    print (arr!!199999);
    print (arr!!199999);
    print (arr!!199999);
    print (arr!!199999);
    print (arr!!199999);
    print (arr!!199999);

printSqrtToZero i arr = do
    print (arr!!i);
    print (arr!!i);
    print (arr!!i);
    print (arr!!i);
    print (arr!!i);
    print (arr!!i);
    print (arr!!i);
    print (arr!!i);
    print (arr!!i);
    print (arr!!i);
    printSqrtToZero (i + 1) arr
```
This took 667.32 seconds

### C
```c
for (int i = 0; i < 2000000; i++) {
    printf("%d\n", arrayName[i]);
    printf("%d\n", arrayName[i]);
    printf("%d\n", arrayName[i]);
    printf("%d\n", arrayName[i]);
    printf("%d\n", arrayName[i]);
    printf("%d\n", arrayName[i]);
    printf("%d\n", arrayName[i]);
    printf("%d\n", arrayName[i]);
    printf("%d\n", arrayName[i]);
    printf("%d\n", arrayName[i]);
}
```
This took 29.978077 seconds

## Fibonacci Numbers
These programs will get the 45th Fibonacci Number
### Haskell 
```hs
getNthFib 0 = 0
getNthFib 1 = 1
getNthFib n = getNthFib (n-1) + getNthFib (n-2)
```
This took 15.68 seconds

### C
```c
int getNthFib(int n) {
    if (n == 0) {
        return 0;
    } else if (n == 1){
        return 1;
    } else {
        return getNthFib(n - 1) + getNthFib (n - 2);
    }
}
```
This took 0.056 seconds


## Breakdown
C beats Haskell by a large margin when it comes to speed. C being faster comes to know surprise as it is one of the fastest languages out there and although it is still
a high level language, compared to most modern languages it is a lot lower level. It doesn't have support for garbage collection, dyanmic typing etc. which causes a lot of processing overhead which
will degrade the performance application. These are some of the reasons for why C is so much faster than Haskell.


