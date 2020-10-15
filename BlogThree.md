# How to Think Recursively
Those who are learning functional programming and are used to object oriented programming often struggle when it comes to recursion because when 
they approach problems using iteration, they almost always attempt to solve the problems with loops and as a result, they tend to struggle with 
recursion because the mindset you take when approaching a problem with a loop vs recursion is different. Here I would like to give some tips on
how to think recursively so that recursive solutions can become easier to generate. We will look at the classic problem of creating a function to
find the factorial of a number.

First, let's talk about what a recursive function needs. Two things are needed in a recursive function:
  * A handler for the base case where the recursion stops and the function can return the result
  * A handler for the recursive case where the function calls itself in order to get one step closer to the solution
  
We will now go about the steps needed to create the two necessary parts for a recursive function
 
## Coming up With the Base Case
When a recursive function reaches the base case, this is where the function does not need to call itself and can immedietly return the result. Try to think of
a situation in which, if this was the case for the problem you are trying to solve, no calculation would be necessary. In the case of the factorial of a number,
if we are trying to find the factorial of 0, we know it is 1 without any calculations necessary, so that will be our base case.
Written in Haskell, our base case looks like: ``findFactorial 0 = 1``


## Coming up With the Recursive Case
When a recursive function is not at the base case, we are at a part where we need to call the function again in order to get one step closer to our goal.
Coming up with how to handle the recursive case is usually the most difficult part for people. In order to accomplish this, you first need to break down the
problem into the simplest steps and try to look at the problem with that mindset. For example, to create this function we try to think in our heads, "how can I
take the factorial of 5?" What then needs to happen is we need to break this problem down so where instead of asking ourselves, how can we find the solution to 
whatever scenario, it is how can we code a function that will solve every step necessary in the problem. So one way we can break down the problem is now instead of
thinking of our problem the way we did before we can think of it as, "How can I multiply 5 then 4 then 3 then 2 then 1?" Now we are thinking of our problem in a way
where it is all broken down into simple individual steps. Now we just need to ask ourselves how we can solve a single step in our list of individual steps that we
have now just come up with. Now we should be asking ourselves "How can I multiply 5 with 4?" With this, we can convert this into an expression that we can then
implement direcly into code. Now instead of thinking of it this way we can think of it has "How can I multiply x with x - 1?" Now we have broken our code into the 
simplest possible step, and converted it into terms that an be direcly translated into code. Translated into code this looks like
`` findFactorial x = x * (x - 1)``
Now that we have solved the simplest step, we can go backward and try to think more broad again. So now looking at the question 
"How can I multiply 5 then 4 then 3 then 2 then 1?" we can change our code to go from solving an individual step to now be able to solve every step.
``findFactorial x = x * findFactorial (x - 1)``

## The Final Solution
```hs
findFactorial 0 = 1
findFactorial x = x * findFactorial (x - 1)
```

Here we have broken down the steps that should be taken for the vast majority of recursion problems. Hopefully with this, recursion problems should look at 
least a little less scary now that you know about this approach.
