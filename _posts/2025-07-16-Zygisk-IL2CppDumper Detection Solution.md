---
layout: post
title: "Zygisk-IL2CppDumper Detection Solution"
date: 2025-07-16 16:30:00 +0800
categories: anti-cheat
tags: Zygisk  IL2CppDumper  JikGuard
---

As we all know, there are two script compilers in Unity engine, Mono and IL2CPP. These two script compilers have their own advantages, but there are also some security issues, this article will analyse them from the perspective of game security and provide solutions.<!-- more -->  

Mono is a cross-platform open-source .NET implementation, which allows developers to use C# and other programming languages to write game logic, providing a simple and easy-to-use environment for game development and efficient script compilation speed, which is favoured by some small and medium-sized games.

In Mono mode, the game C# code is compiled into IL (Intermediate Language) and generates dll files, and then the dlls are typed into the game package file. However, since IL is very easy to be analysed and reversed by professional decompilers such as ILSpy / .NET Reflector, the security of the game is very poor without protection.

![315_21](/assets/res/2025/NETReflector.png)  
.NET Reflector can almost restore C# files

Compared with Mono, IL2CPP can convert game C# code to C++ code, and then compile it to Native code for each platform.

Native code increases the difficulty of reverse/decompile, which can effectively increase the difficulty of game hacking and making cheats. In addition, IL2CPP also has the advantages of high execution efficiency and small memory consumption, and has been adopted by most games.

![315_21](/assets/res/2025/IL2CPPbuild.png)  
IL2CPP build project automatic step-by-step diagram

Although IL2CPP can improve game security to some extent, it is not without vulnerabilities. In IL2CPP mode, Unity records class names, property names, strings, and other information from C# code in the global-metadata.dat file, and the engine relies on this data to implement certain C# language features.

The engine relies on this data to implement certain C# language features. When IL2CPP starts up, it reads the required class names, property names, etc. from this file, which is the mechanism that gives hackers a chance to exploit.

A hacker can use IL2CPPDumper to parse the global-metadata.dat file, and then translate the class names and other string information in the file into Native code, which greatly reduces the difficulty of reverse analysis.

![315_21](/assets/res/2025/IL2CPPDumper111.png)  
IL2CPPDumper receives the path of libil2cpp.so / global-metadata.dat file

In the face of IL2CPPDumper's reverse analysis, the libil2cpp.so file and global-metadata.dat file can be encrypted to fight against it, so as to avoid the game code being analysed.

The emergence of reverse tools such as Zygisk-IL2CppDumper and funil2cpp has raised the intensity of game security confrontation to a new level.

![315_21](/assets/res/2025/Zygiskil2cppDumper.png)  
Reverse tool Zygisk-il2cppDumper interface and operation flow 

Zygisk-IL2CppDumper is a plug-in in Magisk, which is a brushing tool. Compared with the static analysis of IL2CPPDumper, Zygisk-IL2CppDumper has the following features: 

Zygisk-IL2CppDumper can be used to analyse the security of the game. IL2CppDumper can do dynamic dump function names and function offsets during game runtime, which can bypass protection, encryption, and obfuscation.

After launching the game, dump.cs will be automatically generated in the directory, even if the game has detected abnormal crushes, it will not affect the acquisition of dump.cs.

Zygisk-IL2CppDumper adopts github Action, only need to fork the project, fill in the package name and other simple steps to reverse analyse the code, which greatly reduces the threshold of cheats and hacks.

In response to the serious harm caused by Zygisk-IL2CppDumper reverse analysis tool to the game, JikGuard Game Protection has developed a set of mature and perfect countermeasure solution, which can effectively raise the threshold of analysis and hack.

**Magisk Special Detection** 
JikGuard's exclusive detection solution can still accurately identify and perform operations such as crushes when all hidden options of Magisk are fully opened.