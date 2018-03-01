+++

# this an example markdown - used to show what builtin there are - Narinder

# Date this page was created.
date = "2018-02-15"

# Post title.
title = "Why Hashing?"

# Project summary to display on homepage.
summary = "Reason's for hashing functions"

# Optional image to display on homepage (relative to `static/img/` folder).
image_preview = ""

# Tags: can be used for filtering projects.
# Example: `tags = ["machine-learning", "deep-learning"]`
tags = ["crypto", "hashing"]

# Optional external URL for project (replaces project detail page).
external_link = ""

# Does the project detail page use math formatting?
math = false

# Optional featured image (relative to `static/img/` folder).
[header]
image = ""
caption = ""

+++
When using algorithms and searching we often have *key* that needs to lookup a data structure or value. These keys are often strings and by nature are not really good in array indexing which requires an integer. Here hashing comes to play where we convert a key into an array index for a table lookup.

# Uses for Hashing

## Lookups
Lookups using a data structure called hash table for quick access to objects. Here hashing is applied to the key to a index value. When two different keys result in the same index value we have what is called a collision.

## Cryptography
Algorithms that are designed to towards security and are used to create digital fingerpints for authentication and data integrity

# Hashing Terminology

## Open Addressing
A method of collision resolution in hash tables. With this method a hash collision is resolved by *probing*, or searching through alternate locations in the array (the *probe sequence*) until either the target record is found, or an unused array slot is found, which indicates that there is no such key in the table. A critical influence on performance of an open addressing hash table is the load factor; that is, the proportion of the slots in the array that are used. As the load factor increases towards 100%, the number of probes that may be required to find or insert a given key rises dramatically.

Probe sequences include:

* ``Linear`` probing
in which the interval between probes is fixed — often set to 1.

* ``Quadratic`` probing
in which the interval between probes increases linearly (hence, the indices are described by a quadratic function).

* ``Double`` hashing
in which the interval between probes is fixed for each record but is computed by another hash function.

The main tradeoffs between these methods are that linear probing has the best cache performance but is most sensitive to clustering, while double hashing has poor cache performance but exhibits virtually no clustering; quadratic probing falls in-between in both areas. Double hashing can also require more computation than other forms of probing.


# Hash functions

## Perfect hash function
Maps keys into index values (slots) without any collisions. In the worst case each lookup takes constant time.

### Minimum Perfect Hash Function

## Cuckoo hash function
The basic idea of cuckoo hashing is to resolve collisions by using two hash functions instead of only one. This provides two possible locations in the hash table for each key. In one of the commonly used variants of the algorithm, the hash table is split into two smaller tables of equal size, and each hash function provides an index into one of these two tables. Lookup requires inspection of just two locations in the hash table, which takes constant time in the worst case.

# Hash function Implementations

The following are non-crypto has functions that are very fast.

* [CLHash](https://github.com/lemire/clhash) - Library implementing fast CLHash hashing
  function that only works on Intel Haswell or newer.
* [HighwayHash](https://github.com/google/highwayhash) - Fast, strong, SIMD-using hash function. Also contains an implementation of SipHash (although this is slower).
* [SpookyHash](https://github.com/centaurean/spookyhash) - Extremely fast hash function.
* [t1ha]( https://github.com/leo-yuriev/t1ha)- Fast Positive Hash - a portable, fast hash function.
* [xxHash](https://github.com/Cyan4973/xxHash) - Extremely fast hashing algorithm. Comes in 32 and 64-bit varieties.
* [GNU gperf](https://www.gnu.org/software/gperf/) - Perfect hash function generator, given a list of strings.
