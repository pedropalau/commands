# Rust

A language empowering everyone to build reliable and efficient software.

- [Installation](#installation)

## Installation

### Using rustup (Recommended)

```
$ curl https://sh.rustup.rs -sSf | sh
```

### Toolchain management with `rustup`

Rust is installed and managed by the `rustup` tool. Rust has a 6-week rapid release process and supports a great number of platforms, so there are many builds of Rust available at any time. `rustup` manages these builds in a consistent way on every platform that Rust supports, enabling installation of Rust from the beta and nightly release channels as well as support for additional cross-compilation targets.

If you've installed `rustup` in the past, you can update your installation by running `rustup update`.

### Configuring the `PATH` environment variable

In the Rust development environment, all tools are installed to the `~/.cargo/bin` directory, and this is where you will find the Rust toolchain, including `rustc`, `cargo`, and `rustup`.

Accordingly, it is customary for Rust developers to include this directory in their `PATH` environment variable. During installation `rustup` will attempt to configure the `PATH`. Because of differences between platforms, command shells, and bugs in `rustup`, the modifications to `PATH` may not take effect until the console is restarted, or the user is logged out, or it may not succeed at all.

If, after installation, running `rustc --version` in the console fails, this is the most likely reason.