# Source (+) Engine

Refined version of [source-engine](https://github.com/nillerusr/source-engine) repository.<br>
This project is using waf buildsystem. If you have waf-related questions look https://waf.io/book

## How to Build

*You may need* **Git** *in order to clone the repository since it includes submodules:*

With HTTPS: ``git clone --recursive https://github.com/yungDoom/source-plus-engine``<br>
Or with SSH **(Recommended)**: ``git clone --recurse-submodules git@github.com:yungDoom/source-plus-engine.git``

#### Windows

```
.\waf.bat configure -T release --prefix=hl2mp --build-games=hl2mp --disable-warns --enable-opus
.\waf.bat build -p
.\waf.bat install
```

#### Linux

*The List of needed packages:*
``libopenal-dev g++-multilib gcc-multilib libpng-dev libjpeg-dev libfreetype6-dev libfontconfig1-dev libcurl4-gnutls-dev libsdl2-dev zlib1g-dev libbz2-dev libedit-dev``<br>
**Find the matching ones for your distro.**

```
./waf configure -T release --prefix=hl2mp --build-games=hl2mp --disable-warns --enable-opus
./waf build -p
./waf install
```

#### MacOS

- Download XCode from AppStore
- Install Xcode build tools with ``xcode-select --install`` command.
- Install [HomeBrew](https://brew.sh/).

##### Required Dependencies

- Run ``brew install sdl2 freetype2 fontconfig pkg-config opus libpng libedit``

Follow the Linux build instructions.

#### FreeBSD

- Use ``pkg ins python sdl2 freetype2 fontconfig curl pkgconf openal-soft jpeg-turbo png``.

Follow the Linux build instructions.

#### Android (on Linux)

- Download and extract Android NDK r10e from [here](https://github.com/android/ndk/wiki/Unsupported-Downloads).
- Download and extract [CLANG 11](https://github.com/llvm/llvm-project/releases/download/llvmorg-11.1.0/clang+llvm-11.1.0-x86_64-linux-gnu-ubuntu-16.04.tar.xz) or use CLANG from [LLVM repository](https://apt.llvm.org) for APT-based distros.
- Run `export ANDROID_NDK_HOME="PATH/TO/NDK/android-ndk-r10e"` and `export PATH="PATH/TO/CLANG/bin:$PATH"` or `export PATH="/usr/lib/llvm-11/bin:$PATH"` if you're use llvm.sh script.
- Add to WAF args `--togles --android=armeabi-v7a-hard,host,21`. `armeabi-v7a-hard` can be replaced with `aarch64` for arm64 build, but you need to add `-8` or `--64bits` argument.

## Flags

**Make sure to use them while configuring and not building.**

``--32bits`` = This flag allows you to build every component as 32-bits<br>
``-T debug`` = Build in Debug Mode<br>
``-d`` = Dedicated Server<br>
``--prefix=`` and ``--build-games=`` = You can choose which game you want to build, here are the examples:

```
hl1 = Half-Life 1: Source
hl2 = Half-Life 2 // Default when no flag provided.
episodic = Half-Life 2 Episode 1 or Episode 2
dod = Day of Defeat
cstrike = Counter-Strike: Source
portal = Portal
```

### Build Flags


**Make sure to use them while building and not configuring.**

``-v`` = Verbose