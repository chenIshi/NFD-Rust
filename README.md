# NFD-Rust
Simple cross compiler from domain specific language NFD to rust

[NFD](https://github.com/NetFuncDev/NFD-repo) is a cross platform domain specific language for network virtualization development, by default it will be compile to c++, and this simple cross compiler is to compile this NFD to Rust.

Originally trying to do it with LLVM will be my first thought, however, I am not pretty sure about the progress on Rust. So I simply use the Rust crate, [nom](https://github.com/Geal/nom), to build a small rust compiler.

## QuickStart Guide

    1. Use `Rust Stable` instead of `Rust nightly`
    2. Use 2015 version instead of 2018 version
    3. run `cargo build`
    4. run `sudo /home/chenishi/.cargo/bin/cargo run -- --src models/stateless_firewall.txt --net [*network-interface*]`
    or `sudo target/debug/nfd-rust --src models/stateless_firewall.txt --net wlp2s0`
    the previous command require the path to cargo since cargo is not in the root group, and you need to specify the available network interface
    (You can use `ifconfig` to console)
    5. you might require to tweak the model (to conform with the `semantic tweaks` below) in order to pass the compiler parser 

## Semantic Tweaks
    
    1. use quote on IP like "192.168.0.1"
    2. translate "match_flow"-like syntax to "matchFlow"
