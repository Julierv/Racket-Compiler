## Racket Compiler

This repository contains a simple compiler and for a custom programming language implemented in Racket for the semester project of my design and implementation of Programming Languages course CMSC430. The compiler attemps to imitate the Racket compiler almost identically with some modifications like adding recursion to let in let-rec, all implemented in assembly x86. My roll in the project was implementing the Parsing, Checking, and Generating the code into asembly x86, the link files were probided by the course instructor.

- [Examples](#Examples)
- [Abstract Syntax Tree (AST) Configuration](#AbstractSyntaxTree(AST)Configuration)

## Examples

## cond
(cond cond-clause ...) <br>
cond-clause	 	=	 	[test-expr then-body ...+]<br>
 	 	|	 	[else then-body ...+]<br>
 	 	|	 	[test-expr => proc-expr]<br>
 	 	|	 	[test-expr]<br>
<br>

`> (cond)`<br>
`> (cond`<br>
`    [else 5])`<br>
`5`<br>
`> (cond<br>`<br>
`   [(positive? -5) (error "doesn't get here")]`<br>
`   [(zero? -5) (error "doesn't get here, either")]`<br>
`   [(positive? 5) 'here])`<br>
`'here`<br>

## case
(case val-expr case-clause ...) <br>
case-clause	 	=	 	[(datum ...) then-body ...+]<br>
 	 	|	 	[else then-body ...+]<br>

`> (case (+ 7 5)`<br>
`   [(1 2 3) 'small]`<br>
`   [(10 11 12) 'big])`<br>
`'big`<br>
`> (case (- 7 5)`<br>
`   [(1 2 3) 'small]`<br>
`   [(10 11 12) 'big])`<br>
`'small`<br>

## if
(if test-expr then-expr else-expr) <br>

`> (if (positive? -5) (error "doesn't get here") 2)`<br>
`2`<br>
`> (if (positive? 5) 1 (error "doesn't get here"))`<br>
`1`<br>
`> (if 'we-have-no-bananas "yes" "no")`<br>
`"yes"`<br>

## let
(let ([id val-expr] ...) body ...+) <br>

(let proc-id ([id init-expr] ...) body ...+) <br>

`> (let ([x 5]) x)`<br>
`5`<br>
`> (let ([x 5])`<br>
`    (let ([x 2]`<br>
`          [y x])`<br>
`      (list y x)))`<br>
`'(5 2)`<br>

## Abstract Syntax Tree (AST) Configuration

Fun<br>
(FunPlain [Listof Id] Expr)<br>
(FunRest [Listof Id] Id Expr)<br>
(FunCase [Listof FunCaseClause])<br>
FunCaseClause<br>
(FunPlain [Listof Id] Expr)<br>
(FunRest [Listof Id] Id Expr)<br>
Expr<br>
(Eof)<br>
(Empty)<br>
(Int Integer)<br>
(Bool Boolean)<br>
(Char Character)<br>
(Str String)<br>
(Prim0 Op0)<br>
(Prim1 Op1 Expr)<br>
(Prim2 Op2 Expr Expr)<br>
(Prim3 Op3 Expr Expr Expr)<br>
(If Expr Expr Expr)<br>
(Begin Expr Expr)<br>
(Let Id Expr Expr)<br>
(Var Id)<br>
(App Id (Listof Expr))<br>
(Apply Id (Listof Expr) Expr)<br>
Types<br>
Id: Symbol<br>
Op0: 'read-byte<br>
Op1: 'add1 | 'sub1 | 'zero? | 'char? | 'integer->char | 'char->integer | 'write-byte | 'eof-object? | 'box | 'car | 'cdr | 'unbox | 'empty? | 'cons? | 'box? | 'vector? | vector-length | 'string? | string-length<br>
Op2: '+ | '- | '< | '= | 'cons | 'eq? | 'make-vector | 'vector-ref | 'make-string | 'string-ref<br>
Op3: 'vector-set!<br>
