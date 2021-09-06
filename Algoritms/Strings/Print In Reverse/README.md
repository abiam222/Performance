# Anagram

Objective: We want to test the performance of the "Print in reverse" based on different metrics: We want to use different data structure and algorithms to see which ones run the "Print in reverse" fastest.

NOTE: Lodash is a JS library

1. We will use 3 functions
    a. Soring algorithm using vanillas Javascript functions (usingFunctions)
    b. using a for loop (looping)
    c. Using lodash's _reverse method (usingLodash)


Big Oh (O) complexity and space complexity

usingFunctions - we used vanilla javascript. Using split(), reverse(), join(). No other ds were used.

looping - O(n^2) used a for loop

using Lodash - Just as the function "usingFunctions" we will use split() and join() but instead of JS's reverse() we will replace it with lodash "reverse()"

For each function we will run 1000 iterations of a string, getting each answer in nanoseconds. We will then get the average of each iteration for a final average time per function

Solution (all in nanoseconds):

looping: 65215.078
usingFunctions: 26258.72
usingLodash: 13400.612

Hence "usingLodash" was almost twice as fast as "usingFunctions" and almost 4x as fast as "looping". 

Lodash reverse

 function reverse(array) {
      return array == null ? array : nativeReverse.call(array);
}

nativeReverse => nativeReverse = arrayProto.reverse;

arrayProto => Array.prototype

Seems like its just the plain JS reverse? is this correct?
Why is it so different from  "usingFunction" if its using the same function?
Thoughts: Is reverse Array.prototype.reverse() faster than just using it [].reverse()
I would need to test this
It does use nativeReverse.call() => aka Array.prototype.reverse.call(array)


After doing some test. It does seem like using Array.prototype.reverse() directly 
over [].reverse() makes it faster. I believe since if we do [].reverse() it has to go
to the program and eventually has to call Array.prototype.

The difference isn't that great but if we do an iteration of a string 1000 times 
we see that the average time for Array.prototype is 3145.328 and for the 
JS its 3643.302 a difference of about 497.974 nano seconds. 
What if in our application we had Array.prototype = arrayProto 
and then call arrayProto.reverse() then that would work. Thats exactly what
Lodash is doing 