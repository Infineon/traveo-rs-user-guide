<img src="..//media/ifx-logo-600.jpg" align="right" width="150" />  

# Setup Instructions

These setup instructions have been partially adapted from [the installation instructions provided by The Embedded Rust Book](https://docs.rust-embedded.org/book/intro/install.html). Currently Rust development for TRAVEO™ T2G is only supported for Windows 10 and above.

# Rust Toolchain

**Follow the [standard Rust installation steps](https://rust-lang.github.io/rustup/index.html) and first install `rustup` with the default options.**

## Installing **`stable-x86_64-pc-windows-gnu`**

Once `rustup` is installed, install the `stable-x86_64-pc-windows-gnu` toolchain:
```bat
#> rustup toolchain install stable-x86_64-pc-windows-gnu

```

If you want, you can set `stable-x86_64-pc-windows-gnu` as the default toolchain...
```
#> rustup show

Default host: x86_64-pc-windows-msvc
rustup home:  ---

installed toolchains
--------------------

stable-x86_64-pc-windows-gnu
stable-x86_64-pc-windows-msvc (default)

installed targets for active toolchain
--------------------------------------

x86_64-pc-windows-gnu

active toolchain
----------------

stable-x86_64-pc-windows-gnu (default)
rustc 1.65.0 (897e37553 2022-11-02)
```
```
#> rustup default stable-x86_64-pc-windows-gnu

info: using existing install for 'stable-x86_64-pc-windows-gnu'
info: default toolchain set to 'stable-x86_64-pc-windows-gnu'

  stable-x86_64-pc-windows-gnu unchanged - rustc 1.65.0 (897e37553 2022-11-02)
```

## Adding Cortex-M Targets

Add targets for Cortex-M0/M0+, Cortex-M4/M7:
```
> rustup target add thumbv6m-none-eabi
info: downloading component 'rust-std' for 'thumbv6m-none-eabi'
info: installing component 'rust-std' for 'thumbv6m-none-eabi'

> rustup target add thumbv7em-none-eabi
info: downloading component 'rust-std' for 'thumbv7em-none-eabi'
info: installing component 'rust-std' for 'thumbv7em-none-eabi'
 10.7 MiB /  10.7 MiB (100 %)   9.5 MiB/s in  1s ETA:  0s
```

## Additional Cargo Tools

- [cargo-binutils](https://crates.io/crates/cargo-binutils): Cargo subcommands to invoke the LLVM tools shipped with the Rust toolchain
- Optional:
    - [cargo-generate](https://crates.io/crates/cargo-generate): cargo-generate is a developer tool to help you get up and running quickly with a new Rust project by leveraging a pre-existing git repository as a template.

# Arm GNU Toolchain for Windows

Download and install `arm-none-eabi-gdb` from the [GNU Arm Embedded Toolchain Downloads](https://developer.arm.com/downloads/-/gnu-rm) page.

# Python 2.7

- Should be added to `%PATH%`
- Required for the GDB `pretty-printer` (part of the **Arm GNU Toolchain**)

# Visual Studio Code

Install [Visual Studio Code](https://code.visualstudio.com/download).

## In addition, the following VSCode extensions are required:

- [Cortex-Debug](https://marketplace.visualstudio.com/items?itemName=marus25.cortex-debug): Provides ARM Cortex-M GDB debugger support for VSCode
- [rust-analyzer](https://marketplace.visualstudio.com/items?itemName=rust-lang.rust-analyzer): Rust language support for VSCode

# CypressAutoFlashUtility + OpenOCD

Currently, the latest and greatest version of [Cypress OpenOCD](https://github.com/Infineon/openocd/releases) is not supported. Please use the version included in the one of the [code examples](../code-examples/README.md) under the `traveo_debug` folder.

--

Return to the [Table of Contents](../README.md).