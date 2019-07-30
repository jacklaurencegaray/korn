## What is Korn?
Korn is designed to be a child-friendly introductory language to programming. It makes use of common English words instead of symbols prevalent in already existing programming languages in order for kids to easily grasp the concepts of programming. By removing the extensive use of symbols and focusing on the literal meaning of the language’s syntax, Korn promotes readability and logic learning.


### I. Data Types
Several variables of the same data type can be declared in one line of code, separated by commas. Variables with the same name but of different data types are not allowed in the language.

#### a. Letter

Syntax:
Stores a single character, may it be a letter, punctuation mark, or symbol. Has a storage size of 1 byte.

Example: `letter middleInitial`

#### b. Number
Holds either positive or negative single-digit or multi-digit numbers. Has a storage size of 4 bytes.

Example: `number age, coinsLeft`

#### c. Decimal
Holds exact numerical values or decimal numbers. Has a storage size of 8 bytes.

Example: `decimal first, second`

#### d. Sentence
Stores a string of letter data types. Has a storage size of 1 byte x number of letter types in the sentence.

Example: `sentence formalGreetings`

#### e. Boolean
Stores either `true` or `false` values. Has a storage size of 1 byte.

Example: `boolean isGreen`

## II. Operations
Operations make use of the infix notation, where operators are situated between operands. In evaluating operations and expressions, all operators have the same level of precedence and rely on left to right associativity.

### Assignment
Variable declaration and assignment should be done in different lines. All assignment statements utilize the gets keyword.

Syntax: `<varName> gets <value>`
Example: `b gets 3`

Semantic:
A variable name should precede gets and either a literal, another variable, or an expression follows the gets keyword, which is then assigned to the variable.

### Arithmetic
Addition, subtraction, multiplication, and division operations are native to the language and are made possible by making use of the symbols `+`, `-`, `*`, and `/`.

Syntax:
```
<val1> + <val2> + ...
<val1> - <val2> - ...
<val1> * <val2> * ...
<val1> / <val2> / ...
```
Left and right operators should either be a `number` or a `decimal`.

Example:
```
1 + 2.0
5 + 6
```

Semantic:
Arithmetic operations are evaluated from left to right. The first operand, which may be a literal or a variable, is evaluated with the second operand and the mathematical operation dictated by the operator is performed. If there are more succeeding values to be evaluated, the result of the first evaluation serves as the first operand, and is evaluated with the next value, and so on until the last value is evaluated.

### Relational
Relational expressions are expressions that yield boolean values. They make use of the following as relational operators with their corresponding meanings:

`>` greater than			
`<` less than
`>=` greater than or equal to
`<=` less than or equal to
`is equal to` is equal to
`not equal to` is not equal to

Syntax:
```
<val1> > <val2>
<val1> < <val2>
<val1> >= <val2>
<val1> <= <val2>
<val1> is equal to <val2>
<val1> is not equal to <val2>
```

Semantic:
The first operand, which may be a literal or a variable, is evaluated with the second operand and the relational operation dictated by the operator is performed.

### Logical
Logical expressions are expressions that also yield boolean values. Logical operators include `not`, `and`, and `or`.

Syntax:
```
not expression1
expression1 and expression2
expression1 or expression2
```

Semantic:
not negates the value of the expression it is appended to. and returns a `true` value if both expressions are true; otherwise, it returns a `false`. or returns a `true` value if either one of the expressions or both of the expressions are `true`. Otherwise, it returns a `false`.

## III. Arrays
Korn supports arrays, which are collections of aggregate homogeneous elements. Different values of the same data type can be stored simultaneously under the same variable name. An array can be made out of either of the language’s primitive data types.

### Declaration

Syntax: `<dataType> <varName> from 1 to <x>`
Example: `number ages from 1 to 200`

Semantic:
An array named `<varName>` with data type `<dataType>` for its values is created. Array lower bounds always start at 1 and x is the specified upper bound of the array.

### Accessing
Syntax: `<varName>[x]`
Example:

Semantic:
A variable name followed by open and closed brackets denotes that a programmer wishes to access a certain index within the array. x is the index that the programmer wishes to access. If it is within the specified bounds, access is possible.


## IV. Boxes
Structures in Korn are referred to as boxes, and are non-primitive data definitions. A box is a construct where a collection of varied data types and information can be stored into a single variable.

Syntax:
```
box <boxName>
  <dataType> <boxMember>
  <dataType> <boxMember>
  ...
  <dataType> <boxMember>
end
```

Example:
```
box anotherBoxName
  decimal height
  sentence color
end

box objects
  anotherBoxName pencil
  sentence cuteLetter
end
```

Semantic:
The keyword box followed by `<boxName>` is used to create a structure. To include multiple members with varying data types within the box, each member’s data type must be specified, followed by its variable name. Each member must also be indented to indicate membership within the box. The end keyword denotes the end of the box definition.

