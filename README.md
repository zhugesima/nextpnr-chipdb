# nextpnr-chipdb

ChipDB builder for NextPnR project

Prerequisites
-------------

The following packages need to be installed for building nextpnr, independent
of the selected architecture:

- CMake 3.3 or later
- Modern C++11 compiler (`clang-format` required for development)
- Python 3.5 or later, including development libraries (`python3-dev` for Ubuntu)
- Boost libraries (`libboost-dev libboost-filesystem-dev libboost-thread-dev libboost-program-options-dev libboost-python-dev libboost-dev` or `libboost-all-dev` for Ubuntu)
  
Getting started
---------------

```
git clone https://github.com/YosysHQ/nextpnr-chipdb
cd nextpnr-chipdb
git submodule update --init --recursive
```

Additional notes for building nextpnr-chipdb
--------------------------------------------
Use cmake `-D` options to specify which version of nextpnr-chipdb you want to build.
Use `-DARCH=...` to set the architecture. It is a semicolon separated list.
Use `cmake . -DARCH=all` to build all supported architectures.

The default builds all supported targets allows nextpnr to use this as it's external chipdb.

You can change the location where nextpnr-chipdb will be installed (this will usually default to `/usr/local`) by using
`-DCMAKE_INSTALL_PREFIX=/install/prefix`.

```
cmake . -DCMAKE_INSTALL_PREFIX=/usr
make -j$(nproc)
sudo make install
```

For developers:
---------------
When there are changes on main repositores, get all submodules to latest with:

```
git pull --recurse-submodules
git submodule update --remote --recursive
```
