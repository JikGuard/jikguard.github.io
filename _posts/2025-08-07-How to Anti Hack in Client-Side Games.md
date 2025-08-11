---
layout: post
title: "How to Anti Hack in Client-Side Games"
date: 2025-08-07 16:30:00 +0800
categories: anti-cheat
tags: Client-Side  Anti Hack  Games
---

Hogwarts Legacy, a spin-off of the world-class Harry Potter IP, has won the hearts of many gamers. With all the glamour, Hogwarts Legacy was soon targeted by a famous game hacking organisation, which threatened to crack it "under 10 days and spread it, and everyone will be playing it for free".<!-- more -->  

![315_21](/assets/res/2025/hackinggroup.png)  
A hacking group threatened to crack Legacy of Hogwarts "under 10 days"

Subsequently, a hacked version of Hogwarts Legacy was released and spread widely. For a game that has just been released, such a "declaration" will undoubtedly deal a serious blow to the sales of the game, and once the game is hacked, it will face the tragic situation of having no income at all.

As a matter of fact, the problem of hacking games has always been a problem for game makers. In this article, we will take Unity engine games as an example, combined with practical cases, to provide you with a detailed analysis of the client-side games facing the problem of hacking and the solution.

**■ Risk of symbol file extraction**

For Unity programs of il2cpp type, the global-metadata.dat stores all the class names and method names of the program.

If it is exposed without encryption, an attacker can extract and exploit it with tools such as iL2CppDumper, which is very effective for reverse analysis.

![315_21](/assets/res/2025/Unencrypteddatfile.png)  
Unencrypted dat file for symbol extraction

**■ The core code logic is extremely easy to decompile**

For Mono type Unity programs, the user-written code ends up in the core assembly file Assembly-CSharp.dll, which is a standard .NET file format with rich metadata information such as method names, class names, type definitions, etc. Tools such as DnSpy can easily decompile and tamper with it, and the code logic, class and method names, etc., are as easy as looking at C# source code. 

![315_21](/assets/res/2025/DnSpydecompiler.gif)  
Demonstration of DnSpy decompiler

For il2cpp type Unity application, the code written by the user will eventually be compiled into native code, which is a bit safer than the above Assembly-CSharp.dll. However, for experienced hackers, if it is not further encrypted, it can be effectively analysed through the Ghidra static analysis tool.

**■ Risks of easy extraction of game resources**

Unity3D programs are compiled and packaged into AssetBundle files through the Unity editor. AssetBundle is a publicly available compressed file format, which can be parsed, displayed, and extracted using tools such as AssetStudio.

![315_21](/assets/res/2025/resourcefilesba.png)  
Comparison of the decompilation effect of resource files before and after JikGuard encryption

**To address the problems of hacking and resource leakage faced by client-side games, JikGuard Game Hardening adopts a well-constructed purely native solution and provides a series of protection features:**

● Anti-debugging: detect whether the game process is debugged.

● Anti frame capture: detect whether the game process is captured by frame capture tools.

● Anti-injection: detect whether the game is injected by malicious modules.

● Anti multi-instance: Disable game multi-instance.

● Anti-VM: prohibits the game from running in a virtual machine.

● Anti malware tools: detects whether there are malicious tools in the game running environment.
 
**Smooth gaming experience, no impact on performance**
JikGuard encryption is specially constructed to decrypt resources only when they are used, so they are still encrypted when they are released to the cache. The encryption solution only encrypts the core key locations, and has almost no impact on the game loading speed and running process, making it a non-perceptive solution.
 
**Zero Access Cost, Automated Configuration**
JikGuard optimises the encryption process and constructs a minimalist encryption model, with no need to access the SDK or perform complex configuration, just set a gamekey and run a command line to encrypt the game.