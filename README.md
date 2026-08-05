# Tetris
A C++ tetris

## Initial setup

### C++20 installation

```bash
$ sudo apt update
$ sudo apt install -y gcc-15 g++-15
$ sudo update-alternatives --install /usr/bin/gcc gcc /usr/bin/gcc-15 15
$ sudo update-alternatives --install /usr/bin/g++ g++ /usr/bin/g++-15 15
```

```bash
$ sudo update-alternatives --config gcc
There are 3 choices for the alternative gcc (providing /usr/bin/gcc).

  Selection    Path             Priority   Status
------------------------------------------------------------
* 0            /usr/bin/gcc-15   15        auto mode
  1            /usr/bin/gcc-13   13        manual mode
  2            /usr/bin/gcc-14   14        manual mode
  3            /usr/bin/gcc-15   15        manual mode

Press <enter> to keep the current choice[*], or type selection number: 0
$ sudo update-alternatives --config g++
There are 3 choices for the alternative g++ (providing /usr/bin/g++).

  Selection    Path             Priority   Status
------------------------------------------------------------
* 0            /usr/bin/g++-15   15        auto mode
  1            /usr/bin/g++-13   13        manual mode
  2            /usr/bin/g++-14   14        manual mode
  3            /usr/bin/g++-15   15        manual mode

Press <enter> to keep the current choice[*], or type selection number: 0
```

```bash
$ gcc --version
gcc (Ubuntu 15.2.0-16ubuntu1) 15.2.0
Copyright (C) 2025 Free Software Foundation, Inc.
This is free software; see the source for copying conditions.  There is NO
warranty; not even for MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. 
$ g++ --version
g++ (Ubuntu 15.2.0-16ubuntu1) 15.2.0
Copyright (C) 2025 Free Software Foundation, Inc.
This is free software; see the source for copying conditions.  There is NO
warranty; not even for MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.
```

### Clang format installation and configuration

```bash
$ sudo apt install -y clang-format
```

```bash
$ https://gist.githubusercontent.com/gelldur/d7bc3ea226aebcf8cc879df1e8524236/raw/cf155f9ad92461160e149b616fb45a22a3996d0d/.clang-format
```

### CMake installation

```bash
$ sudo apt update
$ sudo apt install -y cmake
```

```bash
$ cmake --version
cmake version 4.2.3

CMake suite maintained and supported by Kitware (kitware.com/cmake).
```

### SDL3 installation

#### Dependencies

```bash
$ sudo apt update
$ sudo apt install -y build-essential git make pkg-config cmake ninja-build gnome-desktop-testing libasound2-dev libpulse-dev libaudio-dev libfribidi-dev libjack-dev libsndio-dev libx11-dev libxext-dev libxrandr-dev libxcursor-dev libxfixes-dev libxi-dev libxss-dev libxtst-dev libxkbcommon-dev libdrm-dev libgbm-dev libgl1-mesa-dev libgles2-mesa-dev libegl1-mesa-dev libdbus-1-dev libibus-1.0-dev libudev-dev libthai-dev libusb-1.0-0-dev libpipewire-0.3-dev libwayland-dev libdecor-0-dev liburing-dev
```

#### Building

Go to [SDL3 releases](https://github.com/libsdl-org/SDL/releases) and install the proper `.tar.gz`.
Here I chose 3.4.14.

```bash
$ mkdir tmp
$ cd tmp/
$ tar -xvf SDL3-3.4.14.tar.gz
$ cd SDL3-3.4.14/
$ cmake -B build/
$ cd build/
$ make
$ sudo make install
$ cd ../../../
$ rm -rf tmp/
```

## Project building

```bash
$ cmake -B build/
$ cd build/
$ cmake --build . --parallel
```

## Run the project

```bash
$ ./build/Tetris
```

## References

- [C++20 ubuntu installation](https://hackmd.io/@JackyDev/SJ8pqFA1xx)
- [GCC/G++ alternatives configuration](https://gist.github.com/cobaohieu/ded429cb892b46ae9bfd9919a11e593a)
- [.clang-format](https://gist.github.com/gelldur/d7bc3ea226aebcf8cc879df1e8524236)
- [.clang-format for wget](https://gist.githubusercontent.com/gelldur/d7bc3ea226aebcf8cc879df1e8524236/raw/cf155f9ad92461160e149b616fb45a22a3996d0d/.clang-format)
- [CMake installation](https://linuxcapable.com/how-to-install-cmake-on-ubuntu-linux/)
- [CMake configuration tutorial](https://keasigmadelta.com/blog/cmake-tutorial-getting-started/?srsltid=AfmBOortqWGGd9fU7lzmIAbkeMwvWKoPue5eVIYVfbw9taAEZ15HbIME)
- [SDL3 releases](https://github.com/libsdl-org/SDL/releases)
- [SDL3 dependencies installation](https://wiki.libsdl.org/SDL3/README-linux)
- [SDL3 installation and setup tutorial](https://glusoft.com/sdl3-tutorials/install-sdl3-linux-cmake/)
- [SDL3 examples](https://examples.libsdl.org/SDL3/)
