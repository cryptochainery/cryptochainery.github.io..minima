---
layout: page
title: What is hashing in cryptography?
permalink: /hashing-cryptography-sha256-bitcoin-blockchain/
description: Who is the founder/inventor of bitcoin and blockchain technology? Who is Satoshi Nakamoto and what is the mystery surrounding him?
published : false
---
Hashing is one of the fundamental concepts that you should know to understand blockchain, bitcoin, or any cryptocurrency. There are entire fields, organizations, PhD thesis dedicated to hashing, but you don't need to go so deep to understand how hashing is used in blockchain. You need to understand how hashing works conceptually, and how it enforces trust in the system, how it is used for digital signatures, how hashing plays a role in the proof-of-work concept of blockchain. That being said, let's get started. 

Define hashing 
Hashing means taking an input string of any length and giving out an output of a fixed length.

For example :-

```
input = crypto     output = jhae87rakjsdf7asdfasiu6fasdnfbkaf
input = currency   output = ansldkfj9a23nduas8mnd8nn86nnkhate 
```


That is the basic definition of hashing. Take some input data, process it, and produce an output which has a fixed, known number of characters. E.g. given any input string, I will create a hashing function that generates an output with 32 characters. Given this basic idea, let us see where you can use hashing and then what are the necessary features of a hashing function. 

### What is a cryptographic hash?
Repeating this from Wikipedia : _A hash function is any function that can be used to map data of arbitrary size to data of a fixed size. The values returned by a hash function are called hash values, hash codes, digests, or simply hashes. A cryptographic hash function allows one to easily verify that some input data maps to a given hash value, but if the input data is unknown, it is deliberately difficult to reconstruct it (or any equivalent alternatives) by knowing the stored hash value._

That is a lot of information to digest - so let's break it down into small chunks. 


So, let's say you decide to create your own hashing function and you want everyone to use it. There are some basic properties that your hashing function needs to satisfy in order for others to take it seriously. Let's take a look! 

* **Deterministic** : this is easy to understand. What it says is that if I provide a particular string (e.g. "cryptochainery" a zillion times to the hashing function, then every single time, the hashing function should return the exact same hash. That is called deterministic. There are some corner cases though. Some hashing functions might use the system time or memory address to create the hash of a string. In this situation, if you run it again, you might not get the same output hash. So, in this situation, the hash is deterministic for that session (period of time) only. 

* **Uniformity** : A good hash function should map the expected inputs as evenly as possible over its output range. If this is not satisfied, then a hashing function might map all of its inputs to a particular range of possible hash values and this might lead to collisions. And, collisions (or two inputs giving the same output) is certainly something that we want to avoid. 

* **Not invertible** : This is sometimes also called the "one-way requirement". Simply put, if I cannot guess the input by looking at the output, then it is a non-invertible hash. In the worst case, it should require an impossible amount of computation to reverse-engineer or invert the hash. That is why it is also called the "one-way property".

* **Fixed size / defined range** : It is desirable that the hash function create a hash of a known, fixed, pre-determined length. For example, the popular [SHA256](https://en.wikipedia.org/wiki/SHA-2) hash produces a 256 bit long hash. This is helpful in using it in table-lookups, etc. There is 

* **Quick to compute** : this is an interesting property. To have a lot of people use your new hash function, it should be easy for them to compute - right? But, it should not be easy to reverse-engineer! 

* **Small changes to the input make large changes to the hash** : This is an intrinsic property that is connected to Uniformity, Not Invertible properties of the hash. If I change one character to the input (maybe change an "x" to a "y") and I see that only the last character of the output changed from "0" to "1", then that is a clue to a hacker. It is preferable that even the smallest change to the input makes a large change to the output. Here is an example from SHA-256. 

```
input = cryptochainery     output = 0B8A51051650071F36D64ABC1DACB41FE52601B6E8B2C89BFBDCA129FA1650EF
input = cryptochaineryx    output = C8B79109CB23C3E218D8C37D0D787BD95362FA58DEBFE3145D4B469C3E00278F 
```


Okay that was a lot of information. Let's summarize it quickly :-
> * the hash should have a fixed size. 
> * you should not be able to guess the input by looking at the output (because the output has a recognizable pattern).
> * no two inputs should give the same hash.
> * the hash should be sufficiently hard to reverse-engineer (computationally).
> * the hash should be computationally efficient to compute. 

In the context of cryptocurrencies like Bitcoin, the transactions are taken as an input and run through a hashing algorithm (Bitcoin uses SHA-256) which gives an output of a fixed length.
