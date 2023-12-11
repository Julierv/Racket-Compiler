## Racket Compiler

This repository contains a simple compiler and for a custom programming language implemented in Racket for the semester project of my design and implementation of Programming Languages course CMSC430.

Abstract Syntax Tree (AST) Configuration<br>
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
