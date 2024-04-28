# `midoku-rs`

Midoku source bindings in Rust. These crates provide a safe and (hopefully)
idiomatic way to building Midoku sources in Rust.

## Motivation

Tachiyomi is a popular manga reader app for Android that can access various
manga sources. However, these sources are written in Java and compiled into
an APK, making it challenging to modify or fix them without the Android
development environment.

This project aims to simplify this process by introducing a new method for
creating sources. By providing a user-friendly API for writing sources in Rust,
developers can compile them into a WebAssembly component. This component can
then be integrated into any application that supports WebAssembly.

The project takes inspiration from [`aidoku-rs`][aidoku-rs], a similar tool
for developing sources for the [Aidoku][aidoku] manga reader app.
Unlike `aidoku-rs`, this project leverages the latest version of WASI
(WebAssembly System Interface), facilitating a smoother development experience.

[aidoku-rs]: https://github.com/Aidoku/aidoku-rs
[aidoku]: https://github.com/Aidoku/Aidoku

## TODO

- [ ] Better documentation
- [ ] More examples
- [ ] Add tests
- [ ] Add CI/CD pipeline for documentation and tests
- [ ] Add more helper crates (e.g. `midoku-http` for handling HTTP requests)