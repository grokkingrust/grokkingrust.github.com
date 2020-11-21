---
layout: article
title: "Result types and expect"
description: "."
tags: [rust, errors, exceptions, error-handling, matching]
---

Rust has what it calls "Result types" and although the Rust book refers to them as enums they are [most similar to algebraic data types](https://doc.rust-lang.org/book/ch06-00-enums.html) (which explains why they feel a bunch like Options in Java). A Result type has the variants "Ok" and "Err".  If your result was a success then the Ok contains your result.  If something went wrong and the operation failed then the Err will give you some information as to why.


The purpose of Result types is to encode error-handling information. Values of the Result type, like values of any type, have methods defined on them. An instance of io::Result has an expect method that you can call. If this instance of io::Result is an Err value, expect will cause the program to crash and display the message that you passed as an argument to expect. If the read_line method returns an Err, it would likely be the result of an error coming from the underlying operating system. If this instance of io::Result is an Ok value, expect will take the return value that Ok is holding and return just that value to you so you can use it. In this case, that value is the number of bytes in what the user entered into standard input.


The Option Enum and it's advantages over null values
https://doc.rust-lang.org/book/ch06-01-defining-an-enum.html#the-option-enum-and-its-advantages-over-null-values

AND WE CAN MATCH ON THEM TOO:

Switching from an expect call to a match expression is how you generally move from crashing on an error to handling the error. Remember that parse returns a Result type and Result is an enum that has the variants Ok or Err. We’re using a match expression here, as we did with the Ordering result of the cmp method.

From: https://doc.rust-lang.org/book/ch02-00-guessing-game-tutorial.html
