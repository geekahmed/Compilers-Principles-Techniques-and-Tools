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
- History is better read from the source.
### Exercises for Section 1.3
- Indicate which of the following terms: a) imperative b) declarative c) von Neumann d) ob ject-oriented e) functional f ) third-generation g) fourth-generation h) scripting apply to which of the following languages: 1) C 2) C++ 3) Cobol 4) Fortran 5) Java 6) Lisp 7) ML 8) Perl 9) Python 10) VB.
	- imperative: C, C++
	- object-oriented: C++, Java
	- functional: ML
	- scripting: Perl, Python
	- third-generation: C, C++, Fortran, Lisp, and Java.
	- von Neumann: Fortan and C

## 1.4. The Science of Building a Compiler
- Compiler design is full of beautiful examples where complicated real-world problems are solved by abstracting the essence of the problem mathematically.
	- These serve as excellent illustrations of how abstractions can be used to solve problems: take a problem, formulate a mathematical abstraction that captures the key characteristics, and solve it using mathematical techniques.
- The study of compilers is mainly a study of how we design the right mathematical models and choose the right algorithms, while balancing the need for generality and power against simplicity and efficiency.
- Compiler optimizations must meet the following design objectives:
	- The optimization must be correct, that is, preserve the meaning of the compiled program,
	- The optimization must improve the performance of many programs,
	- The compilation time must be kept reasonable, and
	- The engineering effort required must be manageable.
## 1.5. Applications of Compiler Technology
- Implementation of High-Level Programming Languages
	- A high-level programming language defines a programming abstraction: the programmer expresses an algorithm using the language, and the compiler must translate that program to the target language.
- Optimizations for Computer Architectures
	- Almost all high-performance systems take advantage of the same two basic techniques: parallelism and memory hierarchies.
- Design of New Computer Architectures
	- in modern computer architecture development, compilers are developed in the processor-design stage, and compiled code, running on simulators, is used to evaluate the proposed architectural features.
- Program Translations
	- While we normally think of compiling as a translation from a high-level language to the machine level, the same technology can be applied to translate between different kinds of languages.
- Software Productivity Tools.
## 1.6. Programming Languages Basics
- The Static/Dynamic Distinction
	- If a language uses a policy that allows the compiler to decide an issue, then we say that the language uses a static policy or that the issue can be decided at compile time.
	- A policy that only allows a decision to be made when we execute the program is said to be a dynamic policy or to require a decision at run time.
	- The scope of a declaration of x is the region of the program in which uses of x refer to this declaration.
		- A language uses static scope or lexical scope if it is possible to determine the scope of a declaration by looking only at the program.
		- Otherwise, the language uses dynamic scope. With dynamic scope, as the program runs, the same use of x could refer to any of several different declarations of x.
- Environments and States
	- The environment is a mapping from names to locations in the store.
	- The state is a mapping from locations in store to their values.
	- Environments change according to the scope rules of a language.
	- Static versus dynamic binding of names to locations.
		- Most binding of names to locations is dynamic.
	- Static versus dynamic binding of locations to values.
		- The binding of locations to values is generally dynamic as well, since we cannot tell the value in a location until we run the program.
		- Declared constants are an exception.
	- Names, Identifiers, and Variables.
		- An identifier is a string of characters, typically letters or digits, that refers to (identifies) an entity, such as a data ob ject, a procedure, a class, or a type.
		- All identifiers are names, but not all names are identifiers.
		- Names can be expressions.
			- For example, the name x.y might denote the field y of a structure denoted by x. Here, x and y are identifiers, while x.y is a name, but not an identifier.
			- Composite names like x:y are called qualified names.
		- A variable refers to a particular location of the store.
- Static Scope and Block Structure
	- A C program consists of a sequence of top-level declarations of variables and functions.
	- Functions may have variable declarations within them, where variables include local variables and parameters. The scope of each such declaration is restricted to the function in which it appears.
	- The scope of a top-level declaration of a name x consists of the entire program that follows, with the exception of those statements that lie within a function that also has a declaration of x.
	- Blocks in a C++ program
	- ![Blocks in c plus plus](https://github.com/geekahmed/Compilers-Principles-Techniques-and-Tools/blob/main/01.%20Introduction/Images/Blocks-in-c.png?raw=true)
- Explicit Access Control
	- Classes and structures introduce a new scope for their members.
	- If p is an object of a class with a field (member) x, then the use of x in p.x refers to field x in the class definition.
- Dynamic Scope
	- The term dynamic scope refers to the following policy: a use of a name x refers to the declaration of x in the most recently called, not-yet-terminated, procedure with such a declaration.
	- Declarations tell us about the types of things, while definitions tell us about their values. Thus, int i is a declaration of i, while i = 1 is a definition of i.
	- While there could be any number of static or dynamic policies for scoping, there is an interesting relationship between the normal (block-structured) static scoping rule and the normal dynamic policy.
		- In a sense, the dynamic rule is to time as the static rule is to space.
		- While the static rule asks us to find the declaration whose unit (block) most closely surrounds the physical location of the use, the dynamic rule asks us to find the declaration whose unit (procedure invocation) most closely surrounds the time of the use.
- Parameter Passing Mechanisms
	- There is three ways for parameter passing, "call-by-value," "call-by-reference," and "call-by-name".
	- In call-by-value, the actual parameter is evaluated (if it is an expression) or copied (if it is a variable).
	- In call-by-reference, the address of the actual parameter is passed to the callee as the value of the corresponding formal parameter.
- Aliasing
	- It is possible that two formal parameters can refer to the same location; such variables are said to be aliases of one another.
### Exercises for Section 1.6
- For the block-structured C code of the following figure, indicate the values assigned to w, x, y, and z.
- 

    int w, x, y, z;
    int i = 4; int j = 5;
    {
      int j = 7;
      i = 6;
      w = i + j;
    }
    x = i + j;
    {
      int i = 8;
      y = i + j;
    }
    z = i + j;
**w = 13, x = 11, y = 13, z = 11.**
- Repeat Exercise 1.6.1 for the code of the following.
- 

    int w, x, y, z;
    int i = 3; int j = 4;
    {
      int i = 5;
      w = i + j;
    }
    x = i + j;
    {
      int j = 6;
      i = 7;
      y = i + j;
    }
    z = i + j;
**w = 9, x = 7, y = 13, z = 11.**
- For the block-structured code of Fig. 1.14, assuming the usual static scoping of declarations, give the scope for each of the twelve declarations.
{
int w, x, y, z; Block B1 
{ int x, z; Block B2
{ int w, x; Block B3
} 
} 
{ 
int w, x; Block B4 
{int y, z; Block B5 }
} 
}

```
Block B1:
    declarations:  ->   scope
        w                B1-B3-B4
        x                B1-B2-B4
        y                B1-B5
        z                B1-B2-B5
Block B2:
    declarations:  ->   scope
        x                B2-B3
        z                B2
Block B3:
    declarations:  ->   scope
        w                B3
        x                B3
Block B4:
    declarations:  ->   scope
        w                B4
        x                B4
Block B5:
    declarations:  ->   scope
        y                B5
        z                B5
```


- What is printed by the following C code?
- 

    #define a (x + 1)
    int x = 2;
    void b() { x = a; printf("%d\n", x); }
    void c() { int x = 1; printf("%d\n", a); }
    void main () { b(); c(); }
**3**

**2**