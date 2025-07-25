<h1 align="center">Source (+) Engine</h1>

<p align="center"> This project is using waf buildsystem. If you have waf-related questions look https://waf.io/book</p>

<h2 align="center"> How to Build </h2>

<h4 align="center"> Windows </h4>

```
.\waf.bat configure --disable-warns
.\waf.bat build -p
.\waf.bat install
```

<h4 align="center"> Linux </h4>



```
./waf configure --disable-warns
./waf build -p
./waf install
```

### Knowledgements

Make sure to use `steam_legacy` branch of every supported source games to get the files.<br>
Having black screen on HL2:DM or any other game? [Download the fix](https://mega.nz/file/bzY2XLrA#1GsxVHTS39Jfk7LanJOou7E_2XK3QADpmDwP7ajMC0Y)<br>
I will not cover how to setup your game files, its pretty straight forward.

#### Flags

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