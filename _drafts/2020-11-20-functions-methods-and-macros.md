Warning: there won't be a great deal of use in this post - I've mainly written it to firmly embed in my head the various ways of reusably wrapping blocks of logic in Rust.

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

# Associated Functions
Associated functions are functions, but look a _bit_ like methods in that they are associated with a Struct's namespace.  The idea is that you can namespace functionality that is particular to a specific struct, without having to have an instance available.  (They seem a lot like static methods to an old Java-head like me.)

See [chapter 5, section 3](https://doc.rust-lang.org/book/ch05-03-method-syntax.html#associated-functions) of The Rust book for more details.

Note: they are also sometimes [just referred to as "functions"](https://doc.rust-lang.org/book/ch08-02-strings.html#creating-a-new-string).

## Use
    let string = String::from("make me a String!")
    
and

    let string = String::new();

Note: the ```::``` syntax is used for both associated functions and namespaces created by modules.  

# Macros(!) 
TBC. See https://doc.rust-lang.org/book/ch05-02-example-structs.html and https://doc.rust-lang.org/book/ch05-03-method-syntax.html in the meantime.

## Use

    println!("This is a test")

