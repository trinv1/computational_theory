# Computational Theory

## Introduction 
This project covers the computational concepts that support the [Secure Hash Standard](https://nvlpubs.nist.gov/nistpubs/FIPS/NIST.FIPS.180-4.pdf), in particular the SHA-256 hashing algorithm. This notebook aims to explore the various computational and mathematical operations that are involved in cryptographic systems. 
Each problem focuses on a different stage of the SHA-256 process, from bitwise operations to generating constants and performing hashing computations.

## Requirements
This project requires the following Python packages:<br>
* **numpy**<br>

### To install these dependencies:
**pip install -r requirements.txt**

## Overview 
### Problem 1
#### Binary Words and Operations
In Problem 1, we are implementing the SHA-256 logical functions (Parity, Ch, Maj, Σ₀, Σ₁, σ₀, σ₁) using NumPy to perform 32-bit operations. SHA-256 operates through these logical functions and bitwise operations, providing a high level of security that is resistant to collisions and **pre-image attacks** (original message before its been hashed) ([SHA-256 logical functions explanation](https://mojoauth.com/compare-hashing-algorithms/sha-256-vs-sha-384/)).

### Problem 2
#### Fraction Parts of Cube Roots
In Problem 2, we are generating the first 64 prime numbers using The Sieve of Eratosthenes Algorithm for speed and memory efficiency, and computing the SHA-256 constants from the fractional parts of their cube roots. These constants are mathematically derived values defined by the Secure Hash Standard to ensure non-linearity and to prevent predictable patterns in the hash process, ensuring that each round of the computation is different. 

### Problem 3 
#### Block Parsing and Message Padding
In Problem 3, we implement message padding and block parsing according to Sections 5.1.1 and 5.2.1 of the Secure Hash Standard.
SHA-256 can only process data in fixed-size 512-bit (64-byte) blocks, so before hashing can occur, any input message must be:<br>
Appended with a single ‘1’ bit<br>
Padded with ‘0’ bits so that the final block has space for:<br>
A 64-bit big-endian integer that stores the length of the original message in bits<br>
The aim of this padding step is to guarantee an unambiguous and consistent message format, ensuring that two different messages can never hash to the same value.

### Problem 4
#### Hashing
In Problem 4, we implement the SHA-256 compression stage that produces the final hash value. Each padded 512-bit message block is processed through 64 rounds of bitwise and arithmetic operations that update the hash state. The output of each block is combined with the current hash state and used as input for the next block until the final 256-bit hash is generated.

### Problem 5
#### Passwords


## URL's, Tools and Packages Used
Markdown cell `SHA-2 Functions` in `Problem 1`:<br>
* [SHA-224 and SHA-256 explanation](https://mojoauth.com/compare-hashing-algorithms/sha-224-vs-sha-256/): This resource helped develop my understanding of how bitwise logical functions contribute to the 
non-linearity of SHA-256, making the hash output unpredictable and resistant to reversal attacks.

Markdown cell `Rotate Right Function` in `Problem 1`:<br>

* [Rotation function](https://www.geeksforgeeks.org/dsa/rotate-bits-of-an-integer/): Resource aided in figuring out how to code function that performs right rotation operation.
------------------------
Markdown cell `Find Prime Function` in `Problem 2`:<br>
1. [Vectorized Sieve of Eratosthenes Algorithm](https://www.geeksforgeeks.org/python/python-program-for-sieve-of-eratosthenes/) and [LibreTexts explanantion of algorithm](<https://math.libretexts.org/Courses/Coalinga_College/Math_for_Educators_(MATH_010A_and_010B_CID120)/04%3A_Number_Theory/4.03%3A_The_Sieve_of_Eratosthenes>): Resources used for understanding and implementing algorithm to add computational efficiency when finding prime numbers

2. [Prime number function in lecturer repo](https://github.com/ianmcloughlin/computational-theory/blob/main/materials/prime_numbers.ipynb): A function provided by lecturer to find first 64 prime numbers

3. [NumPy vectorization](https://www.geeksforgeeks.org/numpy/vectorized-operations-in-numpy/) and [Python slice function](https://www.geeksforgeeks.org/python/python-slice-function/): Resources used to aid understanding  of what numpy vectorization and python slicing was

Markdown cell `Frac Cube Function` in `Problem 2`:<br>
1. [Cube root](https://www.geeksforgeeks.org/python/numpy-cbrt-python/) and [np.modf()](https://www.geeksforgeeks.org/python/python-modf-function/): Resources used to aid understanding of NumPy's functions to get the cube root of a number and split it into its fractional and integer parts
------------------------
Markdown cell `File to Blocks Function` in `Problem 3`:<br>
* [Generator yield explanation](https://www.datacamp.com/tutorial/python-generators): Resource used to understand how generators avoid memory issues and provide context to functions purpose

Markdown cell `Block Padding Function` in `Problem 3`:<br>
* [Padding explanation](https://enlear.academy/blockchain-deep-dive-into-sha-256-secure-hash-algorithm-256-bit-824ac0e90b24): Resource used to aid understanding of padding process and provide explanation of padding under `Purpose:` in markdown cell.

Testing code blocks under `Problem 3`:<br>
[ASCII to Hex](https://www.rapidtables.com/convert/number/ascii-to-hex.html): Used to understand 0x41 representation in ASCII






