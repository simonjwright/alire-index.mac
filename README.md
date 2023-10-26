This repository contains Alire crates that are intended to overcome some issues that arise from macOS features.

For example:

* Gprbuild can try to build static standalone libraries, where the 'standalone' part means that the library will be automatically elaborated. It does this using features available in GNU binutils, but not in Mach-O binary. Alternative versions of crates that normally would attempt this are provided.
* It provides tool versions built for Apple silicon.

The crates provided are:

* Libraries
  * `langkit_support-23.0.1`, builds a plain static library.
  * `libadalang-23.0.1`, likewise.
* Tools
  * `gnat_macos_aarch64=13.1.1`, native GNAT for Apple silicon.
  * `gprbuild=23.0.1-mac-aarch64`, matching gprbuild (avoids you having to say `--target=aarch64-apple-darwin` at every compilation!)
  
To install:

```
$ alr index \
   --add=git+https://github.com/simonjwright/alire-index.mac.git \
   --before=community \
   --name=index_for_mac
```

after which

```
$ alr toolchain --select
Welcome to the toolchain selection assistant     

In this assistant you can set up the default toolchain to be used with any crate
that does not specify its own top-level dependency on a version of gnat or 
gprbuild.

If you choose "None", Alire will use whatever version is found in the 
environment.

ⓘ gnat is currently not configured. (alr will use the version found in the environment.)

Please select the gnat version for use with this configuration
  1. gnat_external=13.1.0 [Detected at /opt/gcc-13.1.0-aarch64/bin/gnat]
  2. None
  3. gnat_macos_aarch64=13.1.1
  4. gnat_macos_aarch64=13.1.0
Enter your choice index (first is default): 
> 3
ⓘ Selected tool version gnat_macos_aarch64=13.1.1

ⓘ Choices for the following tool are narrowed down to releases compatible with just selected gnat_macos_aarch64=13.1.1

ⓘ gprbuild is currently not configured. (alr will use the version found in the environment.)

Please select the gprbuild version for use with this configuration
  1. gprbuild=23.0.1-mac-aarch64
  2. None
  3. gprbuild=23.0.0-mac-aarch64
Enter your choice index (first is default): 
> 1
ⓘ Selected tool version gprbuild=23.0.1-mac-aarch64
```

If you're running [Homebrew](https://brew.sh) (on either Intel or Apple silicon) we recommend that you add this to your shell startup scripts (_after_ invoking `shellenv`!):

```
export C_INCLUDE_PATH=$HOMEBREW_PREFIX/include
export LIBRARY_PATH=$HOMEBREW_PREFIX/lib
```
