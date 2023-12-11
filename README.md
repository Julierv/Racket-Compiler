## Racket Compiler

This repository contains a simple compiler and for a custom programming language implemented in Racket for the semester project of my design and implementation of Programming Languages course CMSC430.

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

## Example syntax

## cond
(cond cond-clause ...) <br>
cond-clause	 	=	 	[test-expr then-body ...+]<br>
 	 	|	 	[else then-body ...+]<br>
 	 	|	 	[test-expr => proc-expr]<br>
 	 	|	 	[test-expr]<br>
<br>
`> (cond)<br>
> (cond<br>
    [else 5])<br>
5<br>

> (cond<br>
   [(positive? -5) (error "doesn't get here")]<br>
   [(zero? -5) (error "doesn't get here, either")]<br>
   [(positive? 5) 'here])<br>
'here`

## case
(case val-expr case-clause ...) <br>
case-clause	 	=	 	[(datum ...) then-body ...+]<br>
 	 	|	 	[else then-body ...+]<br>

## if
(if test-expr then-expr else-expr) <br>

## let
(let ([id val-expr] ...) body ...+) <br>

(let proc-id ([id init-expr] ...) body ...+) <br>
