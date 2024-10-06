# OpenGL/SDL2 in Rust

A test program for a triangle using OpenGL/SDL2 and Rust

Source from https://github.com/Nercury/rust-and-opengl-lessons/tree/master/lesson-05/src

## Cross compiling

Testing can be done locally, but the main goal (for me) is to be able to run
SDL2/OpenGL programs on the Anbernic RG40XX V I have. That needs a cross compiler
for aarch64.

Cross.toml is set up for that: it's using my cross-compile container image which is based
on Debian 12.7. 
Using the original cross-rs container images,
I could only get SDL 2.0.10 which was too old and it caused linker errors.

## How to Use

For non-cross-compile, just use the usual

```
cargo build
```

and for cross compiling, after having installed [cross-rs](https://github.com/cross-rs/cross), do

```
cross build
```

The resulting binary will be in ./target/aarch64-unknown-linux-gnu/debug/sdl2-gl (about 6MB).
Copy it over to your RG40XX (mine runs Knulli from
[here](https://github.com/knulli-cfw/distribution/releases/tag/20240721).
Log in (e.g. I do `ssh knulli.local`) and the run it.
You should see the famous colored triangle on the screen.

