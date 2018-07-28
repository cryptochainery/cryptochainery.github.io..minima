---
layout: tutorial
title: What is public/private key cryptography with an example?
permalink: /asymmetric-public-private-key-cryptography-with-example/
description: Hashing is fundamental to blockchains, bitcoins, and any cryptocurrency and in this lesson, we look at the basic properties of hashing and how these properties makes hashing attractive to blockchains and cryptocurrencies. 
---
Before we dive into symmetric/aymmetric cryptography or understanding whta public-private key cryptography is, let us first take a quick glance at the definition of cryptography. It is defined on Wikipedia as follows:

> **Cryptography is the practice and study of techniques for secure communication in the presence of third parties called adversaries.**
>
> _Rivest, Ronald L. (1990). "Cryptography". In J. Van Leeuwen. Handbook of Theoretical Computer Science. 1. Elsevier._


What this says, is that cryptography is a science that deals with making communication safe and secure from people trying to eavesdrop or spy on the communication. You can imagine how crucial cryptography is to everything that we do in our daily lives - send emails, make phone calls, send text messages, log on to our online banking systems, make international money transfers, cyber-security, cyber-warfare, etc.

### Symmetric cryptography
There are two types of cryptography (that we will deal with in this tutorial) and they are symmetric and asymmetric cryptography. Note that we use the words cryptography and encryption inter-changably in this tutorial. 

Let's take a simple example to understand symmetric encryption. Suppose I create a code language and write a message in it to my best friend and I give it to him. He won't be able to understand it until I give him the code - and this is the huge problem. Somebody might attack me while I am on the way to give him the code and then my code language is cracked/hacked and becomes useless. In symmetric encryption, both the sender and the receiver need to have the code for creating and reading the message and transmissing this information is a security threat! 

### Asymmetric cryptography - the solution?
How do we solve this? A simple but superb way is to create two codes - one for encoding and one for decoding (don't worry how - but just go along with the example). Now I give my best friend my encoding code and tell me to use that to send me a message. After I get his message, I can use my decoding code to read the message. Now - I can tell the whole world my encoding code and ask them to send me messages. Why? Because only I have the decoding code to read the messages - so my secrets are safe. Now if I have to write a message to my friend, then he has to create a pair of codes and give me his encoding code while he keeps his decoding code with him (safely!)

Here is another example. Suppose I get a lock and give it to my friend but keep the key with me. I ask him to take a box, put a message in it, and lock it with this lock. This is a safe method, because only I have the key to the lock and only I can open the box. 

### Public-private key encryption (asymmetric encryption)
What we just studied is the fundamental concept of public-private key encryption (asymmetric encryption). 

I create two keys - a public and a private key. I keep the private key with me safely and give my public key to the whole world. Now anyone can use the public key to encrypt a message and only I can decode it with my private key. Simple right?

### But what are the catches in public-key cryptography?
* the encoding/decoding should be computationally efficient and not take a very long time! 
* it should be impossible/incredibly hard to guess a private key by looking at the public key. 
* the weakest point is ensuring the safety of the private key. This is a crucial step of asymmetric encryption. 

Example of public key systems : the most common and widely used public-key cryptosystem is the [RSA](https://en.wikipedia.org/wiki/RSA_(cryptosystem)) algorithm attributed to three computer scientists from MIT.

Apart from public-private key encryption, there is another important encryption method called "Digital Signatures" that we shall study in the next tutorial. Hope you understood asymmetric encryption in this tutorial. If you have any questions, please let me know in the comments section. Thanks! 
