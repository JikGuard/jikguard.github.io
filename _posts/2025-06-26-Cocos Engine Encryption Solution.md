---
layout: post
title: "Cocos Engine Encryption Solution"
date: 2025-06-26 16:30:00 +0800
categories: anti-cheat
tags: Cocos  Encryption  Cocos Engine
---

According to the data, the global game market share of Cocos engine is about 20%. The advantage of Cocos engine is outstanding in 2D rendering, which is more suitable for the needs of small and medium-sized games. However, due to the open source nature of Cocos engine, hacks against Cocos engine are more rampant.<!-- more -->  

![315_21](/assets/res/2025/cocos.png)  

The main resources and code files of Cocos engine are located in the assets/ directory of the package, and let's take the JavaScript script as an example, the resources are stored in the .JSC file. Since the files can't be opened and compiled directly, the hacker will find libcocos2djs.so file in the engine's startup project, where the secret key is stored.

![315_21](/assets/res/2025/libcocos.png)  
The libcocos2djs.so file stores the Cocos secret key

SO file into IDA and other tools for disassembly, by searching for applicationDidFinishLaunching, you can find the secret key, and finally compile the secret key to get resources, code files.

![315_21](/assets/res/2025/keyofCocos.png)  
Use IDA tool to find the secret key of Cocos engine

In addition, there is another scripting language in Cocos engine, Lua. Compared with JavaScript, Lua is more suitable for making non-h5 games, and also faces serious hacking risks.

Since Lua is an interpreted language, the Lua virtual machine can directly interpret and execute the Lua source code, which leads many game developers to directly store the Lua source code in apk / ipa. This operation is equivalent to directly leaking the game source code, which greatly lowers the threshold for cheats, and also leads to the game being plagiarized by competitors.

Some game companies will use LuaJIT, custom Lua and other means, but in the face of professional decompilers, it is still difficult to escape being hacked.

![315_21](/assets/res/2025/luadec.png)  
Decompiler luadec

Resource files, as important assets of the game, store important resources such as pictures, code, audio and video, especially lua files in Cocos engine. Once leaked, it will cause a series of serious problems such as plagiarism by competitors, damage to intellectual property rights, dramatization of the game content, and tampering with the game resources to make and sell cheats, and so on.

How to effectively encrypt the Cocos engine and raise the threshold of hacking has become a must study for game manufacturers. JikGuard has developed a set of encryption protection solutions for Cocos engine to address the above problems:

**◆ Engine Module Reinforcement**

Game Hardening uses the industry's original SO shelling with no import function to protect the game code from being analyzed and prevent further operations by hackers.

**◆ JS Script Encryption**

Use high strength algorithm to encrypt JS scripts and prevent hacking scripts by HOOK.

**◆ C++ Code Encryption**

Encrypt the dynamic library after C compilation, and prevent it from being decompiled.

**◆ Lua Script Encryption**

Adopt deep encryption to ensure that Lua scripts can not be directly decrypted, support ulua/tolua/slua/xlua and other different Lua script encryption, and strengthen the Lua parsing module at the same time.

**◆ Resource Encryption**

JikGuard encryption is specially constructed, and the encryption solution only encrypts the core key positions, which has almost no effect on the game loading speed and running process.

**◆ Anti-Cheats**

In addition to all kinds of encryption protection, JikGuard Hardening solution also provides behavior detection means and anti-modifier, anti-debugging, anti-injection, anti-shifting and other anti-cheats features to better protect the Game Hardening security.

**◆ Anti-Hacking**

Adopting JikGuard's exclusive technology, “No API Signature Verification Technology”, which encrypts the game's engine and code from the bottom, it can perform multiple checks on the signature of the game packages and the integrity of the files, so as to prevent the game from being implanted with malicious modules and culling out advertisements.

In addition, JikGuard Cocos engine encryption protection solution has the following advantages:

**◆ Low Performance Overhead**

Pure native solution, security modules are all written in C++, which is highly efficient. Encryption and decryption algorithms use private obfuscation, greatly reducing performance overhead.

**◆ Multi-terminal interoperability, support for hot updates**

Cocos engine encryption solution supports Android / iOS / PC / H5 platforms, and supports online hot update of resources.

**◆ Convenient operation, low access cost**

It is very easy to use, just run a command line to complete the encryption of the entire game resources.