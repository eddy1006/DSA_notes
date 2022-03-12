<h1 align = "center">DSA notes</h1>


1. suppose u do a\^b = c (\^ = xor) now if you do b\^c u will get a again
 and vice versa therefore if you keep on doing xor between these three
 numbers only u will never get a new number. 

2. In recursion sometimes to return a count by using return 1 concet its better to make a global variable and keep on incrementing that. 

3. If you ever have to find the a very large power of a number in that case u can make use of recursion and this property: <br>
    x\^n = x.x\^(n-1) // if n is odd <br>
    x\^n = (x^2)^(n/2).. if n is even <br>
    By this technique u can achieve your answer in log(n) time. 

4. <strong>Catalan Numbers</strong>: https://youtu.be/0pTN0qzpt-Y <br>
    C0 = C1 = 0 <br>
    C2 = C0C1 + C1C0 <br> 
    C3 = C0C2 + C1C1 + C2C0 and so on.. 
    
5. The least number of perfect squares neede to sum up to a number n can be only 1,2,3 or 4 based on the <em>lagrange's four square theorem.</em> 

6. Josephus problem :- https://en.wikipedia.org/wiki/Josephus\_problem 

7. Remember that whenever we have to divide our array into two subsets with sum of means of both the subsets should be maximum then one subset contains only the max element while others contains remaining. 

8. For a problem to generate all Permutations and combinations of a string like "aab" or "aaabbc" we use the counters method where we store frequency of each alphabet and then do backtracking to generate all possible combinations and their permutations. 

9. If we do and of any number with 1 . the no stays the same. 

10. a xor 1 = a compliment <br> 
    a xor 0 = a <br> 
    a xor a = 0 
    
11. a \<\< 1 = 2 \* a            (\<\< left shift operator) <br> 
    example 10 \<\< 1 = 20 <br> 
            20 \<\< 1 = 40 <br>
            40 \<\< 1 = 80 <br> 
    therefore, a \<\< b = a \* 2\^b (\^ - power) 
    
12. a \>\> b = a/ 2\^b (\>\> right shift operator , \^ - power) 

13. Last bit in the binary digit is called LSB ( Least Significant Bit). 

14. Just like your mathematical operators the bitwise operators also follow the associativity property for eg :- <br>
    (a^b)^c = a^(b^c) = (a^c)^b (\^ - XOR) 
    
15. Suppose we have to do a certain thing with the ith bit of a number then in such situations we create a mask . for doing so we do left shit of 1 eg :- 1 \<\< 4 = 10000 <br> 
now we can use this to find the
5th bit in any number by doing its and with the number <br> 
    1001101101 <br>
    0000010000 
    
16. The MSB of a number denotes whether it is positive or negative rest other bits denote its value. 

17. Why does 2's complement of a number gives us the negative of that number? <br>
<strong>Answer</strong> :- so if we use our simple math logic then to find negative of a number we just subtract it from 0 like -10 = 0 - 10. Similarly , if we do the same thing in binary and assume that our data type is of 1 byte i.e you can represent only 8 bits then we will have something like this :<br> 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;00000000 <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-00001010 <br> 

    Now if we add 1 before all the 8 zeros then it wont matter as our data type can store only 8 bits so any more bits after that will be just ignored so our situation will become something like this: <br> 

    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;100000000 <br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-00001010 <br>

    Now, we can porve that 100000000 can be written as 1111111 + 1 <br> 
    So, 1111111 + 1 - 00001010 <br>
    =\> 1111111 - 00001010 + 1 <br>
    =\> 1's complement(or just complement) + 1 
    
18. Range formula : for n bits -2\^(n-1) to 2\^(n-1) - 1 (\^ - power) 

19. ```
    int hammingWeight(uint32\_t n)
    { int count = 0;

    while (n) {
        n &= (n - 1);
        count++;
    }

        return count;
    }
    ```
    n & (n - 1) drops the lowest set bit. It's a neat little bit trick.

    Let's use n = 00101100 as an example. This binary representation has
    three 1s.

    If n = 00101100, then n - 1 = 00101011, so n & (n - 1) = 00101100 &
    00101011 = 00101000. Count = 1.

    If n = 00101000, then n - 1 = 00100111, so n & (n - 1) = 00101000 &
    00100111 = 00100000. Count = 2.

    If n = 00100000, then n - 1 = 00011111, so n & (n - 1) = 00100000 &
    00011111 = 00000000. Count = 3.

    n is now zero, so the while loop ends, and the final count (the numbers
    of set bits) is returned.

20. Number of digits in base b of number n :<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;= int(log n) + 1 <br> 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;b <br> 
for example :- if we want to find the no of bits required to represent 10 in binary we can simply do log 10 to the base 2 and then add one to it.

21. Pascal's Triangle : <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;1 <br> 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;1 &nbsp; 1 <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;1 &nbsp; 2 &nbsp; 1 <br>
&nbsp;&nbsp;&nbsp;1 &nbsp; 3 &nbsp; 3 &nbsp; 1<br> 
&nbsp;&nbsp;1 &nbsp; 4 &nbsp; 6 &nbsp; 4 &nbsp; 1 <br>
1 &nbsp; 5 &nbsp; 10 &nbsp; 10 &nbsp; 5 &nbsp;1

    in pascal's traingle the sum of every row is a power of 2.

22. An observation : if you want to find XOR of all numbers from 0 to a where a can be any positive number, a certain pattern pops up which when broken down can be written like this : <br> 
if a%4 == 0 &nbsp;&nbsp; ans = a <br>
    a%4 == 1 &nbsp;&nbsp; ans = 1 <br> 
    a%4 == 2 &nbsp;&nbsp; ans = a+1 <br>
    a%4 == 3 &nbsp;&nbsp; ans = 0 <br> 
    for ex: xor of all nos till 5<br> 
    &nbsp;&nbsp;&nbsp;&nbsp;1^2^3^4^5 = 1 and 5%4 also equals to 1. <br> 
    doing xor for every number might result into bad complexity that is why this approach is preferable.

23. If a xor b = c , then b xor c = a and also a xor c = b.

24. f(i) = i\^(i\>\>1) will give you the ith term of gray code.

25. Divide two integers without using divison,multiplication and mod operator :- https://leetcode.com/problems/divide-two-integers/discuss/13407/C%2B%2B-bit-manipulations

26. ~0 = a sequence of 1s. similarly -1 is also a sequence of 1s.

27. <a href="https://www.codingninjas.com/blog/2020/09/09/floyds-cycle-detection-algorithm/#:~:text=Floyd's%20cycle%2Dfinding%20algorithm%20is,pointers%20of%20the%20head%20node."><strong>Floyd’s Cycle Detection Algorithm</strong></a>

28.Running a loop till sqrt(n) will give you all of its prime and odd factors. 
