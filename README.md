# Compiler

## Introduction

Implementation of a compiler for the <a href="https://github.com/Dinista/Simple-Language-Compiler/blob/main/Docs/Simple_Language_Especification(Portuguese).pdf">Simple Language</a> in <b>C++</b>.
The primary purpose of this project is to apply the knowledge acquired in the undergraduate years, in addition to a study of how a compiler works, including lexical, syntactic, semantic builders.

Project specification and documents can be found at <i>/Docs</i> folder. 
<b>All documents are in Portuguese language.</b>

<b> Project of the Compliler class. </b>


## Simple Language



## How it works

The <b>front-end</b> implemented contains a <b>lexical</b> builder, <b>syntactic</b> builder, <b>semantic</b> builder and <b>the intermediary <a href= "https://llvm.org/docs/LangRef.html">LLVM</a> code generator</b>. The LLVM infrastructure is used as <b>backend</b> to generate the final executable code.

We can divided the front-end process in the following topics.

#### Lexicon Analyzer
