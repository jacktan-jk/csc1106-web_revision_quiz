# Week 2 Revision Notes

**1. Rust Functions vs. Macros**
- **Function declaration**: use the `fn` keyword (e.g. `fn add(a: i32, b: i32) -> i32 { a + b }`).
- **Macros**: invoked with `!` (e.g. `println!("Hello, {}", name);`).
  - **Declarative macros**: defined via `macro_rules!`, match patterns and expand tokens at compile time.
  - **Procedural macros**: Rust functions annotated with `#[proc_macro]` that generate code programmatically during compilation.

**2. Compile-Time Expansion**
- Macros run and expand into Rust code **before** the compiler type-checks and optimizes, enabling powerful metaprogramming.

**3. Ownership & Borrowing**
- **Ownership**: each value has a single owner; moving ownership invalidates the original binding (e.g. `let b = a;` makes `a` unusable).
- **Borrowing**: use `&T` for immutable references and `&mut T` for mutable references. Borrowing does **not** move ownership.
- **Rules**:
  1. At any time, you can have either one mutable borrow or any number of immutable borrows.
  2. References must always be valid.

**4. Moves vs. Clones**
- **Move**: transfer ownership without copying. After `let b = a;`, `a` is invalid.
- **Clone**: explicitly copy data with the `clone()` method when the type implements the `Clone` trait.

**5. The Unit Type `()`**
- Represents an empty tuple. Commonly used when a function returns nothing.
- In generics, `<()>` sets the generic parameter to the unit type.

**6. Generics and Traits**
- **Generics**: allow functions and types to operate on multiple data types (`fn identity<T>(x: T) -> T { x }`).
- **Traits**: define shared behavior; types implement traits to guarantee methods are available (e.g. `impl Display for MyType`).

**7. Memory Safety without Garbage Collection**
- Rust enforces memory safety at compile time via the borrow checker—no runtime garbage collector needed.
- **Resource Acquisition Is Initialization (RAII)** ensures cleanup when values go out of scope.

**8. WebAssembly (WASM) Basics**
- **WASM**: portable binary format running at near-native speed in browsers.
- Rust compiles to WASM using `wasm-pack` or `wasm-bindgen`, enabling high-performance web modules.

**9. JSON Serialization**
- Use the **Serde** library (`serde` and `serde_json` crates) for serializing and deserializing Rust structs to/from JSON.

---
*Review these core Rust concepts before moving on to Week 4.*

