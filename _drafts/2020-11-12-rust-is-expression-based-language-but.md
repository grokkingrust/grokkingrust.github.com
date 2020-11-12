Title: Rust is an expression-based language, but...


"Rust is an expression-based language." from https://doc.rust-lang.org/book/ch03-03-how-functions-work.html

"Statements are instructions that perform some action and do not return a value. Expressions evaluate to a resulting value." also from https://doc.rust-lang.org/book/ch03-03-how-functions-work.html

"The let y = 6 statement does not return a value, so there isn’t anything for x to bind to. This is different from what happens in other languages, such as C and Ruby, where the assignment returns the value of the assignment. In those languages, you can write x = y = 6 and have both x and y have the value 6; that is not the case in Rust."

[My error when I make the block return the output from a statement....]

"statements don’t evaluate to a value, which is expressed by (), an empty tuple"


What about Go and Scala?

"Expressions can be part of statements: in Listing 3-1, the 6 in the statement let y = 6; is an expression that evaluates to the value 6. Calling a function is an expression. Calling a macro is an expression. The block that we use to create new scopes, {}, is an expression"

"Expressions do not include ending semicolons. If you add a semicolon to the end of an expression, you turn it into a statement, which will then not return a value. Keep this in mind as you explore function return values and expressions next."

https://en.wikipedia.org/wiki/Expression-oriented_programming_language
