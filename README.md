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

