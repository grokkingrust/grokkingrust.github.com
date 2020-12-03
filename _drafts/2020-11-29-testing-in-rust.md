# Unit tests
When you create a new library you get tests set up for you for free.  That's nice.

"0 filtered out" is also nice

and "0 measured" sounds awesome

Doc-tests - "Rust can compile any code examples that appear in our API documentation. This feature helps us keep our docs and our code in sync!"

from: https://doc.rust-lang.org/book/ch11-01-writing-tests.html

"unit tests go in the same files as the code" - from https://doc.rust-lang.org/book/ch11-03-test-organization.html

## Testing private functions
"Rust’s privacy rules do allow you to test private functions."

# Integration tests
"In Rust, integration tests are entirely external to your library. They use your library in the same way any other code would, which means they can only call functions that are part of your library’s public API. Their purpose is to test whether many parts of your library work together correctly."

"each file in the tests directory is a separate crate, so we need to bring our library into each test crate’s scope"

"We don’t need to annotate any code in tests/integration_test.rs with #[cfg(test)]"

# Doc tests
"Adding example code blocks in your documentation comments can help demonstrate how to use your library, and doing so has an additional bonus: running cargo test will run the code examples in your documentation as tests! Nothing is better than documentation with examples. But nothing is worse than examples that don’t work because the code has changed since the documentation was written. " from https://doc.rust-lang.org/book/ch14-02-publishing-to-crates-io.html#documentation-comments-as-tests
