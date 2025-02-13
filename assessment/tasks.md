# Tasks

Make sure to re-read the [assessment instructions](instructions.md) regularly.  
The main reference for these tasks is [FIPS 180-4, Secure Hash Standard (SHS)](https://csrc.nist.gov/pubs/fips/180-4/upd1/final).  

## Task 1: Binary Representations

Create the following functions in Python, demonstrating their use with examples and tests.

1. The function `rotl(x, n=1)` that rotates the bits in a 32-bit unsigned integer to the left `n` places.

2. The function `rotr(x, n=1)` that rotates the bits in a 32-bit unsigned integer to the right `n` places.

3. The function `ch(x, y, z)` that chooses the bits from `y` where `x` has bits set to `1` and bits in `z` where `x` has bits set to `0`.

4. The function `maj(x, y, z)` which takes a majority vote of the bits in `x`, `y`, and `z`.  
The output should have a `1` in bit position `i` where at least two of `x`, `y`, and `z` have `1`'s in position `i`.  
All other output bit positions should be `0`.

## Task 2: Hash Functions

The following hash function is from *The C Programming Language* by Brian Kernighan and Dennis Ritchie.  
Convert it to Python, test it, and suggest why the values 31 and 101 are used.

```c
unsigned hash(char *s) {
    unsigned hashval;
    for (hashval = 0; *s != '\0'; s++)
        hashval = *s + 31 * hashval;
    return hashval % 101;
}
```

## Task 3: SHA256

Write a Python function that calculates the SHA256 padding for a given file.  
The function should take a file path as input.  
It should print, in hex, the padding that would be applied to it.  
The [specification](https://doi.org/10.6028/NIST.FIPS.180-4) states that the following should be appended to a message:  

- a`1` bit;
- enough `0` bits so the length in bits of padded message is the smallest possible multiple of 512;
- the length in bits of the original input as a big-endian 64-bit unsigned integer.

The example in the specification is a file containing the three bytes `abc`:  

```python
01100001 01100010 01100011
```

The output would be:  

```python
80 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
00 00 00 00 00 00 00 00 18
```

## Task 4: Prime Numbers

Calculate the first 1,00 prime numbers using two different algorithms.  
Any algorithms that are well-established and works correctly are okay to use.  
Explain how the algorithms work.

## Task 5: Roots

Calculate the first 32 bits of the fractional part of the square roots or the first 100 prime numbers.

## Task 6: Proof of Work

Find the word(s) in the English language with the greatest number of `0` bits at the beginning of their SHA256 hash digest.  
Include proof that any word you list is in at least one English dictionary.  

## Task 7: Turing Machines

Design a Turing Machine that adds `1` to a binary number on its tape.  
The machine should start at the left-most non-blank symbol.  
It should treat the right-most symbol as the least significant bit.

For example, suppose the following is on the tape at the start:

```python
100111
```

Your Turing machine should leave the following on the tape when it completes:

```python
101000
```

### Task 8: Computational Complexity

Implement **bubble sort** in Python, modifying it to count the number of comparisons made during sorting.  
Use this function to sort all permutations of the list:  

```python
L = [1, 2, 3, 4, 5]
```

For each permutation, print the permutation itself followed by the number of comparisons required to sort it.  
