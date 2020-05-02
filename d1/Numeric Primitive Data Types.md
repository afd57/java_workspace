# Numeric Primitive Data Types



**Integer Primitive Data Types**

| **Type** | **Size** | Range                                    |
| -------- | -------- | ---------------------------------------- |
| byte     | 8 bits   | -128 to +127                             |
| short    | 16 bits  | -32,768 to +32,767                       |
| int      | 32 bits  | -2 billion to +2 billion (approximately) |
| long     | 64 bits  | -9E18 to +9E18 (approximately)           |



**Floating Point Primitive Data Types**

| float  | 32 bits | -3.4E38 to +3.4E388 |
| ------ | ------- | ------------------- |
| double | 64 bits | -1.7E308 to 1.7E308 |



Is the following an integer literal? 197.0

### Answer:

No — it has a decimal point.



In source programs, floating point literals always have a decimal point in them, and **no commas** although you can used underscore to separate thousands:

```java
     123.0       
    -123.5     
 -198234.234   
-198_234.234
```



**Note:** Literals written like the above will automatically be of type `double`. Almost always, if you are dealing with floating point numbers you should use variables of type `double`. Then the data type of literals like the above will match the data type of your variables. Data type `float` should be used only for special circumstances (such as when you need to process a file of data containing 32 bit floats).



(Thought question: ) Do you think that using `float` instead of `double` saves a significant amount of computer memory?

### Answer:

No. For most programs using variables of type `double` will cost only a few extra bytes. This is insignificant in a program thousands of bytes long.



# Floating Point Literals

- Sometimes you need to explicitly ask for a single-precision `float` literal. Do this by putting a lower case `f` or upper case `F` at the end, like this:

```java
      123.0f 
        
     -123.5F
```



- Sometimes you need to explicitly ask for a `double` literal. Do this by putting a lower case `d` or upper case `D` at the end, like this:

```java
      123.0d  
       
     -123.5D 
```



> Remember, that without any letter at the end, a floating point literal will automatically be of type `double`.



- You will sometimes see **scientific notation**. The following are all double-precision literals: The big "E" means "times 10 to the power of" . The integer that follows it says what power of ten to multiply the rest of the number by.

```java
 1.23E+02
```



# The `char `Primitive Data Type

The `char` type represents a character using 16 bits. Java uses 16 bits so that a very large number of characters can be represented, nearly all of the characters in all of the World's languages. The method used is called **Unicode.**

A character literal is a single character with an apostrophe on each side:

```
'm'       'y'         'A'
```

A control character is represented with a special sequence of characters:

```
'\n'       '\t'
```



What is wrong with the following `char` literal:

```
"W"
```

### Answer:

The character is not surrounded by apostrophes. It should be: `'W'` .

With double quotes, `"W"`, you get a `String` that contains a single character.

# Names for Variables

As a matter of programming style, a name for a variable usually starts with a lower case letter. If a name for a variable is made of several words, capitalize each word except the first. For example, `payAmount` and `grandTotal`. These conventions are not required by syntax, but make programs easier to read.

### Answer:

There are some syntax errors:

```java
int myPay, yourPay; // OK

long good-by ;  // bad identifier: "-" not allowed

short shrift = 0;  // OK

double bubble = 0, toil= 9, trouble = 8 // missing ";" at end.

byte the bullet ;    // bad identifier: can't contain a space

int  double;    // bad identifier: double is a reserved word

char thisMustBeTooLong  ;   // OK in syntax, but a poor choice 
                            // for a variable name

int  8ball;    // bad identifier: can't start with a digit

float a=12.3; b=67.5; c= -45.44; // bad syntax: don't use ";" to separate variables
```



# Two Steps

FIRST, do the multiplication 2*3 to get the value 6.

> ![Do First](http://www.programmedlessons.org/Java9/chap09/doFirst.gif)

NEXT, put the result of the calculation into the "litte box of memory" used for the variable `value`:

> ![Do Second](http://www.programmedlessons.org/Java9/chap09/doSecond.gif)

It will really, really help you to think carefully about these two steps. Sometimes even second year computer science majors get confused about this and write buggy code.



# Arithmetic Operators



### QUESTION 22:

| Expression | 16 - 12 / 4 | 2 + 6 / 2 | 8 + 4*2 | 8+4 * 2 | 12/2 - 3 | 6/8 + 2 |
| ---------- | ----------- | --------- | ------- | ------- | -------- | ------- |
| Value      | 13          | 5         | 16      | 16      | 3        | 2       |

The last result is correct. First `6/8` is done using integer division, resulting in `0`. Then that `0` is added to `2`.



# Evaluate Equal Precedence from Left to Right

When there are two (or more) operators of equal precedence, evaluate the expression from left to right.

```
2 * 7 * 3 
-----
  14  * 3
  -------
     42
```

Since both operators are `*`, each has equal precedence, so calculate `2 * 7` first, then use that result with the second operator.

Here is a second example:

```
4 - 2 + 5
-----
  2   + 5
  -------
      7
```

Now the operators are different, but they both have the same precedence, so they are evaluated left to right.

Usually it doesn't matter if evaluation is done left to right or in any other order. In algebra it makes no difference. But with floating point math it sometimes makes an important difference. Also, when an expression uses a *method* it can make a very big difference. (Methods are discussed in part 6 of these notes.)



> The sources of this article is the link in the bellow.
>
> - http://www.programmedlessons.org/Java9/chap08/ch08_01.html
> - http://www.programmedlessons.org/Java9/chap09/ch09_01.html

