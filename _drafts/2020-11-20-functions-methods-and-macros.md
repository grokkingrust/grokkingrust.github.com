Warnging: there won't be a great deal of use in this post - I've mainly written it to firmly embed in my head the various ways of reusably wrapping blocks of logic in Rust.

# Functions 
Declared by the keyword ```fn```, functions are first class (i.e. you don't need to home them in a struct or anywhere else). You use them simply by referencing their name.

## Define
    
    fn hello(name: &str) {
        println!("Hello, {}!", name);
    }

## Use
    hello("World);

# Methods
Methods are also declared by the keyword ```fn``` but within the scope of a ```struct``` implementation or a ```trait``` definition. To use a method we start with the instance of the ```struct``` followed by a dot (```.```) then the method name, parens, and any arguments.

For example, the ```to_string``` method which is available on any type which implements the Display trait.

## Define

    struct Rectangle {
        width: u32,
        height: u32,
    }

    impl Rectangle {
        fn area(&self) -> u32 {
            self.width * self.height
        }
    }

## Use
    rect.area()

Read more in [chapter 5 of the Rust Book](https://doc.rust-lang.org/book/ch05-03-method-syntax.html)

Plus also note in the definition above the use of ```&self``` in the method signature instead of ```rectangle: &Rectangle```. This is an occurrence of ownership in action.

As the Rust Book says:

> "Methods can take ownership of self, borrow self immutably as we’ve done here, or borrow self mutably, just as they can any other parameter."  

From [chapter 5 of the Rust Book](https://doc.rust-lang.org/book/ch05-03-method-syntax.html)

## Associated Functions
See https://doc.rust-lang.org/book/ch05-03-method-syntax.html#associated-functions

"Let you namespace functionality that is particular to your struct without having an instance available"

E.g. String::from and String::new.

N.b. "the :: syntax is used for both associated functions and namespaces created by modules".  They are also sometimes just referred to as "functions" (c.f. https://doc.rust-lang.org/book/ch08-02-strings.html#creating-a-new-string)

# Macros ! (e.g. println!)

https://doc.rust-lang.org/book/ch05-02-example-structs.html
and https://doc.rust-lang.org/book/ch05-03-method-syntax.html
