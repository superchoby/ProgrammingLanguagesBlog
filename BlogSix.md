# Stumbling Blocks of Learning Haskell

Coming from an object oriented background, I understand the many stumbling blocks of learning Haskell and hopefully this article will make your transition into Haskell smooth and less painless. Functional Programming has some major differences from object oriented programming and an understanding of these different features can make learning Haskell a lot easier. 
## Some of the Common Stumbling Blocks

  * Haskell has a interesting pattern matching system that can cause a single function to have multiple, completely different effects.
      ```hs
        less O O = False
        less O n = True
        less n O = False
      ```
      Here is a function called less that takes in two natural numbers and evaluates whether or not the first number pass is less than the second number.
      Haskell has a system where it can check all the declarations of a function when it is called and see which function's parameters matches the given arguments.
      Readers seeing this syntax may be confused at first and think a functionl is constantly being redefined or mistake it for something else that's wrong. 
      
  * Haskell has an interesting syntax for declaring parameter and return types
  
     ```hs
        less :: NN -> NN -> Bool
     ```
     
     At first when seeing this it can be very confusing but the way it is read is that the name of the function is written first and then after the ``::``, you list the parameter
     and return types. Everything except the very last type listed is the type of a parameter. Haskell makes sure to ensure this is the case as you go through and use this function.
     
  * For many users, understanding recursion is very hard especially when you are very used to loops and it can be hard to picture it in your head. Often creating and looking at a list of every step that is run can help picture it better.
  
  ```hs
  subtr :: NN -> NN -> NN
  subtr O n = O
  subtr n O = n
  subtr (S n) (S m) = subtr n m
  ```
   Let's use this subtraction function and walk through it. So if we ran (Subtr S S 0 S S S 0) this is what would be computed. 
   Subtr S S 0 S S S 0<br/>
   Subtr S 0 S S 0<br/>
   Subtr 0 S 0<br/>
   S 0<br/>
  
  At first, manually going through every step could help understand the execution of recursive Haskell functions and eventually you can reach a point where you can picture it in your head. 
  <br/><br/>
 
 
 Hopefully through reading this blog, you are able to have a much smoother transition now into Haskell. 
  
  
  
