This repository contains software specifically adjusted for macOS.

* Alire crates providing development versions of `gnat`. These will appear in `alr toolchain` as `gnat_macos_{arch}-{version}`.
* Gprbuild can try to build static standalone libraries, where the 'standalone' part means that the library will be automatically elaborated. It does this using features available in GNU binutils, but not in Mach-O binary. Alternative versions of crates that normally would attempt this are provided.
  * `langkit_support-{version}.0.1`, builds a plain static library.
  * `libadalang-{version}.0.1`, likewise.

To add the crates to your index:

```shell
$ alr index --reset-community
$ alr index \
   --add=git+https://github.com/simonjwright/alire-index.mac.git \
   --before=community \
   --name=index_for_mac
```

### Homebrew 

Prior to Alire release 2.0, if you're running [Homebrew](https://brew.sh) (on either Intel or Apple silicon) we recommend that you add this to your shell startup scripts (_after_ invoking `shellenv` to get `HOMEBREW_PREFIX` defined!):

```
export C_INCLUDE_PATH=$HOMEBREW_PREFIX/include
export CPLUS_INCLUDE_PATH=$HOMEBREW_PREFIX/include
export LIBRARY_PATH=$HOMEBREW_PREFIX/lib
```
