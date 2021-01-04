# Kotlin basics #

Created 11.12.20 by **DGL**

Modified 11.12.20 by **DGL**

[Source](https://kotlinlang.org/docs/reference/)

# Table of Content: #

<!-- vim-markdown-toc GFM -->

1. [Compiling from console](#compiling-from-console)
1. [Native compilation from console](#native-compilation-from-console)

<!-- vim-markdown-toc -->

## Compiling from console ##
[Table of Content](#table-of-content)

Use JVM:

```
// Compile for JVM
kotlinc hello.kt -include-runtime -d hello.jar

// Execute
java -jar hello.jar
```

## Native compilation from console ##
[Table of Content](#table-of-content)

Need `Kotlin-native`:

```
// Compile native
kotlinc-native hello.kt -o hello

// Execute
hello.exe
```

