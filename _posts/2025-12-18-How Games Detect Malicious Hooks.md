---
layout: post
title: "How Games Detect Malicious Hooks"
date: 2025-12-18 16:30:00 +0800
categories: anti-cheat
tags: Malicious Hooks  Hook  Cheat Engine  Frida
---

A hook is a technique that allows developers to insert custom code when specific events occur. This technology is commonly used to modify or extend existing software behavior without altering the source code. It is frequently employed to intercept function calls, modify data, or execute other custom modules.<!-- more --> 

Due to the inherent characteristics of hooking technology, it has been exploited by the Game Black/Gray Industry. By leveraging hooking and injection techniques, cheaters inject malicious code into game processes, enhancing the stealthiness of their cheating activities and complicating the analysis of malicious code. Compared to traditional, generic cheating methods, hooking technology poses greater challenges for detection.

Malicious hooks are typically implemented through three methods: hooking code, hooking system functions, and hooking security modules. This article will analyze their implementation principles through case studies and propose corresponding solutions.

**Hook Code**

Hook code is a common method for malicious hooking. We will analyze this using a Unity engine IL2CPP framework game as an example.

First, Cheater extracts the game package, locates the global-metadata.dat and libil2cpp.so files, and uses Il2CppDumper to parse them. The generated dump.cs file enables reverse engineering of the game's symbol table and addresses, revealing critical information such as coins, health points, attack power, and more. Finally, they hook relevant functions, modify parameters, or manipulate call logic to implement various cheat Features.

![315_21](/assets/res/2025/12181.png)  
Frida Framework Hook Operation Process

Compared to traditional universal cheating methods, hook code-based cheat tools are more covert. Cheater also employs additional techniques to conceal their signatures, making detection significantly more challenging.

**Hook System Functions**

Hook system functions are commonly used to create speed hack cheats. Cheater typically employs Cheat Engine modifiers, whose speed-altering mechanism involves hooking the following three time-related functions:

timeGetTime;
GetTickCount;
QueryPerformanceCount

Cheat Engine modifiers record the start time of each step, obtain the address of the time function, and use hooking operations to jump to a custom function. Within this custom function, they modify the return value or output parameters. The specific calculation formula is: current time + (current time - start time) * desired multiplier.

![315_21](/assets/res/2025/12182.png) 
Cheat Engine Speed Hack

Moreover, the trend toward high-level cheating methods is becoming increasingly pronounced. Cheaters run mobile games within PC emulators, using Cheat Engine modifiers to hook system functions and achieve global speed manipulation. They then manufacture and sell these speed hacks. Such sophisticated cheating bypasses traditional detection methods, significantly increasing the difficulty of detection and investigation.

**Hook Security Module**

The Hook Security Module represents a more aggressive approach to security countermeasures. Cheater attempts to bypass or circumvent the game's security detection modules entirely, rendering the game's security detection methods ineffective.

In such scenarios, even encrypted games may encounter issues like hacking and cracking, presenting a comprehensive test of the game hardening product's capabilities. While ensuring robust security detection capabilities, it is also essential to safeguard the security modules themselves.

To address hooking risks in games, JikGuard has developed specialized countermeasures. This solution has been integrated into multiple popular games and has demonstrated outstanding protection capabilities.
Proactive Malicious Module Detection Mechanism

Unlike other security products on the market that require obtaining samples before combating cheats, JikGuard's exclusive “Proactive Malicious Module Detection Mechanism” actively identifies suspicious modules within games. Combined with its online countermeasure features, it enables proactive defense, significantly reducing the time required to investigate and eliminate cheats.

**Anti-Debugging Features**

Prevents cheater from debugging the game and blocks static or dynamic analysis. Upon detection, the game will immediately crash.

**Speed hack crush feature**

Using more low-level detection methods and extensive testing on actual machines, it can ignore any speed s and their variants. Once a speed hack is detected, the game will immediately crash.

**anti-hack Features**

JikGuard's industry-exclusive “API Signature Verification-Free Technology” employs deep encryption on game engines and code, coupled with multi-layered verification of game package signatures and file integrity. This significantly reduces the possibility of bypassing security measures, preventing malicious modules from being implanted into games or advertisements from being stripped out.