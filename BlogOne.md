# Interesting Things about Functional Programming

When people who are used to object oriented programming attempt to learn functional programming, they tend to try to associate newly acquired knowledge with already known knowledge in order to understand the concepts themselves and given how different functional and object oriented programming is, this often results in failure and many people get discouraged from it and thing functional programming is weird and just not for them. Here I would like to introduce some core and fun things about functional programming that will help you gain that functional programming mindset when trying to learn it

## Just a few of the Cool Features
Before getting started with FP, it is important to understand a few key differences.
  * Variables are immutable - Data is immutable in functional programming which preserves the purity of functions so that you know what they do everytime.
      While in an object oriented language like Java, you can do this:
      ```java
         int canBeChanged = 5
         canBeChanged = 10
      ```
      In a functional programming language like haskell, that can not be done.
      ```hs
        cannotBeChanged = 5
        cannotBeChanged = 10
      ```
      This will produce an error saying "Multiple declerations of 'yes'"
      
  * Everything is a function - There are no classes in FP and as a result, you can't have things such as objects and every function is meant to perform a specific task. This can make the code a lot cleaner and easier to read.
  
     Here's how a minimal file that squares a number would look like in Java:
     ```java
       public SquareNumber {
          int squareNumbers(int x) {
             return x ^ 2;
          }
       }
     ```
     
     Here's how a file with the same functionality would look like in Haskell:
     ```hs
        squareNumber x = x ^ 2
     ```
  
  * Uses recursion for iteration - since loops can not be used, recursion is used instead.
    Here is a function in Java that finds the factorial of a number iteratively
    ```java
       static int factorial(int n) 
       { 
           int res = 1, i; 
           for (i=2; i<=n; i++) 
               res *= i; 
           return res; 
       } 
    ```
    
    Due to the immutibility of variables in functional programming for loops such as ``(for int i = 0; i < 5; i++)`` can not be used as the value of the ``i`` variable can't be increased every loop, so recursion is used.
    ```hs
       factorial 0 = 1
       factorial n = n * factorial (n-1)
    ```
    
Now you know some cool parts about functional programming and can hopefully see the benefits of learning it. Knowledge of these core differences between functional programming and will help tremendously when it comes to gaining proficieny in a functional programming langauge.
    
    
    


 

