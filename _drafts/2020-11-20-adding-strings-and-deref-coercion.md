Adding Strings and Deref Coercion

"This isn’t the exact signature that’s in the standard library: in the standard library, add is defined using generics. Here, we’re looking at the signature of add with concrete types substituted for the generic ones, which is what happens when we call this method with String values. We’ll discuss generics in Chapter 10. This signature gives us the clues we need to understand the tricky bits of the + operator.

First, s2 has an &, meaning that we’re adding a reference of the second string to the first string because of the s parameter in the add function: we can only add a &str to a String; we can’t add two String values together. But wait—the type of &s2 is &String, not &str, as specified in the second parameter to add. So why does Listing 8-18 compile?

The reason we’re able to use &s2 in the call to add is that the compiler can coerce the &String argument into a &str. When we call the add method, Rust uses a deref coercion, which here turns &s2 into &s2[..]. We’ll discuss deref coercion in more depth in Chapter 15. Because add does not take ownership of the s parameter, s2 will still be a valid String after this operation.

Second, we can see in the signature that add takes ownership of self, because self does not have an &. This means s1 in Listing 8-18 will be moved into the add call and no longer be valid after that. So although let s3 = s1 + &s2; looks like it will copy both strings and create a new one, this statement actually takes ownership of s1, appends a copy of the contents of s2, and then returns ownership of the result. In other words, it looks like it’s making a lot of copies but isn’t; the implementation is more efficient than copying."


From: https://doc.rust-lang.org/book/ch08-02-strings.html#concatenation-with-the--operator-or-the-format-macro
