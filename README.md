# Compilers: Principles, Techniques, and Tools
Summary and exercises for the well-known book Compilers: Principles, Techniques, and Tools by Alfred V. Aho, Monica S. Lam, Ravi Sethi, and Jeffrey D. Ullman about compiler construction for programming languages.

Contributions: Issues, comments and pull requests are super welcome.

## Book Description
**Chapter 1** contains motivational material and also presents some background issues in computer architecture and programming-language principles.

**Chapter 2** develops a miniature compiler and introduces many of the important concepts, which are then developed in later chapters. The compiler itself appears in the appendix.

**Chapter 3** covers lexical analysis, regular expressions, nite-state machines, and scanner-generator tools. This material is fundamental to text-processing of all sorts.

**Chapter 4** covers the ma jor parsing methods, top-down (recursive-descent, LL) and bottom-up (LR and its variants).

**Chapter 5** introduces the principal ideas in syntax-directed denitions and syntax-directed translations.

**Chapter 6** takes the theory of Chapter 5 and shows how to use it to generate intermediate code for a typical programming language.

**Chapter 7** covers run-time environments, especially management of the run-time stack and garbage collection.

**Chapter 8** is on ob ject-code generation. It covers construction of basic blocks, generation of code from expressions and basic blocks, and register-allocation techniques.

**Chapter 9** introduces the technology of code optimization, including ow graphs, data-ow frameworks, and iterative algorithms for solving these frameworks.

**Chapter 10** covers instruction-level optimization. The emphasis is on the extraction of parallelism from small sequences of instructions and scheduling them on single processors that can do more than one thing at once.

**Chapter 11** talks about larger-scale parallelism detection and exploitation. Here, the emphasis is on numeric codes that have many tight loops that range over multidimensional arrays.

**Chapter 12** is on interprocedural analysis. It covers pointer analysis, aliasing, and data-ow analysis that takes into account the sequence of procedure calls that reach a given point in the code.

## MOOCS
Ghassan Shobaki: https://www.youtube.com/playlist?list=PL6KMWPQP_DM97Hh0PYNgJord-sANFTI3i

Compilers from Stanford (CS143): https://www.youtube.com/playlist?list=PLoCMsyE1cvdUZRe1udlyjpzTww1U5olL2

## Table of Content
- [Chapter 1. Introduction](#)
- [Chapter 2. A Simple Syntax-Directed Translator](#)
