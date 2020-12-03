---
layout: article
title: "Testing in Rust is a first-class citizen"
description: "."
tags: [rust, docs, testing]
---
Testing in Rust is a first-class citzen and thats nice.  

What do I mean by "first class citizen"?  Well, you get support for writing tests _in the standard libraries_, the bundled build tool / package manager runs tests for you, and best of all _cargo builds will run the example code in your documentation if you ask them to._

Lets look at the details of some of these things.

# Unit tests
First up, when you create a new library (with ```cargo new hello_world --lib```) you get tests set up for you for free.  That's nice.

Then, when you run your tests with ```cargo test``` you get some handy feedback as to what you have filtered out, and excitingly, how many you "measured" (i.e. tested the performance of.)

"unit tests go in the same files as the code" - from https://doc.rust-lang.org/book/ch11-03-test-organization.html

## Testing private functions
Another key point about unit testing in Rust is that, because the style is to put the tests in the same files as your code the privacy rules allow you to test private functions.  I know it comes down to testing style, but personally thats a boon for me when I TDD. 

# Integration tests
Next up is integration tests.  As is the way with many things these days, Rust takes an opinionated stance on what an "integration test" is, and I personally am all for that

    > "In Rust, integration tests are entirely external to your library. They use your library in the same way any other code would, which means they can only call functions that are part of your library’s public API. Their purpose is to test whether many parts of your library work together correctly."

Integration tests then go in separate Rust files, but becasue they live in a standard place (```tests/```) we dont need to annotate them.

# Documentation tests
Finally we have documentation tests.  This is a new concept to me, but one which I can very much get behind. I'll simply quote from the Rust Book  

    > "Adding example code blocks in your documentation comments can help demonstrate how to use your library, and doing so has an additional bonus: running cargo test will run the code examples in your documentation as tests! Nothing is better than documentation with examples. But nothing is worse than examples that don’t work because the code has changed since the documentation was written. " from {Documentation comments as tests](https://doc.rust-lang.org/book/ch14-02-publishing-to-crates-io.html#documentation-comments-as-tests) in the Rust Book
