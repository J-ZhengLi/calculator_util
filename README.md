# calculator_util

A utility dependency that helps you solving mathmatical expressions.

[![Crate](https://img.shields.io/crates/v/calculator_util.svg)](https://crates.io/crates/calculator_util)

This crate provide implementation for Rust's string type, thus you can evaluate math expression by simply using `String.eval()` for supported format.

### Usage

Add this crate as dependency to your project's `Cargo.toml`.

```toml
[dependencies]
calculator_util = "0.1.2"
```

### Example:

Evaluates a math expression.

```rust
use calculator_util::{ExprParser, number::Number};

let equation = "(5+6) * 7".to_string();
let result = equation.eval();
assert_eq!(result, Number::from(77));
println!("{}", result); // 77
```

Or just convert a math expression to postfix notation.

```rust
use calculator_util::ExprParser;

let equation = "1 + 2 * 3 + -4/2".to_string();
let result: String = equation.to_postfix();
println!("{}", result); // "1 2 3 * + -4 2 / +"
```

# License
This crate is distributed under the terms of MIT license.

See [LICENSE](LICENSE) for details.
