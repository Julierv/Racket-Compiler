Racket Compiler
This repository contains a simple compiler and for a custom programming language implemented in Racket for the semester project of my design and implementation of Programming Languages course CMSC430.

Abstract Syntax Tree (AST) Configuration<br>
Fun<br>
(FunPlain [Listof Id] Expr)<br>
(FunRest [Listof Id] Id Expr)<br>
(FunCase [Listof FunCaseClause])<br>
FunCaseClause<br>
(FunPlain [Listof Id] Expr)<br>
(FunRest [Listof Id] Id Expr)
Expr
(Eof)
(Empty)
(Int Integer)
(Bool Boolean)
(Char Character)
(Str String)
(Prim0 Op0)
(Prim1 Op1 Expr)
(Prim2 Op2 Expr Expr)
(Prim3 Op3 Expr Expr Expr)
(If Expr Expr Expr)
(Begin Expr Expr)
(Let Id Expr Expr)
(Var Id)
(App Id (Listof Expr))
(Apply Id (Listof Expr) Expr)
Types
Id: Symbol
Op0: 'read-byte
Op1: 'add1 | 'sub1 | 'zero? | 'char? | 'integer->char | 'char->integer | 'write-byte | 'eof-object? | 'box | 'car | 'cdr | 'unbox | 'empty? | 'cons? | 'box? | 'vector? | vector-length | 'string? | string-length
Op2: '+ | '- | '< | '= | 'cons | 'eq? | 'make-vector | 'vector-ref | 'make-string | 'string-ref
Op3: 'vector-set!
