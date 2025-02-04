# Learn Rust Programming - Complete Course (2023) - @42/839

src: https://www.youtube.com/watch?v=BpPEoZW5IiY  

![image](https://github.com/user-attachments/assets/2e7719e0-8a73-4f9a-be35-7996b520fe48)

## Course Goals

- Getting familiar with core concepts and syntax
- Data Types & Data Structures
- Ownership & Borrowing
- Allocating data to memory and accessing data from memory
- Standard Library
- Generics, Traits, Lifetimes, Closures, and much more

## Why learning Rust?

- Fastest language after C
- Rich type system
- No garbage collector (faster runtime)
- Useful compiler output
- Guarantees Memory safety
- Most beloved programming language since 2016 (according to Stack Overflow)
- Fast adoption in various branches

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

You can't reassign a value to a variable that is not mutable.  
You can't increment a variable that is not mutable.  

We can allow unused variables by using the `_` character to prepend the variable name:
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

## Destructuring Assignments

???

---

## Writing our first Rust program

- see `firstProgram.rs` file
- every Rust program includes a `main` function, that is the entry point of the program

---

# Data Types

## Numbers

### Integer ranges

![image](https://github.com/user-attachments/assets/a399e426-95da-4d7a-ae0a-3ab5a85de8ab)

### What is a word?

In a 32-bit architecture, the size of a word is 4 bytes (32 bits), which means that the processor can access 4 bytes at a time.  
In a 64-bit architecture, the size of a word is 8 bytes (64 bits), which means that the processor can access 8 bytes at a time.  

### Floating Point

types are f32 and f64  





---
EOF