### Declaration

Syntax:
`<boxName> <varName>`

Semantic:
A defined boxName followed by user-defined variable name/s is used to create a box of the specified boxName type.

### Accessing

Syntax:
`<boxName>.<boxMember>`

Example:
`anotherBoxName pencil`
`pencil.height gets 12.9`

Semantic:
Accesses `<boxName>` and then accesses one of its members.

## V. Selection Statements
Korn supports `if`, `else`, and `else if`. Scopes in the language are achieved with indentation rather than the traditional braces. Nested ifs are possible.

Syntax:
```
if <condition>:
/** do stuff **/
else if <condition>:
	/** do stuff **/
else:
	/** do stuff **/
end
```

Semantic:
The condition following the if keyword is evaluated. If true, the indented statements following it are executed. Otherwise, succeeding else if conditions (if there are any) are evaluated and the same procedure of evaluation repeats for all of them. If one of the conditions return true, the indented statements following it are executed. If none of the conditions are `true` and there exists an else statement, its indented statements are executed. The else if and else statements are optional but are always preceded by an if statement. The end keyword denotes the end of the if statement.

## VI. Multiple-Selection Statements
Korn also supports multiple-selection statements, which are achieved with the keywords when and is. The end keyword is required in every case body to signify the end of its executable body, hence control cannot flow through more than one case. The keyword for the default statement is is none. When statements only evaluate non-boolean values and literals.

Syntax:
```
when <varName>:
 is <literal>:
	 /** do stuff **/
	 end
 is <literal>:
   /** do stuff **/
   end
 is none:
  /** do stuff **/
		end
```

Semantic:
The variable after the when keyword is checked against the possible cases. The cases are preceded by the is keyword. Case bodies are closed by the end keyword, which prevents flow of control to the succeeding cases. If a case returns true, its indented statements are executed. If none of the cases return `true` and is none is present, its indented statements are executed.

## VII. Iteration

### While
Loops in this language are achieved with the `while` keyword. Loop bodies are defined by using indentation instead of curly braces. Nested whiles are possible.

Syntax:
```
while <condition>:
 /** do stuff **/
end
```

Semantic:
The condition after the while keyword is first checked. If the condition is true, the indented statements following it are executed. After all is executed, the condition is checked again. If the condition is still true, the process repeats. When the condition returns false, it exits the loop. The keyword end signifies the end of the loop.

### Do-while
Another available loop is the do-while, which uses the run and while keywords. Code written in the loop body is always executed first. Evaluation of the condition following the while keyword then determines whether or not the body of the loop should be executed again.
	
Syntax:
```
run:
 /** do stuff **/
while <condition>
```

Semantic:
The indented statements after the run keyword are executed first. After all are executed, the condition after the while keyword is checked. If the condition is true, the succeeding indented statements following the run keyword are executed. This process repeats as long the condition is true. If the condition is false, it exits the loop.

## VIII. Multi-lined Comments

Syntax:
```
/** code **/
```

### IX. Steps

Calling

Syntax:
```
do <funcName>
do <funcName> with <param1>, <param2>, ...
```

Semantic:
Steps are invoked by using the keyword do, followed by the name of the step to be called. When parameters need to be passed, calling a step can optionally be appended with a with keyword and proceeded with a list of parameters in the order of the formal parameters specified in the step’s declaration, separated by commas.

Declaration

Syntax:
```
step <stepName>:
or
step <stepName> with <param1>, ...:
 /** code **/
end
```

Semantic:
Step definitions start with the keyword step, followed by a step name, and proceeded optionally by the keyword with and the list of parameters. Statements within the step body are executed, and the step terminates afterwards. The end keyword marks the end of the step declaration.

X. Built-in Tasks
Built-in tasks are language-built tasks that come with the compiler without having to be explicitly defined by the user. Some built-in tasks include say and accept, which are reminiscent of C’s `printf` and `scanf`, respectively.

Syntax:
```
do accept with <varName>
do say with <value>
```

Example:
```
do accept with x
do say with "Hello world!
```

Semantic:
Invoking accept prompts the user for input. The input is then parsed into sentence data types and stored in the variable specified after the with keyword. Invoking say displays on the console the variable, sentence literal, or combination of both specified after the with keyword.

Example:
```
sentence name
do accept with name
do say with name
```

If need be, value parsers that are similar to Java’s parsing methods are available in the language, which are `toNum`, `toDecimal`, and `toSentence`.

Syntax:
```
<numName> gets toNum(<sentenceName>)
<decName> gets toDecimal(<numName>)
<sentenceName> gets toSentence(<numName>)
```

Semantic:
A variable or literal is passed to the built-in task and returns either a number, decimal, or sentence value, respectively.
