# Chapter 1. Introduction
> Programming languages are notations for describing computations to people and to machines. The software systems that do this translation are called ***compilers***.
## 1.1. Language Processors
- A compiler is a program that can read a program in one language -the source language- and translate it into an equivalent program in another language -the target language-.
- An important role of the compiler is to report any errors in the source program that it detects during the translation process.
- An interpreter is another common kind of language processor.
	- Instead of producing a target program as a translation, an interpreter appears to directly execute the operations specified in the source program on inputs supplied by the user.
- The machine-language target program produced by a compiler is usually much faster than an interpreter at mapping inputs to outputs.
- An interpreter can usually give better error diagnostics than a compiler, because it executes the source program statement by statement.
- Java language processors combine compilation and interpretation.
	- A Java source program may first be compiled into an intermediate form called bytecodes.
	- The bytecodes are then interpreted by a virtual machine.
- A source program may be divided into modules stored in separate files.
	- The task of collecting the source program is sometimes entrusted to a separate program, called a preprocessor.
- The assembly language is then processed by a program called an assembler that produces relocatable machine code as its output.
- Large programs are often compiled in pieces, so the relocatable machine code may have to be linked together with other relocatable object files and library files into the code that actually runs on the machine.
	- The linker resolves external memory addresses, where the code in one file may refer to a location in another file.
	- The loader then puts together all of the executable object files into memory for execution.
### Exercises for Section 1.1
- What is the difference between a compiler and an interpreter?
	- A compiler translates a source program into a target program.
	- An interpreter executes the source program along with an input from the user in statement by statment manner.
- What are the advantages of (a) a compiler over an interpreter (b) an interpreter over a compiler?
	- The produced machine-dependent code from the compiler is much faster.
	- An interpreter gives better error diagnostics than a compiler, because it executes the source program statement by statement.
- What advantages are there to a language-processing system in which the compiler produces assembly language rather than machine language?
	- The compiler may produce an assembly-language program as its output, because assembly language is easier to produce as output and is easier to debug.
- A compiler that translates a high-level language into another high-level language is called a source-to-source translator. What advantages are there to using C as a target language for a compiler?
	- C compilers are available for any platform.
	- C compilers can agressively optimize.
	- C language is easier to understand than any "proprietary" intermediate language.
- Describe some of the tasks that an assembler needs to perform.
	- The assembly language is processed by a program called an assembler that produces relocatable machine code as its output.
## 1.2. The Strucutre of a Compiler
- The analysis part breaks up the source program into constituent pieces and imposes a grammatical structure on them.
- The synthesis part constructs the desired target program from the intermediate representation and the information in the symbol table.
- The first phase of a compiler is called lexical analysis or scanning.
	- The lexical analyzer reads the stream of characters making up the source program and groups the characters into meaningful sequences called lexemes.
	- For each lexeme, the lexical analyzer produces as output a token of the form `<token-name; attribute-value>` that it passes on to the subsequent phase, syntax analysis.
- The second phase of the compiler is syntax analysis or parsing.
	- The parser uses the first components of the tokens produced by the lexical analyzer to create a tree-like intermediate representation that depicts the grammatical structure of the token stream.
	- A typical representation is a syntax tree in which each interior node represents an operation and the children of the node represent the arguments of the operation.
- The semantic analyzer uses the syntax tree and the information in the symbol table to check the source program for semantic consistency with the language defnition.
	- An important part of semantic analysis is type checking, where the compiler checks that each operator has matching operands.
- After syntax and semantic analysis of the source program, many compilers generate an explicit low-level or machine-like intermediate representation, which we can think of as a program for an abstract machine.
	- This intermediate representation should have two important properties: it should be easy to produce and it should be easy to translate into the target machine.
- The machine-independent code-optimization phase attempts to improve the intermediate code so that better target code will result.
- The code generator takes as input an intermediate representation of the source program and maps it into the target language.
- Symbol table is an essential function of a compiler is to record the variable names used in the source program and collect information about various attributes of each name.
	- The symbol table is a data structure containing a record for each variable name, with fields for the attributes of the name.
	- The data structure should be designed to allow the compiler to find the record for each name quickly and to store or retrieve data from that record quickly.
- In an implementation, activities from several phases may be grouped together into a pass that reads an input file and writes an output file.
- Some commonly used compiler-construction tools include:
	- Parser generators that automatically produce syntax analyzers from a grammatical description of a programming language.
	- Scanner generators that produce lexical analyzers from a regular-expression description of the tokens of a language.
	- Syntax-directed translation engines that produce collections of routines for walking a parse tree and generating intermediate code.
	- Code-generator generators that produce a code generator from a collection of rules for translating each operation of the intermediate language into the machine language for a target machine.
	- Data-flow analysis engines that facilitate the gathering of information about how values are transmitted from one part of a program to each other part. Data-ow analysis is a key part of code optimization.
	- Compiler-construction toolkits that provide an integrated set of routines for constructing various phases of a compiler.
## 1.3. The Evolution of Programming Languages
### Exercises for Section 1.3

## 1.4. The Science of Building a Compiler

## 1.5. Applications of Compiler Technology

## 1.6. Programming Languages Basics
### Exercises for Section 1.6