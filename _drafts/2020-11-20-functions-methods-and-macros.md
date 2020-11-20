# Functions e.g. area
# Methods e.g. rect.area

method syntax goes after an instance: we add a dot followed by the method name, parentheses, and any arguments - from https://doc.rust-lang.org/book/ch05-03-method-syntax.html

Plus also note: &self instead of rectangle: &Rectangle. ("Methods can take ownership of self, borrow self immutably as we’ve done here, or borrow self mutably, just as they can any other parameter.")

## Associated Functions
See https://doc.rust-lang.org/book/ch05-03-method-syntax.html#associated-functions

"Let you namespace functionality that is particular to your struct without having an instance available"

E.g. String::from

N.b. "the :: syntax is used for both associated functions and namespaces created by modules"

# Macros ! (e.g. println!

https://doc.rust-lang.org/book/ch05-02-example-structs.html
and https://doc.rust-lang.org/book/ch05-03-method-syntax.html
