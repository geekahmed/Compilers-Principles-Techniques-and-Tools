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

## 1.3. The Evolution of Programming Languages
### Exercises for Section 1.3

## 1.4. The Science of Building a Compiler

## 1.5. Applications of Compiler Technology

## 1.6. Programming Languages Basics
### Exercises for Section 1.6