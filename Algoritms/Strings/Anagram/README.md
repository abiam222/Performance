# Anagram

Objective: We want to test the performance of the "Anagram" based on different metrics: We want to use different data structure and algorithms to see which ones run the "anagram" fastest. We will also use different amount of data sets, since algorithms can run on a completely time based on size of the input. 

1. We will use 3 functions
    a. Soring algorithm using plain Javascript (isAnagram)
    b. Using Heap algorithm (isAnagramHeap)
    c. Using a hashmap data structure (isAnagramMap)

2. We will test the algorithms based on 2 different data sets. One "large" and one "small"

Big Oh (O) complexity and space complexity

isAnagram - we used vanialla javascript. Using split(), sort(), join(). No other ds were used.

isAnagramHeap - O(n log n) using the heapsort algorithm. Tree and Array were used as ds's.

isAnagramMap - O (log n) using the javascript Map() function. No extra data structures were used. 1 Object ({}) was used for a break exception

Anagram - a word, phrase or name formed by rearranging the letters of another 
e.g. cinema, formed form iceman 



Solution:

Small data set (all average times in nanoseconds): 
I ran the small data set 6 times for each function. I summed the average of each to get 
a total average time. 
isAnagram: 30140.4992
isAnagramMap: 30820.2665
isAnagramHeap: 39410.8105

Hence isAngram run fastest with the small data set. This is not entirely shocking as algorithms can run faster with smaller data sets vs larger ones. (e.g. bubble sort)

Larger data set (all average times in nanoseconds):
isAnagram: 55857.457
isAnagramMap: 19528.8744
isAnagramHeap: 53985.0354

isAnagramMap ran wayyyy faster on a large data set. 

Overall, "isAnagramMap" ran fastest if we took the average of the large and small data set.