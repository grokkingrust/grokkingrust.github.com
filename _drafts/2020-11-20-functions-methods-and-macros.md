Warnging: there won't be a great deal of use in this post - I've mainly written it to firmly embed in my head the various ways of reusably wrapping blocks of logic in Rust.

# Functions e.g. area
Declared by the keyword ```fn```, functions are first class (i.e. you don't need to home them in a struct or anywhere else.

# Methods e.g. rect.area

method syntax goes after an instance: we add a dot followed by the method name, parentheses, and any arguments - from https://doc.rust-lang.org/book/ch05-03-method-syntax.html

For example, the to_string method which is available on any type which implements the Display trait.

Plus also note: &self instead of rectangle: &Rectangle. ("Methods can take ownership of self, borrow self immutably as we’ve done here, or borrow self mutably, just as they can any other parameter.")

## Associated Functions
See https://doc.rust-lang.org/book/ch05-03-method-syntax.html#associated-functions

"Let you namespace functionality that is particular to your struct without having an instance available"

E.g. String::from and String::new.

N.b. "the :: syntax is used for both associated functions and namespaces created by modules".  They are also sometimes just referred to as "functions" (c.f. https://doc.rust-lang.org/book/ch08-02-strings.html#creating-a-new-string)

# Macros ! (e.g. println!

https://doc.rust-lang.org/book/ch05-02-example-structs.html
and https://doc.rust-lang.org/book/ch05-03-method-syntax.html
