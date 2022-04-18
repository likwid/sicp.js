# Building Abstractions with Functions

## The Elements of Programming

> Primitive expressions, the simplest entities the language is concerned with
> Means of combination, by which compound elements are built from simpler ones
> Means of abstraction, by which compound elements can be named and manipulated as units

## Expressions

JS programs are made up of statements. A statement that returns a value is called an expression statement. This is a statement with an expression, followed by a semicolon. One kind of primitive expression is a number.

```
486;
486
```

Expressions representing numbers may be combined with operators (such as `+` or `*`) to form a compound expression that represents the application of a corresponding primitive function to those numbers.

```
137 + 349;
486

1000 - 334;
666

5 * 99;
495
```

Expressions that contain other expressions as components, are called _combinations_. Combinations that are formed by an _operator_ symbol in the middle, and _operand_ expressions to the left and right of the operator, are called _operator combinations_.

This is very similar to mathematics. Parentheses are used to group operator combinations to remove ambiguity. Javascript uses precedence of operators to preserve the usual conventions when parentheses are omitted. Multiplication (`*`) and division (`/`) have a higher precedence than addition (`+`) and subtraction (`-`).

```
1 - 5 / 2 * 4 + 3
```

stands for

```
(1 - ((5 / 2) * 4)) + 3;
```

## Naming and the Environment

As programmers, we need the ability to use names to refer to computational objects. Our first such means are _constants_. We say that the name identifies a constant whose _value_ is the object.

```
const size = 2;
```

Constant declarations are our simplest form of abstraction, allowing us to use simple names to refer to the result of compound operations. Associating values with names and later retrieving them means the interpreter must maintain a memory to track the name/value pairs. This is called the _program environment_.

## Evaluating Operator Combinations

##  Compound Functions

## Substitution Model for Function Application

## Conditional Expressions and Predicates

## Exercise 1.1

```
10;                           //10

5 + 3 + 4;                    //12

9 - 1;                        //8

6 / 2;                        //3

2 * 4 + (4 - 6);              //6

const a = 3;                  //undefined

const b = a + 1;              //undefined

a + b + a * b;                //19

a === b;                      //false

b > a && b < a * b ? b : a;   //4

a === 4
? 6
: b === 4
? 6 + 7 + a
: 25;                         //16

2 + (b > a ? b : a);          //6

(a > b
? a
: a < b
? b
: -1)
*
(a + 1)                       //16
```

# Exercise 1.3
> Declare a function that takes three numbers as arguments and returns the sum of the squares of the two larger numbers.

```
const square = (x) => x * x;
function one_three(a, b, c) {
    const [one, two, ...rest] = Array.from(arguments).sort((x, y) => y - x);
    return square(one) + square(two);
}

function one_three_a(...args) {
    const [one, two, ...rest] = args.sort((x, y) => y - x);
    return square(one) + square(two);
}
```