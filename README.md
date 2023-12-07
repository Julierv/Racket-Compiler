# Racket-Compiler
Making my final project for CMSC430 available, I made a compiler using Racket

AST confuguration:
type Fun = (FunPlain [Listof Id] Expr)
         | (FunRest [Listof Id] Id Expr)
         | (FunCase [Listof FunCaseClause])
type FunCaseClause = (FunPlain [Listof Id] Expr)
                   | (FunRest [Listof Id] Id Expr)

type Expr = (Eof)
          | (Empty)
          | (Int Integer)
          | (Bool Boolean)
          | (Char Character)
          | (Str String)
          | (Prim0 Op0)
          | (Prim1 Op1 Expr)
          | (Prim2 Op2 Expr Expr)
          | (Prim3 Op3 Expr Expr Expr)
          | (If Expr Expr Expr)
          | (Begin Expr Expr)
          | (Let Id Expr Expr)
          | (Var Id)
          | (App Id (Listof Expr))
          | (Apply Id (Listof Expr) Expr)
type Id   = Symbol
type Op0  = 'read-byte
type Op1  = 'add1 | 'sub1 | 'zero?
          | 'char? | 'integer->char | 'char->integer
          | 'write-byte | 'eof-object?
          | 'box | 'car | 'cdr | 'unbox
          | 'empty? | 'cons? | 'box?
          | 'vector? | vector-length
          | 'string? | string-length
type Op2  = '+ | '- | '< | '=
          | 'cons | 'eq?
          | 'make-vector | 'vector-ref
          | 'make-string | 'string-ref
type Op3  = 'vector-set!
