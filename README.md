# Compiler

## Introduction

Implementation of a compiler for the <a href="https://github.com/Dinista/Simple-Language-Compiler/blob/main/Docs/Simple_Language_Especification(Portuguese).pdf">Simple Language</a> in <b>C++</b>.
The primary purpose of this project is to apply the knowledge acquired in the undergraduate years, in addition to a study of how a compiler works, including lexical, syntactic, semantic builders.

Project specification and documents can be found at <i>/Docs</i> folder. 
<b>All documents are in Portuguese language.</b>

<b> Project of the Compliler class. </b>


## How it works

The <b>front-end</b> implemented contains a <b>lexical</b> builder, <b>syntactic</b> builder, <b>semantic</b> builder and <b>the intermediary <a href= "https://llvm.org/docs/LangRef.html">LLVM</a> code generator</b>. The LLVM infrastructure is used as <b>backend</b> to generate the final executable code.

We can divided the front-end process in the following topics.

#### Lexicon Analyzer

The <a href= "https://www.geeksforgeeks.org/flex-fast-lexical-analyzer-generator"/>Fast Lexical Analyzer Generator (FLEX)</a> tool, it's used for generating lexical analyzers (scanners or lexers). A specification is create for the tool where the analyzer must <b>recognize all the language tokens</b>, then the C++ code is generated.

####  Parser

The <a href="https://www.gnu.org/software/bison/">Bison</a> tool is responsable for the parser process, also is in control of determining whether a
certain program is write in the Simple Language or not. As a consequence, during grammar rules recognition, the parser generates an <b>abstract syntax tree</b>.

####  Abstract Syntax Tree

The <a href="https://en.wikipedia.org/wiki/Abstract_syntax_tree"> Abstract Syntax Tree (AST)</a> is a tree representation of the abstract syntactic structure of text. Eeach node of the tree denotes a construct occurring in the text. <b>Such structure isn't standardized for common use</b>.

####  Semantic Analyzer

The Semantic Analyzer is in charge of <b>validating the language rules</b>. The rules are specified in the <a href="https://github.com/Dinista/Simple-Language-Compiler/blob/main/Docs/Simple_Language_Especification(Portuguese).pdf">document</a>.

#### Intermediary Code Generator

A well-formed entry code is able to move forward in the compilation process, as a consequence <a href= "https://llvm.org/docs/LangRef.html">LLVM</a> will generate a intermediary code.

#### Final Code Generator

The <a href= "https://llvm.org/docs/LangRef.html">LLVM</a> infrastructure allow to generate the <b>final executable code</b> performing as an back-end, 
as it was mentioned before.

### How to use

Run:

```console
sc [-i] [-s] [-o <output>] <source.s>
```
<ul>
  <li>-i : prints the intermediary code  (fonte.ll).  <em>optional</em></li>
  <li>-s : prints the assembly code (fonte.s).  <em>optional</em></li>
  <li>-o output : generates the executable with the name "output". Otherwise the file will be called <em>a.out</em>.</li>
  <li>source : source code, whose extension is ".s".</li>
</ul>

Example:
```console
sc -o resultFile sourceCode.s
```
