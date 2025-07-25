<h1 align="center">Source (+) Engine</h1>

<p align="center"> This project is using waf buildsystem. If you have waf-related questions look https://waf.io/book</p>

<h2 align="center"> How to Build </h2>

*You may need* **Git** *in order to clone the repository since it includes submodules:*

``git clone --recursive https://github.com/yungDoom/source-plus-engine``<br>
Or with SSH **(Recommended)**: ``git clone --recurse-submodules git@github.com:yungDoom/source-plus-engine.git``

<h4 align="center"> Windows </h4>

```
.\waf.bat configure --disable-warns
.\waf.bat build -p
.\waf.bat install
```

<h4 align="center"> Linux </h4>

*The List of needed packages:*
``libopenal-dev g++-multilib gcc-multilib libpng-dev libjpeg-dev libfreetype6-dev libfontconfig1-dev libcurl4-gnutls-dev libsdl2-dev zlib1g-dev libbz2-dev libedit-dev``<br>
**Find the matching ones for your distro.**

```
./waf configure --disable-warns
./waf build -p
./waf install
```

<h4 align="center"> MacOS </h4>

- Download XCode from AppStore
- Install Xcode build tools with ``xcode-select --install`` command.
- Install [HomeBrew](https://brew.sh/).

##### Required Dependencies

- Run ``brew install sdl2 freetype2 fontconfig pkg-config opus libpng libedit``

Follow the Linux build instructions.

<h4 align="center"> FreeBSD </h4>

- Use ``pkg ins python sdl2 freetype2 fontconfig curl pkgconf openal-soft jpeg-turbo png``.

Follow the Linux build instructions.

<h4 align="center"> Android (on Linux) </h4>

- Download and extract Android NDK r10e from [here](https://github.com/android/ndk/wiki/Unsupported-Downloads).
- Download and extract [CLANG 11](https://github.com/llvm/llvm-project/releases/download/llvmorg-11.1.0/clang+llvm-11.1.0-x86_64-linux-gnu-ubuntu-16.04.tar.xz) or use CLANG from [LLVM repository](https://apt.llvm.org) for APT-based distros.
- Run `export ANDROID_NDK_HOME="PATH/TO/NDK/android-ndk-r10e"` and `export PATH="PATH/TO/CLANG/bin:$PATH"` or `export PATH="/usr/lib/llvm-11/bin:$PATH"` if you're use llvm.sh script.
- Add to WAF args `--togles --android=armeabi-v7a-hard,host,21`. `armeabi-v7a-hard` can be replaced with `aarch64` for arm64 build, but you need to add `-8` or `--64bits` argument.


<h2 align="center"> Knowledgements </h2>

Make sure to use `steam_legacy` branch of every supported source games to get the files.

<h4 align="center"> Flags </h4>

**Make sure to use them while configuring and not building.**

``--32bits`` = This flag allows you to build every component as 32-bit<br>
``-T debug`` or ``-T release`` = Switch between debug or release depending which flag u choose<br>
``--prefix=`` and ``--build-games=`` = You can choose which game you want to build, here are the examples:

```
hl1 = Half-Life 1: Source
hl2 = Half-Life 2 -- Default Option if you dont provide both of those flags.
episodic = Half-Life 2 Episode 1 or Episode 2
hl2mp = Half-Life 2: Deathmatch
dod = Day of Defeat
cstrike = Counter-Strike: Source
portal = Portal
```

``--enable-opus`` = Enables Voice-Chatting features.
``-d`` = Dedicated Server

**e.g:** `./waf | .\waf.bat configure -T release --prefix=hl2mp --build-games=hl2mp --disable-warns --enable-opus`