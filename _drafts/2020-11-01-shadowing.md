We create a variable named guess. But wait, doesn’t the program already have a variable named guess? It does, but Rust allows us to shadow the previous value of guess with a new one. This feature is often used in situations in which you want to convert a value from one type to another type. Shadowing lets us reuse the guess variable name rather than forcing us to create two unique variables, such as guess_str and guess for example. (Chapter 3 covers shadowing in more detail.)

From: https://doc.rust-lang.org/book/ch02-00-guessing-game-tutorial.html
