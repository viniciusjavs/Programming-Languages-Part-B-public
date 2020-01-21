Acknowledgment: This concise list was contributed by Charilaos Skiadas.

**Notes on material:**

- Always use ```#lang racket``` at the top of the file.
- Need ```(provide (all-defined-out))``` near the top.
- Comments start with a semicolon, go to end of line.
- Many things have the form ```(a b c ...)``` where first term is operator, the rest are the arguments.
- Use ```define``` to define new variables.
- ```lambda``` similar to ML's ```fn```.
- Some arithmetic operations can take any number of arguments.
- Two ways to define functions: ```(define f (lambda (x) body))``` or ```(define (f x) body)```. Most often use the latter. They mean the same thing.
- if-then-else is ```(if eTest eThen eElse)```.
- Parentheses _ALWAYS_ matter in Racket! (Adding "extra" parentheses changes the meaning.)
- List operations named differently:
	- ```[] -> null```,
	- ```:: -> cons```,
	- ```hd -> car```,
	- ```tl -> cdr```,
	- ```null -> null?```.
	Can also use ```'()``` instead of ```null```.
- The library function ```list``` is convenient for making lists: ```(list 4 2 1 2 ...)```.
- Hyphens are allowed in variable names. It is conventional to use them as separators (rather than ```_```).
- ```true -> #t```, ```false -> #f```.
- In conditionals, anything other than ```#f``` is "truthy" (so empty lists, empty strings, 0, etc. are all "true").
- Can use square brackets instead of parentheses.
- Let expressions: ```(let ([x1 e1] [x2 e2] [x3 e3]) body)```.
- Variety of let expressions, with different semantics (```let```, ```let*```, ```letrec```, ```define```).
- Top-level bindings can refer to later bindings, but do so only inside functions (so they don't actually get used until after they have been defined).
- Mutation allowed via ```set!``` -- essentially an assignment. (Should only be used when really appropriate.)
- ```cons``` makes pairs. ```#1 -> car```, ```#2 -> cdr```.
- Documentation for pairs and list: [http://docs.racket-lang.org/reference/pairs.html](http://docs.racket-lang.org/reference/pairs.html).
- A list is just nested pairs (made with ```cons```) ending with a ```cdr``` of ```null```.
- Use thunks to delay evaluation of expressions.
- Be careful not to evaluate thunks too soon when defining streams.
- Memoization: Store previous results and reuse on same input to avoid recomputation.
- ```begin``` used to sequentially group expressions (useful in conjunction with ```set!```).

**Notes on homework:**

- Because Section 4 in Part A had no homework, this module is Section _5_ but with Homework _4_. This "lag" will continue for the next module and through Part C.
- Some questions expect you to look up and use specific Racket library functions. Do so!
- ```funny-number-stream``` needs to be the stream (i.e. the thunk), not a function that would return the stream. Same for ```dan-then-dog```.
- In problems 9 and 10, when searching in the vector/list, you need to return the whole pair, not just the cdr.
- Test your functions! A lot.
- Extra parentheses are _NEVER OKAY_. Be careful to use only where needed.
- Remember that you cannot write arithmetic the "normal" way.

**Racket forms for common tasks:**

Defining a function:
```
(define (f x y) body)

(define (f x y)
   body)

(define f (lambda (x y) body))

; no-argument function:
(define (f) body)
(define f (lambda () body))
```

Let expressions:
```
(let ([x1 e1]
      [x2 e2]
      [f1 (lambda (x) body)])
   letBody))
```

If expressions:
```
(if testExp
    thenExp
    elseExp)
```

Cond expressions:
```
(cond [test1 exp1]
      [test2 exp2]
      [test3 exp3]
      [#t expDefault])
```
