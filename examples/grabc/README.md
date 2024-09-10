# grabc

## Getting Started

If the repo submodule appears to be empty or out of date, you may need to run `git submodule update --init path/to/repo`.

## Transpiling

The steps to get the transpiled code are as follows:

    $ intercept-build make
    $ c2rust transpile compile_commands.json
    $ rustc grabc.rs -L/usr/X11R6/lib -lX11

If you want to have the transpiler create a crate:

    $ intercept-build make
    $ c2rust transpile compile_commands.json --emit-build-files -m grabc --output-dir rust
    $ cd rust
    $ RUSTFLAGS="-L/usr/X11R6/lib -lX11" cargo build
