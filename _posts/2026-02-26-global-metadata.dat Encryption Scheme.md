---
layout: post
title: "global-metadata.dat Encryption Scheme"
date: 2026-02-26 16:30:00 +0800
categories: anti-cheat
tags: global-metadata.dat  unity  IL2CPP
---

In IL2CPP mode, the Unity engine can convert game C# code into C++ code, which is then compiled into native code for various platforms. This approach increases the difficulty of reverse engineering/decompilation to a certain extent.<!-- more --> 

![315_21](/assets/res/2026/2261.png) 

However, IL2CPP is not without its weaknesses. Numerous targeted reverse engineering tools have emerged on the market, such as IL2cppDumper.

First, let's understand how IL2CPP is Hacked. In Unity's IL2CPP mode, game logic runs as native code, but certain C# language features (such as GC and reflection) persist. These features log all C# class names, property names, strings, and other information into the global-metadata.dat file. When IL2CPP launches, it reads the required information from this file.

![315_21](/assets/res/2026/2262.png) 

Hackers use the IL2cppDumper tool to Hack the game. Simply drag the libil2cpp.so and global-metadata.dat files from the game package into the input folder, then run a single command line to complete the process.

Subsequently, the hack can drag the parsed dump.cs file into the Visual Studio parsing tool to directly analyze the source code:

![315_21](/assets/res/2026/2263.png) 

Hackers can exploit analyzed code logic to create various types of cheats, or even develop cracked versions, which severely undermine game fairness. This leads to significant loss of paying players and directly impacts developers' revenue, among other negative consequences.

Therefore, encrypting the game files libil2cpp.so and global-metadata.dat is essential. Based on the above circumstances, JikGuard has developed a comprehensive solution supporting Android, iOS, and PC platforms. It has been integrated into multiple popular games and demonstrated outstanding protection capabilities, primarily featuring the following functions:

**■ Encryption of global-metadata.dat File**

Encrypt the global-metadata.dat file while maintaining transparency for developers. Developers only need to run a single command line using the hardening tool to achieve encryption, without requiring the upload of additional files.

**■ libil2cpp.so Encryption**

Since IL2cppDumper relies on the string addresses within the global-metadata.dat file corresponding to libil2cpp.so, it is essential to apply deep encryption to libil2cpp.so.

JikGuard's proprietary SO packing solution, featuring no export/import functions, applies packing to il2cpp. After applying this encryption scheme, even if libil2cpp.so is dumped from memory, it remains undetectable by IL2cppDumper.