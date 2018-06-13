# Assignment 1: Constructing a Lexical Analyzer        

## Assignment Details:

Construct a lexical analyzer generator  that takes a lexer specification file mylex.l as input. The file mylex.l  contains a set of regular expressions and the corresponding tokens  where the input alphabet is ∑ = {a,b}. The analyzer should be able to  take a input string and return the lexemes that matches with the regular  expressions and the corresponding tokens.

ALTERNATIVELY, your program  Analyzer.c/Analyzer.java/Analyzer.exe can take as input the mylex.l and  the input string and produce the list of matched lexemes and tokens  output.

The regular expressions may contain the  following operators: ‘.’, ‘|’, ‘*’, ‘+’ (positive closure),?, and  symbols: () and epsilon (we will use e instead of ε) .

We will follow lex/flex’s conventions for matching
 \1. If it finds more than one match, it takes the one matching the most text
 \2. If it finds two or more matches of the same length, the rule listed first in the  mylex.l  input file is chosen.
 Also assume the input string doesn’t contain any illegal characters and  the whole input string can be divided into the token to be recognized.   Extra credit will be awarded if your lexer can handle error case –i.e,  skip illegal characters and portions of the input string that doesn’t  match with any of the regular expressions.

## Implementation

Construct DFAs from the given regular  expressions using the direct DFA construction algorithm that uses the  firstpos, lastpos, and followpos functions. You may want to convert the  regular expressions to postfix notation first and rather than creating a  tree use a stack to find the firstpos, lastpos, and followpos for each  ‘node’. You can use C/C++ or Java for implementation.

Sample input and output are given below:

### Sample mylex.l file

a+                        TOKEN1
 a|b|e).a.b*          TOKEN2
 (aa)+(bb)+         TOKEN3

### Sample input for mylex.exe

aabbbbaaaa

### Sample output for mylex.exe

aabbbb TOKEN2
 aaaa      TOKEN1

## My Solution Procedure and Source code

### How it works:

1. Convert infix regular expression to postfix regular expression
2. Find Nullablity, Firstpos, Lastpos, Followpos
3. Make DFA table from these.
4. Now Find whether any string gets accepted by these DFAs.
5. Now check the longest sequence accepted by the DFAs. That’s all about algorithm.

### Source Code : [Lexzical Analyzer ](https://github.com/Sayef/LexicalAnalyzer)

### How to run my code:

1. Add my 2 java sources to your project.
2. There is a file input.l (which is called mylex.l in the assignment  details) where actually the regular expression are written. (there is an  absolute path for the file in the code, change it for your own use)
3. Our program will analyze them and will take input from console to test whether your given string matches any regular expression
4. Initially we handled only two characters ‘a’ and ‘b’, but you can  convert it easily for any characters (see comments to understand easily)

###  Example strings as input:

```
(not regular expressions; regular expressions are given in input.l; 
offcourse you can also change/add/remove for further checking)
```

1. aab
2. abab
3. aabbb