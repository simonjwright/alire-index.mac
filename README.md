This repository contains Alire crates that are intended to overcome some issues that arise from macOS features.

For example:

* Gprbuild can try to build static standalone libraries, where the 'standalone' part means that the library will be automatically elaborated. It does this using features available in GNU binutils, but not in Mach-O binary. Alternative versions of crates that normally would attempt this are provided.
* It provides tool versions built for Apple silicon.
