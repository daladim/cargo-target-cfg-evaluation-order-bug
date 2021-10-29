This is a minimal reproducer related to an unexpected Cargo behaviour.


# How to fail the build

Run `cargo build`, this will not build. \
See the `.cargo/config` file and [the original issue](https://github.com/rust-lang/cargo/issues/6858) for some insight.

# How to build

Change the `.cargo/config` so that it does not contain a conditional section:
```
[build]
rustflags = ["--cfg", "my_flag"]
```

`cargo run` will succeed.
