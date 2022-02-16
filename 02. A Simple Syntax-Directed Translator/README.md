# Chapter 2.  A Simple Syntax-Directed Translator
## 2.1. Introduction
- Analysis is organized around the "syntax" of the language to be compiled.
- The syntax of a programming language describes the proper form of its programs.
- The semantics of a programming language defines what its programs mean; that is, what each program does when it executes.
- Context-free grammars or BNF are widely used notations in specifying the syntax.
- A model of a compiler front end
"Image of compiler front end model:
- A lexical analyzer allows a translator to handle multicharacter constructs like identifiers, which are written as sequences of characters, but are treated as units called tokens during syntax analysis.
- There are two forms of intermediate code:
	- Abstract syntax trees: represent the hierarchical syntactic of the source program.
	- Three address code: This form of intermediate code takes its name from instructions of the form x = y op z, where op is a binary operator, y and z are the addresses for the operands, and x is the address for the result of the operation.
## 2.2. Syntax Definition
### Definition of Grammars
### Derviations
### Parse Trees
### Ambiguity
### Associativity of Operators
### Precedence of Operators
### Exercises for Section 2.2