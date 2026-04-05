# libprocessing

libprocessing is an experimental native library with the goal of supporting the implementation of the core Processing API in a variety of languages. The library is written in the [Rust programming language](https://rust-lang.org/) and built on top of the [Bevy game engine](https://bevy.org/). libprocessing uses [WebGPU](https://webgpu.org/) as its rendering backend and is designed to (eventually) support desktop, mobile, and web targets.

## Getting started

### mewnala (the python library)

Inside of our `processing_pyo3` crate we have created a python package that you can easily install with pip.
Again, we are still very nascent, but let us know what kinds of snags you may run into while getting this set up.
Try running the examples in the [processing_pyo3 examples directory](crates/processing_pyo3/examples).

```bash
# have python3 installed on your system

# create a sketch folder and go inside
mkdir my-sketch-folder && cd my-sketch-folder

# create a virtual env
python -m venv .venv

# activate virtual env
source .venv/bin/activate

pip install mewnala

python my_sketch.py
```

### Rust

You'll need to install the Rust toolchain to work on this project. Most users will want to install Rust via [`rustup`](https://rustup.rs/), which helps manage Rust toolchain versions.

### Build commands

This project uses [just](https://github.com/casey/just) as a command runner. Run `just` to see available commands.

## Building for web

The `processing_wasm` crate provides WebAssembly bindings that expose a JavaScript API mirroring the C FFI.

### Requirements

Install [wasm-pack](https://rustwasm.github.io/wasm-pack/):

```bash
cargo install wasm-pack
```

You'll also need the wasm32 target:

```bash
rustup target add wasm32-unknown-unknown
```

### Build

```bash
just wasm-build
```

This outputs the package to `target/wasm/`.

### Run the example

```bash
just wasm-serve
```


## Contributing

We want your help building this library! You can see a list of outstanding tasks in our [issues](https://github.com/processing/libprocessing). However, while we're still in the early phases, consider checking in with us first in the `#devs-chat` channel on [Discord](https://discord.gg/h99u95nU7q) to coordinate our efforts.

You can read our project design principles [here](./docs/principles.md).
