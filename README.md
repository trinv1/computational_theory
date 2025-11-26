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

### Problem 5
#### Passwords


## URL's, Tools and Packages Used




