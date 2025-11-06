---
layout: post
title: "How Games Counter IL2CppDumper Reverse Engineering"
date: 2025-11-06 16:30:00 +0800
categories: anti-cheat
tags: IL2Cpp  global-metadata.dat  IL2CppDumper
---

As is well known, the Unity engine has two script compilers: Mono and IL2CPP. Compared to Mono, IL2CPP offers advantages such as higher execution efficiency and cross-platform support, making it the preferred choice for most games.<!-- more -->

In IL2CPP mode, game C# code can be converted to C++ code and then compiled into native code for each platform. Native code increases the difficulty of reverse engineering/decompilation, effectively increasing the difficulty of developing cheats and hacking games.

![315_21](/assets/res/2025/IL2CPP.png)  
IL2CPP project build automatic step diagram

Although Unity IL2CPP makes cheating more difficult to a certain extent, it is not without its weaknesses. There are many targeted reverse engineering tools on the market, such as IL2cppDumper.

This article will focus on analysing how games should respond to IL2cppDumper's reverse engineering in IL2CPP mode and provide effective solutions.

First, let's understand how IL2CPP is hacked.

In Unity IL2CPP mode, game logic runs as native code, but certain C# language features (such as GC and reflection) still exist. These features record all class names, property names, and strings from C# into the global-metadata.dat file. When IL2CPP starts, it reads the necessary information from this file.

![315_21](/assets/res/2025/IL2CPPso.png)  
The relationship between IL2CPP.so and global-metadata.dat

Hackers only need to unzip the game package, find the libil2cpp.so and global-metadata.dat files, drag them into the input folder, and run a command line to complete the reverse analysis.

Then, they can drag the parsed dump.cs file into the Visual Studio parsing tool to directly analyse the source code:

![315_21](/assets/res/2025/VisualStudio.png)  
Visual Studio can parse the code in the .cs file

In this way, the game is no different from "running naked" in the eyes of hackers. Hackers can use the analysed code logic to create various types of cheats and even create hacked versions, which will seriously affect the fairness of the game, cause a large loss of normal paying players, and directly damage the manufacturer's revenue.

Based on this situation, JikGuard has developed a complete solution that supports Android/iOS/PC multi-end. It has been integrated into many popular games and has proven its excellent protection capabilities. It mainly includes the following features:
 
**■ global-metadata.dat file encryption**

Encrypt the global-metadata.dat file while remaining transparent to developers. Developers only need to run a command line using the reinforcement tool to achieve encryption, without the need to upload additional files.
 
**■ libil2cpp.so obfuscation**

Since IL2cppDumper relies on the string addresses in the global-metadata.dat file corresponding to libil2cpp.so, deep encryption of libil2cpp.so is essential.

JikGuard's unique no-export/no-import function SO shell solution shells il2cpp. After encryption, even if libil2cpp.so is dumped from memory, it will still not be recognised normally by IL2cppDumper.

In addition, JikGuard also provides anti-cheat, anti-hacking, and resource encryption features, which are closely coupled with the engine reinforcement feature to take game protection to the next level.