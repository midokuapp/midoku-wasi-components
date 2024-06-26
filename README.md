# `midoku-rs`

Midoku extension bindings in Rust. These crates provide a safe and (hopefully)
idiomatic way to building Midoku extensions in Rust.

## Motivation

Tachiyomi is a popular manga reader app for Android that can access various
manga sources. However, these extensions are written in Java and compiled into
an APK, making it challenging to modify or fix them without the Android
development environment (which can be cumbersome to set up just for editing a
single file).

This project aims to simplify this process by introducing a new method for
creating extensions. By providing a user-friendly API for writing sources in
Rust, developers can compile them into a WebAssembly component. This component
can then be integrated into any application that supports WebAssembly
(e.g. [`wasmtime`][wasmtime]).

This project takes inspiration from [`aidoku-rs`][aidoku-rs], a similar project
for developing extensions for the [Aidoku][aidoku] manga reader app.
However, unlike `aidoku-rs` this project takes advantage of the WebAssembly
Component Model to make use of richer types and interfaces, making the
development process smoother and more efficient.

[wasmtime]: https://wasmtime.dev
[aidoku-rs]: https://github.com/Aidoku/aidoku-rs
[aidoku]: https://github.com/Aidoku/Aidoku

## Building

To build an extension, run the following command:

```sh
cargo component build --release --package example-extension --target wasm32-unknown-unknown
```

Replace `example-extension` with the name of the extension you want to build.

You can also build all extensions at once by running:

```sh
cargo component build --release --workspace --target wasm32-unknown-unknown
```

Make sure to target `wasm32-unknown-unknown` since we do not want unwanted
WASI dependencies in our modules (`wasm32-wasi` is targeted by default).

## License

Licensed under either of

- Apache License, Version 2.0 ([LICENSE-APACHE](LICENSE-APACHE) or http://www.apache.org/licenses/LICENSE-2.0)
- MIT license ([LICENSE-MIT](LICENSE-MIT) or http://opensource.org/licenses/MIT)

at your option.
