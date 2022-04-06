# Introduction
* Getting rid of explicit loops and running the code in vectorized format.
* Your code actually runs over 300x faster if using vectorized version as compared to non-vectorized version.
* Try using as many inbuilt functions avaiable that you can use instead of loops.
* Can use time library of python to check the result.

# How does it work?
* Using inbuilt functions have optimised code that can even run paralelly on CPU or GPU using SIMD (Single Instruction Multiple Data).
* This means that using for loops only does the computations on CPU sequentially whereas the inbuilt functions can take advantage of paralellization of CPU and GPU to achieve much more faster results.