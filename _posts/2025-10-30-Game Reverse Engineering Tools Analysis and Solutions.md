---
layout: post
title: "Game Reverse Engineering Tools Analysis and Solutions"
date: 2025-10-30 16:30:00 +0800
categories: anti-cheat
tags: speed-hack  cheat engine  GameGuardian
---

Game reverse engineering refers to the process of decompiling and analysing game source code using various tools to attempt to analyse the game's implementation logic. This process requires the use of techniques such as decryption, decompilation, and decompression, with the aim of restoring or analysing the game's code logic and resources.<!-- more -->

Game reverse engineering tools can be classified according to different features, such as: dynamic debugging injection tool Frida; static analysis tool IL2CppDumper; MT Manager with APK editing and signature verification removal features; and memory modification tool GameGuardian Modifier, etc.

This article will analyse the implementation principles of some common game reverse engineering tools through case studies and propose solutions.

**◆ Frida**

Frida is a dynamic instrumentation tool that can insert external code into the memory space of native apps for dynamic debugging and modification.

Frida calls the system ptrace to inject the frida-agent-xx.so module into the game process, and communicates with the frida-server installed on the mobile phone through this module to perform a series of analysis and hook operations, such as hooking the attack function of your own character in the game to achieve cheats.

![315_21](/assets/res/2025/10301.png)  
Frida and ida joint debugging APK

Frida has a simple configuration environment and is easy to operate. It supports Java layer and Native layer hook operations, and uses "glue languages" such as python and JavaScript to lower the threshold for reverse analysis and cheating modifications.

Additionally, Frida has numerous variants, such as the commonly used hluda-server, which can hide Frida's characteristics, bypass traditional detection methods, and increase the difficulty of detection and investigation.

**◆ IL2CppDumper**

As is well known, the Unity engine has two script compilers: Mono and IL2CPP. IL2CPP can convert game C# code into C++ code and then compile it into native code for various platforms.

In IL2CPP mode, Unity records class names, property names, strings, and other information from C# code in the global-metadata.dat file, and IL2CPP reads the required class names, property names, and other information from this file when it starts.

Hackers can use IL2cppDumper to parse the global-metadata.dat file and map the class names and other string information in the file to the native code, greatly reducing the difficulty of reverse analysis.

![315_21](/assets/res/2025/10302.png)  
Reverse engineering tool Zygisk-il2cppDumper 

As the intensity of the confrontation escalated, Zygisk-IL2CppDumper was born. It can dynamically dump function names and function offsets during game execution, bypassing protection, encryption, and obfuscation.

After the game is launched, dump.cs will be automatically generated in the directory. Even if the game detects an abnormal crash, it will not affect the acquisition of dump.cs.

Zygisk-IL2CppDumper uses github Action, and only requires simple steps such as forking the project and filling in the package name to reverse engineer the code, greatly reducing the threshold for cheats and hacks.

**◆ MT Manager**

MT Manager is a reverse engineering modification tool software on the Android platform. It has dual-window file management and APK editing features, which can efficiently perform various file operations and modify Android software.

After obtaining root permissions, MT Manager can access the system directory, mount the file system for reading and writing, and modify file privileges and owners. Its main features are APK editing, including DEX editing, XML editing, APK signing, signature verification removal, RES resource deobfuscation, etc.

![315_21](/assets/res/2025/10303.png)  
MT Manager

**◆ GameGuardian Modifier**

GameGuardian provides manual memory search and modification features and also supports script calls. Calling scripts can locate and modify memory to achieve automatic hacking.

![315_21](/assets/res/2025/10304.jpg)  
GameGuardian Modifier calls lua scripts to implement cheating functions

The use of GameGuardian Modifier requires the device to provide a root environment. Even if systems after Android 6.0 do not provide root permissions, hackers will use virtual machines, virtual frameworks, etc. to simulate a root environment and provide high permissions for the modifier.

In addition, the modifier also has anti-detection features to prevent it from being detected by the game, greatly increasing the difficulty of detection.

![315_21](/assets/res/2025/10305.jpg)  
GameGuardian Modifier calls lua scripts to implement cheating functions

In response to various reverse engineering attacks faced by games, JikGuard has customised a mature and comprehensive solution, which has been integrated into many popular games and has proven its excellent protection capabilities.
 
**Anti-hack features**

JikGuard's exclusive "API-Free signature verification technology" encrypts the game engine and code at the low-level, enabling multiple verifications of game package signatures and file integrity to prevent malicious modules from being implanted in the game and remove advertisements.
 
**Anti-memory modification features**

In response to the risk of memory modification faced by games, JikGuard has devoted itself to the research and development of a "behaviour detection solution". Through a sensitive intelligent perception system, once a modification is detected, it can immediately crush all types of modification cheats and their variants, providing effective protection.
 
**Active identification of malicious module mechanism**

Unlike other security products on the market that require samples to be obtained before combating cheats, JikGuard's exclusive "active identification of malicious modules mechanism" actively identifies suspicious modules and, combined with online combat functions, achieves active defence, greatly shortening the cheat investigation cycle.
 
**Anti-injector features**

Prohibits the use of various cheat module injectors such as Xposed and Frida, preventing various malicious behaviours such as modifying game memory after injection, and immediately crashes the game once detected.
 
**Anti-debugging feature**

Prevents cheats from debugging the game and blocks static or dynamic analysis of the game. Once detected, it immediately crushes the game.
 
**Security environment detection feature**

Unlike other products on the market, JikGuard's hardening uses more low-level detection methods to accurately identify various risk environments such as virtual frameworks, virtual machines, jailbreaks, ROOT, and cloud phones, and provides customized crush strategies.