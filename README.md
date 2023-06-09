This repository contains Alire crates that are intended to overcome some issues that arise from macOS features.

For example:

* Gprbuild can try to build static standalone libraries, where the 'standalone' part means that the library will be automatically elaborated. It does this using features available in GNU binutils, but not in Mach-O binary. Alternative versions of crates that normally would attempt this are provided.
* It provides tool versions built for Apple silicon.

The crates provided are:

* Libraries
  * `langkit_support-23.0.1`, builds a plain static library.
  * `libadalang-23.0.1`, likewise.
* Tools
  * `gnat_macos_aarch64=13.1.0`, native GNAT for Apple silicon.
  * `gprbuild=23.0.0-mac-aarch64`, matching gprbuild (avoids you having to say `--target=aarch64-apple-darwin` at every compilation!)
