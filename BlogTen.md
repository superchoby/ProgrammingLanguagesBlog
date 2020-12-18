# Haskell Performance vs Java Performance
Here we will benchmark some algorithms in Haskell and Java to see how they compare. We will start with simpler algorithms and move our way
up to more complex ones. To time our Haskell algorithms, we will use the ``:set +s`` command. To time our Java algorithms, we will use the System class in Java.
## Printing the numbers from 200000 to 0
### Haskell 
```hs
printSqrtToZero 0 = print 0
printSqrtToZero x = do
    print (sqrt (fromIntegral  x))
    printSqrtToZero (x - 1)
```
This took 9.31 seconds

### Java
```java
for (int i = 0.0; i < 100000; i++) {
    printf("%.17lf", sqrt(i));
}
```
This took 0.883196979 seconds

## Printing Elements in an array
These programs will print 10 times every element in a list of size 100000. 
### Haskell 
```hs
printArrElement 99999 arr = do
    print (arr!!99999);
    print (arr!!99999);
    print (arr!!99999);
    print (arr!!99999);
    print (arr!!99999);
    print (arr!!99999);
    print (arr!!99999);
    print (arr!!99999);
    print (arr!!99999);
    print (arr!!99999);

printArrElement i arr = do
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
    printArrElement (i + 1) arr
```
This took 155.48 seconds

### Java
```java
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
This took 3.156467802 seconds

## Fibonacci Numbers
These programs will get the 38th Fibonacci Number
### Haskell 
```hs
getNthFib 0 = 0
getNthFib 1 = 1
getNthFib n = getNthFib (n-1) + getNthFib (n-2)
```
This took 66.17 seconds

### Java
```java
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
This took 0.167784239 seconds


## Breakdown
Java is a lot better than Haskell in terms of performance. I believe Java having to be compiled first before it runs plays a big factor as all the code is compiled and ready to be executed. Also, bytecode, the code Java gets compiled to, is designed to run very fast. 


