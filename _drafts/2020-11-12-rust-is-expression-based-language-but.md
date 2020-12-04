---
layout: article
title: "Rust is an expression-based language, but..."
description: "."
tags: [rust, design, expressions, statements]
---
Most languages these days are expression-based (aka "[expression-oriented](https://en.wikipedia.org/wiki/Expression-oriented_programming_language)").  

> "Statements are instructions that perform some action and do not return a value. Expressions evaluate to a resulting value."

From [chapter 3, section 3 of the Rust Book](https://doc.rust-lang.org/book/ch03-03-how-functions-work.html).

While Java isn't, [Rust very much is](https://doc.rust-lang.org/book/ch03-03-how-functions-work.html).

However, there are some subtleties...

# Not everything in Rust is an expression
Here's some code from [chapter 3 of the Rust Book](https://doc.rust-lang.org/book/ch03-03-how-functions-work.html#function-bodies-contain-statements-and-expressions) which won't compile:

    fn main() {
        let x = (let y = 6);
    }
    
When we try and compile, we get the following error:

    error: expected expression, found statement (`let`)

The Rust Book [explains why](https://doc.rust-lang.org/book/ch03-03-how-functions-work.html#function-bodies-contain-statements-and-expressions):

> "The let y = 6 statement does not return a value, so there isn’t anything for x to bind to. This is different from what happens in other languages, such as C and Ruby, where the assignment returns the value of the assignment. In those languages, you can write x = y = 6 and have both x and y have the value 6; that is not the case in Rust."

This came as a bit of a surprise.  What also came as a surprise was the whole thing aroung semi-colons:

> "Expressions do not include ending semicolons. If you add a semicolon to the end of an expression, you turn it into a statement, which will then not return a value. Keep this in mind as you explore function return values and expressions next."

Now that makes sense, but again there are subtlities. I _think_ that because Rust is explicitly memory-safe, it's not happy with you having things being retured from expressions willy-nilly

[My error when I make the block return the output from a statement....]

"statements don’t evaluate to a value, which is expressed by (), an empty tuple"
"Expressions can be part of statements: in Listing 3-1, the 6 in the statement let y = 6; is an expression that evaluates to the value 6. Calling a function is an expression. Calling a macro is an expression. The block that we use to create new scopes, {}, is an expression"

# One final point of note
Interestingly, when we try and compile our first code example we also get an exciting nugged of info in the error output:

    error[E0658]: `let` expressions in this position are experimental

Sounds like things might be changing sometime in the near Rust-future.
