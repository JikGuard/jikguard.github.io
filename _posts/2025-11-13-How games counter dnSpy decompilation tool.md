---
layout: post
title: "How games counter dnSpy decompilation tool"
date: 2025-11-13 16:30:00 +0800
categories: anti-cheat
tags: dnSpy  Mono  Unity
---

Unity Mono serves as the default script runtime environment for the Unity engine, implemented via the cross-platform open-source .NET framework. It enables developers to write game logic using programming languages such as C#. Thanks to its user-friendly development environment and efficient script compilation speed, it has gained favour among numerous games.<!-- more -->

In Mono mode, game C# code is compiled into IL (Intermediate Language) and packaged into DLL files, which are then embedded within the game files.

However, since IL is highly susceptible to analysis and reverse engineering by decompilation software, its security is extremely poor without protection, making hack and analysis remarkably easy. How to effectively encrypt it has become a major industry challenge.

![315_21](/assets/res/2025/11134.png)  
Script compilation and execution in Mono mode

This article will demonstrate through case studies the characteristics of the decompilation tool dnSpy, analyse how games should counter reverse engineering and hack issues, and propose effective solutions. 

dnSpy is a free, open-source, cross-platform .NET debugging tool and decompiler that enables code debugging and modification without source code. Leveraging support for multiple languages including IL and C#, dnSpy can decompile .NET programme binary files back into source code.

![315_21](/assets/res/2025/11135.png)  
dnspy function parsing results

To prevent reverse engineering, some games employ DLL function encryption. This approach has the advantage that decryption occurs only when a method is invoked. Since games typically do not utilise all methods during execution, a complete DLL never resides in memory.

![315_21](/assets/res/2025/11136.png)  
function encryption causes dnSpy parsing errors

However, DLL hardening solution still has drawbacks. Using disassembly tools, function names and some functions can be viewed, making them susceptible to analysis and exploitation by hackers, posing certain security risks.

To safeguard game code, the paramount objective is to eliminate clues for hackers. To this end, JikGuard has developed the "DLL Structure Virtualisation" features:

The file structure of DLLs can be customised and restructured, with the structural data subjected to high-strength encryption. Once processed, no tools can extract any data whatsoever; even for professional hack reverse-engineering analysts, decrypting the internal structural data presents an immense challenge.

![315_21](/assets/res/2025/11137.png)  
Virtualised DLL structure cannot be properly parsed by 010 Editor

Additionally, the JikGuard game hardening solution offers encryption features for files such as global-metadata.dat and libil2cpp.so, alongside a cross-platform Unity Assetbundle resource encryption solution.

To ensure comprehensive game protection, our solution incorporates multiple features including anti-cheat, anti-hack, anti speed hack, and anti-debugging, effectively addressing various security challenges faced by games.
 
**Anti-Cheat Features**

To address the threat of memory modification in gaming environments, JikGuard has developed a behavioural detection solution capable of precisely identifying memory tampering activities. This solution comprehensively eliminates all types of modification tools and their variants, delivering effective protection.
 
**Anti-Hack Features**

JikGuard's proprietary API-free signature verification technology employs deep encryption on game engines and code, alongside multi-layered verification of game package signatures and file integrity. This prevents the game from being hacked, malicious modules from being implanted, or advertisements being stripped out.
 
**Anti Speed Hack Features**

Employing more low-level detection methods, extensively tested on actual devices, it identifies any speed hacks and their variants. Upon detecting speed manipulation, the game immediately crushes.
 
**Anti-Debugging Features**

Prevent cheats authors from debugging the game, block static or dynamic analysis of the game, and trigger an immediate crush upon detection.