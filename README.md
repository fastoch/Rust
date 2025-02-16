# Learn Rust Programming - Complete Course (2023)

src: https://www.youtube.com/watch?v=BpPEoZW5IiY  

![image](https://github.com/user-attachments/assets/2e7719e0-8a73-4f9a-be35-7996b520fe48)

## Course Goals

- Getting familiar with core concepts and syntax
- Data Types & Data Structures
- Ownership & Borrowing
- Allocating data to memory and accessing data from memory
- Standard Library
- Generics, Traits, Lifetimes, Closures, and much more

## What is Rust?

A systems programming language known for its safety, performance, and productivity.  
It's basically **C++ without** the hassle of **manual memory management**.  

## Why learning Rust?

- Fastest language after C/C++
- Rich type system
- No garbage collector (faster runtime)
- Useful compiler output
- Guarantees **Memory safety**
- Most beloved programming language since 2016 (according to Stack Overflow)
- Fast adoption in various branches (e.g. Linux kernel, Chromium, Android, Firefox, etc.)

The majority of security vulnerabilities in large codebases can be traced to **memory safety** bugs.  
And since Rust code can largely, if not totally, avoid such problems when properly implemented,  
its widespread adoption is no surprise.  

Back in september 2022, Microsoft Azure CTO Mark Russinovich argued that software projects that might have  
been started in C/C++ should use Rust instead. 

## Recommended Resources

- The Rust Programming Language (book covering the basics - 2nd edition)
- Rust for Rustaceans (book introducing more advanced concepts)
- https://practice.course.rs/why-exercise.html
- https://play.rust-lang.org/?version=stable&mode=debug&edition=2021

---

# Variables

- variables are assigned using the `let` keyword	
- print to standard output using `println!` or `print!` (same as println but without the newline)
- the scope of a variable is the block of code in which it is declared
- a **function** is a named block of code that is **reusable**
- **shadowing** allows a variable to be re-declared in the **same scope** with the **same name**

In Rust, variables are **immutable** by default.  
You need to explicitly declare a variable as mutable using the `mut` keyword.  
```rust
fn main() {
  let x = 5; // immutable
  let mut y = 5; // mutable
  y = 6;
```

You can't reassign a value to a variable that is not mutable.  
You can't increment a variable that is not mutable.  

We can allow **unused** variables by using the `_` character to prepend the variable name:
```rust
fn main() {
  let _x = 5;
}
```

We can also use this to make the compiler ignore unused variables:
```rust
#[allow(unused_variables)]
fn main() {
  let x = 5;
}
```

## Destructuring

We can use a pattern with `let` to destructure a tuple to separate variables:
```rust
let (a, b) = (1, 2);
```

---

## Writing our first Rust program

- see `firstProgram.rs` file
- every Rust program includes a `main` function, that is the entry point of the program

---

# Data Types

## Numbers

### Integer ranges

- i = signed integer
- u = unsigned integer

![image](https://github.com/user-attachments/assets/a399e426-95da-4d7a-ae0a-3ab5a85de8ab)

### What is a word?

In a 32-bit architecture, the size of a word is 4 bytes (32 bits), which means that the processor can access 4 bytes at a time.  
In a 64-bit architecture, the size of a word is 8 bytes (64 bits), which means that the processor can access 8 bytes at a time.  

### Floating Point

- f32 - floats with a size of 32 bits
- f64 - floats with a size of 64 bits

>[!important]
>we cannot assign a variable of a type to a variable of another type

If we don't explicitly assign a type to a variable, then the compiler will infer one for us.  
- By default, Rust compiler will infer the type i32 (32-bit signed integer) for numbers.
- 

### Type annotation

- We can annotate a type like that: `let x: i64 = 16;`
- but we can also annotate a type directly on a value: `let x = 16_i64;`

### Type inference

If we don't explicitly assign a type to a variable, then the compiler will infer one for us.  
- By default, Rust compiler will infer the type `i32` (32-bit signed integer) for numbers.
- By default, Rust compiler will infer the type `f64` (64-bit floating point number) for floating point numbers.

### Type conversion

We can't assign a variable of a type to a variable of another type.  
We can convert a variable of one type to another type using the `as` keyword.
```rust
let x = 16; // i32
let y: i64 = x as i64;
```

```rust
fn main() {
  let x: u32 = 16; 
  assert_eq!("u32".to_string(), type_of(&x)); // &x is a reference to x
  println!("Success!");
}

// Get the type of given variable, return a string representation of the type
fn type_of<T>(_: &T) -> String {
    format!("{}", std::any::type_name::<T>())
}
```

### Numeral systems

```rust
fn main() {
  let v = 1_024 + 0xff + 0o77 + 0b1111_1111;
  // 1024 (decimal) + 255 (hexadecimal) + 63 (octal) + 255 (binary)
    // 0xff = 15x16 + 15 = 255 
    // 0o77 = 7x8 + 7 = 63 
    // 0b1111_1111 = 1x2^7 + 1x2^6 + ... + 1x2^0 = 255
  assert!(v == 1597);
  println!("Success!");
}
```



---
EOF
