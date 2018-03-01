+++
# This is the frontmatter on all post when you create using:
#  hugo new post/test.md

date = 2018-02-27T15:41:51-05:00
draft = false

title = "C Programming Resources"
summary = "List of projects and resources written in the C programming language."

# Optional external URL for project (replaces project detail page).
external_link = ""

# Does the project detail page use math formatting?
math = false

# Does the project detail page use source code highlighting?
highlight = true

# Tags and categories
# For example, use `tags = []` for no tags, or the form `tags = ["A Tag", "Another Tag"]` for one or more tags.
tags = ["Programming" , "C"]
categories = []

# Featured image
# Place your image in the `static/img/` folder and reference its filename below, e.g. `image = "example.jpg"`.
# Use `caption` to display an image caption.
#   Markdown linking is allowed, e.g. `caption = "[Image credit](http://example.org)"`.
# Set `preview` to `false` to disable the thumbnail in listings.
[header]
image = ""
caption = ""
preview = true

+++

This post aims to list projects and resources written in the C programming language. It will attempt to breakdown the into functional components that are very useful in creating a project from scratch using Open source code.  



## Contents ##

* [Build Tools](#build-tools)
* [Compilers](#compilers)
* [Compression](#compression)
* [Concurrency and Parallelism](#concurrency-and-parallelism)
* [Crypto](#crypto)
* [Data Structures](#data-structures)
* [Frameworks](#frameworks)
* [Memory Management](#memory-management)
* [Serialization](#serialization)


## Build Tools ##

Tools that automate the building and testing of projects in C.

* [CMake](https://cmake.org/) - Cross-platform family of tools designed to build, package and test
  software.
* [GNU Make](https://www.gnu.org/software/make/) - Tool which controls the generation of executables and other
  non-source files of a program.
* [Libtool](https://gnu.org/software/libtool/) - Generic library support script. Libtool hides the complexity of using shared libraries behind a consistent, portable interface.

## Compilers ##

Compilers, as well as compiler- and compilation-related tooling.

* [Clang](https://clang.llvm.org/) - Compiler for LLVM. Supports C11.
* [distcc](https://github.com/distcc/distcc) - Program that allows builds to be distributed among several machines.
* [GCC](https://gcc.gnu.org/) - Provides a C compiler as part of its compiler set. Supports C11.

## Compression ##

* [blosc](http://blosc.org/pages/blosc-in-depth) -  A high performance meta-compressor optimized for binary data.  It has been designed to transmit data to the processor cache faster than the traditional, non-compressed,  direct memory fetch approach via a memcpy OS call.
* [CRoaring](https://github.com/RoaringBitmap/CRoaring) - C implementation of [Roaring bitmaps](http://roaringbitmap.org/).
* [DENSITY](https://github.com/centaurean/density) - Super-fast compression library.
* [fast\_zlib](https://github.com/gildor2/fast_zlib) - Improved zlib, which runs 2 to 10 times faster.
* [huffandpuff](https://github.com/adamierymenko/huffandpuff) - Minimal Huffman encoder and decoder.
* [libvbyte](https://github.com/cruppstahl/libvbyte) - A fast implementation for varbyte 32bit/64bit integer compression - see [Upscaledb](https://upscaledb.com/)
* [lz4](http://lz4.github.io/lz4/) - Library for an extremely fast compression algorithm.
* [StreamVByte](https://github.com/lemire/streamvbyte) - An integer compression technique that applies SIMD instructions (vectorization) to Google's Group Varint approach.
* [TurboPFor](https://github.com/powturbo/TurboPFor) - Fastest integer compression.
* [Zstandard](http://facebook.github.io/zstd/) - Fast, lossless compression algorithm, targeting real-time compression scenarios at zlib-level or better compression ratios.

## Concurrency and Parallelism ##

* [Concurrency Kit](https://github.com/concurrencykit/ck.git) - Concurrency primitives, safe memory reclamation mechanisms and non-blocking data structures for the research, design and implementation of high performance concurrent systems.
* [libhl](https://github.com/xant/libhl) - A fast C library implementing a thread-safe API to manage hash-tables, linked lists, lock-free ring buffers and queuesLibrary implementing a thread-safe API to manage a range of data.
* [liburcu](http://liburcu.org/) - Userspace RCU (read-copy-update) library. This data synchronization library provides read-side access which scales linearly with the number of cores.
* [mill](http://libmill.org/) - Go-style concurrency that can execute up to 20 million coroutines and 50 million context switches per second.
* [pthreads](https://en.wikipedia.org/wiki/POSIX_Threads)- POSIX thread library.

## Crypto ##

Mostly library implementations of well-known cryptographic algorithms or protocols.

* [GnuTLS]([http://www.gnutls.org/) - Secure communication library, implementing SSL, TLS and DTLS protocols.
* [OpenSSL](https://www.openssl.org/) - A full-featured toolkit for the Transport Layer Security (TLS) and Secure Sockets Layer (SSL) protocols. It is also a general-purpose cryptography library.
* [liboqs](https://openquantumsafe.org/) - Library for quantum-resistant cryptographicl algorithms.
* [libsodium](https://github.com/jedisct1/libsodium) - Modern and easy-to-use crypto library.
* [MIRACL]( https://github.com/miracl/MIRACL) - Cryptographic SDK: Multiprecision Integer and Rational Arithmetic Cryptographic Library is a library that is regarded as the gold standard open source SDK for elliptic curve cryptography (ECC).
* [s2n](https://github.com/awslabs/s2n) - C99 implementation of the TLS/SSL protocols, designed to be simple, fast and with security as a priority.
* [trezor-crypto](https://github.com/trezor/trezor-crypto) - Heavily-optimized crypto algorithms for embedded devices.


## Data Structures ##

* [C Algorithms](https://github.com/fragglet/c-algorithms) - A collection of common data structures and algorithms.
* [Collections-C](https://github.com/srdja/Collections-C) - Library of generic data structures.
* [libavl](http://adtinfo.org/libavl.html/index.html) - Library containing a range of self-balancing binary trees.K
* [liblfds]( http://liblfds.org/) - Portable lock-free data structure library that are process, thread and interrupt safe, never sleep, operate without context switches, cannot fail, perform and scale literally orders of magnitude better than locking data structures.
* [libsrt](https://github.com/faragon/libsrt) - Soft and hard real-time data structures.
* [klib](https://github.com/attractivechaos/klib) - Small and lightweight implementations of common algorithms and data structures.

## Frameworks ##

The frameworks are libraries that provide data structures and other stuff you expect of a 'modern' standard library.

* [APR](http://apr.apache.org/) - Apache Portable Runtime; a highly portable library that is at the heart of Apache HTTP Server 2.x. APR has many uses, including access to advanced IO functionality (such as sendfile, epoll and OpenSSL), OS level functionality (random number generation, system status, etc), and native process handling (shared memory, NT pipes and Unix sockets).another library of cross-platform utility.
* [qlibc](https://github.com/wolkykim/qlibc) -  Simple and powerful general purpose C/C++ library that includes all kinds of containers and general library routines.
* [libcoap](https://github.com/obgm/libcoap) - Implementation of the [Constrained Application Protocol](http://coap.technology/) used to define Internet of Things (IoT).
* [libPhenom](https://github.com/facebook/libphenom) - Eventing framework for building high-scalability and high-performance systems. Uses Concurrency Kit.

* [libsvx](https://github.com/caikelun/libsvx) - A pure C network library that uses the reactor pattern whereby callback functions can be executed when a specific event occurs.
* [rDSN](https://github.com/Microsoft/rDSN) - framework for quickly building robust distributed systems. It has a microkernel for pluggable components, including applications, distributed frameworks, devops tools, and local runtime/resource providers, enabling their independent development and seamless integration.
* [nuklear](https://github.com/vurtun/nuklear) - A single-header ANSI C gui library.
* [TBOX](https://github.com/waruqi/tbox) - Multi-platform library with a large number of capabilities.


## Memory Management ##

* [Lockless Memory Allocator](https://locklessinc.com/) - Efficient memory allocator using lock-free echniques to minimize latency and memory contention.
* [rpmalloc](https://github.com/rampantpixels/rpmalloc) - Lock free thread caching, fast memory allocator, naturally aligned on 32-byte boundaries.

## Serialization ##

* [binn](https://github.com/liteserver/binn) - Binary serialization format, which is compact and fast.
* [cmp](https://github.com/camgunz/cmp) - Implementation of the [MessagePack](https://msgpack.org/) serialization protocol.
* [flatcc](https://github.com/dvidelabs/flatcc) - Compiler and library for Google's [FlatBuffers](https://google.github.io/flatbuffers/)
* [libavro](https://avro.apache.org/)] - Implementation of the Apache Avro data serialization system.
* [mpack](https://github.com/ludocode/mpack) - Implementation of the [MessagePack](https://msgpack.org/) serialization protocol.
* [OPIC](https://github.com/dryman/opic) - Object Persistence in C; Unlike traditional approaches which walk through the in-memory objects and write it to disk, OPIC itself is a memory allocator where all the objects created are backed by a memory mapped file.
* [protobuf-c](https://github.com/protobuf-c/protobuf-c) - Implementation of Google Protocol Buffer.
