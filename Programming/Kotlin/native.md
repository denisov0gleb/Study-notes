# Working with other languages #

Created 11.12.20 by **DGL**

Modified 11.12.20 by **DGL**

[Source](https://kotlinlang.org/docs/reference/native-overview.html)

# Table of Content: #

<!-- vim-markdown-toc GFM -->

1. [Target platforms](#target-platforms)
1. [Interoperability](#interoperability)

<!-- vim-markdown-toc -->

## Target platforms ##
* iOS
* macOS
* watchOS
* tvOS
* Android
* Windows (through *mingw*)
* Linux
* WebAssembly (wasm32)

## Interoperability ##

Compiler creates:

* executable for many platforms
* static or dynamic library with C headers for C/C++ projects
* Apple framework for Swift and Objective-C projects

Can be used in Kotlin:
* static or dynamic C libraries
* C, Swift and Objective-C frameworks
