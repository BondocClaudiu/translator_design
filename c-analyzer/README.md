## files

```
  expression.h         header file for syntax tree data structure
  expression.c         implementation of syntax tree
  lexer.l              Flex token specs
  parser.y             Bison language syntax specs
  main.c               call the Flex scanner and Bison parser
                       to make a syntax tree, then evaluate the tree
  makefile             compile everything
  README.md            you're looking at it
  LICENSE
```

## software requirements

Bison + Flex on Linux/MacOs

```
  $ /usr/local/bin/bison --version
  bison (GNU Bison) 3.0.4

  $ flex --version
  flex 2.5.35 Apple(flex-31)

  $ g++ --version
  Apple LLVM version 7.0.0 (clang-700.1.76)
  Target: x86_64-apple-darwin14.5.0
```

## running it

```
    $ make
    flex lexer.l
    /usr/local/bin/bison parser.y
    g++ -g -x c -ansi lexer.c parser.c expression.c main.c -o test

    $ ./test  # also creates tree.dot
    Result of ' 4 + 2*10 + 3*( 5 + 1 ) ' is 42

    # generate parse tree image from tree.dot
    $ dot -Tpng < tree.dot > tree.png

```

  
