# Password Generator in C
Based on Marsenne Twister's general-purpose pseudorandom number generator. ([pseudocode on Wikipedia](http://en.wikipedia.org/wiki/Mersenne_twister#Pseudocode))

The state of the Mersenne Twister algorithm is represented by an array of numbers, typically 624 numbers. Each element in the array is denoted as MT[i], where i ranges from 0 to 623 (since the array has 624 elements).

The state update involves the following formulas:

```
MT[i] = MT[(i+1) mod 624] XOR (Y >> 1)

MT[i] = tempering(MT[i])
```

Here, XOR represents the XOR operation, Y is the result of a multiplication and linear combination of two elements from the current state, and tempering(x) is a tempering function that improves the statistical properties of the generated sequence.

Pseudo-Random Number Generation:
To generate a pseudo-random number, the following formula is used:

```
X = MT[i] XOR ((MT[i] >> u) AND d)
```

In this formula, >> denotes the right shift operation, AND represents the bitwise AND operation, and u and d are constants that determine the shift amount and mask applied to the element MT[i] to obtain the pseudo-random number X.
