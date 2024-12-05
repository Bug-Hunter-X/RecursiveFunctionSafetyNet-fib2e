# F# Stack Overflow Bug

This repository demonstrates a potential stack overflow error in F# when using mutable variables within a recursive function. The `bug.fs` file contains the problematic code.  The `bugSolution.fs` file provides a solution using tail recursion to prevent the stack overflow.

The issue arises because the recursive call to `loop()` doesn't release the stack frames until the base case is reached. With a high iteration count, this leads to a stack overflow.  The solution utilizes tail recursion, which allows the compiler to optimize the recursion into a loop, eliminating the risk of stack overflow.