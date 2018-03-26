+++
# Date this page was created.
date = "2018-02-07"

# Project title.
title = "Hashing"

# Project summary to display on homepage.
summary = "Hashing is the generation of a value or values from a string of text using a mathematical function."

# Optional image to display on homepage (relative to `static/img/` folder).
image_preview = ""

# Tags: can be used for filtering projects.
# Example: `tags = ["machine-learning", "deep-learning"]`
tags = ["hashing", "low-latency", "hash"]

# Optional external URL for project (replaces project detail page).
external_link = ""

# Does the project detail page use math formatting?
math = false

# Optional featured image (relative to `static/img/` folder).
[header]
image = ""
caption = ""

+++
## Introduction
In its simplest form `hashing` is generation of a value or values from a string of text using a mathematical function. So we also refer to it as a hash function that maps data of arbitrary size to data of fixed size.

It by the definition and implementation is generally regarded as Pseudo Random Number Generators (PRNG).

## Properties

### Determinism
A hash procedure must be deterministic - meaning that for a given input value it must always generate the same hash value.

### Uniformity
A good hash function should map the expected inputs as evenly as possible over its output range because the cost of the hash increases with the number collisions.

### Fixed and defined range
It is often desirable that the output of a hash function have fixed size. Producing fixed-length output from variable length input can be accomplished by breaking the input data into chunks of specific size.


## Guidelines for implementing hash functions

1. When hashing large messages, one could break the message up into chunks and compute the hash of each chunk in parallel then aggregate the hashes using a mix operation, this will dramatically increase the throughput of the hash function when running upon architectures that support multiple cores. This method of hashing is known as a `Merkle-Tree` or a hash-tree.

2. The "mix" operation does not need to be the same on each round. There could be multiple mix operations which are selected based on criteria such as the index of the current round, the value of the internal state etc.

3. The operations present in the Mix should be carefully chosen, as more often than not the mixing process may result in lowering the entropy of the internal state to the point where the internal state does not change. As an example in the mix operation denoted above if the internal state reaches the value ZERO it will typically end-up returning zero.

4. The mix operation should handle repeated values in the message block, without causing a "flush effect on the internal state. A typical scenario might be a message comprised of bytes with the value of zero. Ideally a well designed has function should take a long-time before it reduces the internal state to zero.

5. When hashing a key derived-from or otherwise aliasing a pointer to memory that has been obtain from an allocator that returns aligned addresses, one will observe that the first 2 or 3 Least Significant Bits (LSBs) of the key will always be zero, or in other words will have zero entropy. This is due to the fact that the pointers will be storing addresses that are multiples of either 4 or 8 depending on the machine's addressing granularity. The following are a couple of techniques to resolve the issue of low-entropy LSBs:
   * Fill in the LSBs with bits from their higher order neighbours: pointer |= (pointer >> 3) & 0x03
   * Fill in the LSBs with bits from a LUT: pointer |= lut[round_i % lut_size] & 0x03

## Types of Hashing - usescases/application

### 1. String hashing
Simplest and often used in area of data storage where it forms the basis if indexing into hash tables.

### 2. Cryptographic Hashing
A special class of hash function that has certain properties which make it suitable for use in cryptography. It is a mathematical algorithm that maps data of arbitrary size to a bit string of a fixed size (a hash) and is designed to be a one-way function, that is, a function which is infeasible to invert. The input data is often called the message, and the output (the hash value or hash) is often called the message digest or simply the digest.

The ideal cryptographic hash function has following main properties:

* it is deterministic so the same message always results in the same hash
* it is quick to compute the hash value for any given message
* it is infeasible to generate a message from its hash value except by trying all possible messages
* a small change to a message should change the hash value so extensively that the new hash value appears uncorrelated with the old hash value
* collision resistance property - it is infeasible to find two different messages with the same hash value
* its input can be any string of any size
* it produces a fixed size output


#### Usecases

##### Password checks
To authenticate a user, the password presented by the user is hashed and compared with the stored hash. The password is often concatenated with a random, non-secret salt value before the hash function is applied. The salt is stored with the password hash. [Argon2](https://en.wikipedia.org/wiki/Argon2) is the NIST ([SP 800-63B-3](pdf/NIST.SP.800-63b.pdf)) recommended algorithm.

##### Verifying the integrity of files or messages
Determining whether any changes have been made to a message (or a file), for example, can be accomplished by comparing message digests calculated before, and after, transmission (or any other event). `MD5`, `SHA1`, or `SHA2` hashes are sometimes posted along with files on websites or forums to allow verification of integrity.[6] This practice establishes a chain of trust so long as the hashes are posted on a site authenticated by HTTPS.

##### File or data identifier
A digest can also reliably used to identify a file; source code management systems like Git, use the **sha1sum** of various types of content (file content, directory trees, ancestry information, etc.) to uniquely identify them. Hashes are used to identify files on peer-to-peer filesharing networks. For example, in an ed2k/Magnet link, is combined with the file size, providing sufficient information for locating file sources, downloading the file and verifying its contents.

##### Proof of work
A proof-of-work system (or protocol, or function) is an economic measure to deter denial-of-service attacks and other service abuses such as spam on a network by requiring some work from the service requester, usually meaning processing time by a computer. A key feature of these schemes is their asymmetry: the work must be moderately hard (but feasible) on the requester side but easy to check for the service provider. Bitcoin is an example.
The way it typically works, is a known value K is given (some number of bits), then either an expected hash value or a hash value with a specific trait (eg: certain number of leading zero bits) is proposed.
The applicant (aka entity performing the work) will then go off and perform a computation to determine another piece data D, such that H(K | D) (the hash of the concatenation of K and D) will either be equal to the expected hash value or will posses the properties required to prove the work has been done. Furthermore because the verification of the hash value can be performed cheaply and efficiently and the work in computing the value D itself must be done in full .


### 3. Geometric Hashing
A hashing technique developed in the field of computer vision for matching features against a database of such features. This is object recognition that allows objects to be identified in an image that are partially occluded or have gone gemetric transformation.

### 4. Bloom Filters
A Bloom filter is a data structure designed to tell you, rapidly and memory-efficiently, whether an element is present in a set. The price paid for this efficiency is that a Bloom filter is a probabilistic data structure: it tells us that the element either definitely is not in the set or may be in the set. Often it is coded as a bit-vector where a larger filter will have less false positives.

Bloom filters are commonly found in applications such as spell-checkers, string matching algorithms, network packet analysis tools and network/internet caches.
