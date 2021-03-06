# blackarch-devtools
Development framework for the BlackArch Linux distribution written in Rust.

# What is it?
It's a development framework for BlackArch Linux developers that allow you to do: setup chroot enviroment, build packages in chroot environment, build packages with dependencies that aren't in the repos, sync the working chroot copy with the root chroot copy, test packages in the chroot enviroment and more things.

# Installation
If you want to install it, you can do that manually compiling the source or using the precompiled binary.

Prerequisites:
- [curl](https://www.archlinux.org/packages/core/x86_64/curl/)
- [devtools](https://www.archlinux.org/packages/extra/any/devtools/)

You can install the prerequisites with `# pacman -S curl devtools`

**Manually:** You need to have [Rust](https://www.archlinux.org/packages/extra/x86_64/rust/) installed in your computer first. Install it with `# pacman -S rust`
```
$ git clone https://github.com/Edu4rdSHL/blackarch-devtools.git
$ cd blackarch-devtools
$ cargo build --release
$ sudo cp target/release/blackarch-devtools /usr/bin/blackarch-devtools
$ blackarch-devtools
```
**Using the binary:**
```
$ git clone https://github.com/Edu4rdSHL/blackarch-devtools.git
$ sudo cp blackarch-devtools/bin/blackarch-devtools /usr/bin/blackarch-devtools
$ blackarch-devtools
```

# Usage

The available options are:

```
blackarch-devtools 0.1.0
Eduard Tolosa <tolosaeduard@gmail.com>
Development tools for BlackArch Linux

USAGE:
    blackarch-devtools [FLAGS] [OPTIONS]

FLAGS:
    -b, --build      Build package from PKGBUILD in clean chroot environment.
    -c, --clean      Clean chroot environment before building.
    -h, --help       Prints help information
    -s, --setup      Setup the clean chroot environment (automatically setup blackarch keyring).
    -t, --test       Install and test package in clean chroot environment.
    -u, --update     Update BlackArch Linux chroot environment.
    -V, --version    Prints version information
    -v               Sets the level of verbosity

OPTIONS:
    -e, --executable <executable>
            Name of the binary file provided by the package that you're installing in the chroot environment.

    -I, --install-missing <install-missing>...
            Build package files that aren't available in repos. You can specify it multiple times.

    -p, --package <package>                       Build package to install in the clean chroot environment.
```
Flags doesn't require arguments, options require.

If you have found an issue or want to make a feature request, please use the [issue tracker](https://github.com/Edu4rdSHL/blackarch-devtools/issues).
