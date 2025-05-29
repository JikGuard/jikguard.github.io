---
layout: post
title: "Explanation of Unity Engine Encryption Solutions"
date: 2025-03-17 16:30:00 +0800
categories: anti-cheat
tags: Unity  Solutions  Encryption
---

It is reported that the global market share of Unity engine has exceeded 50%, and among the top 1,000 handheld games in the world, this figure is as high as 73%. The huge volume attracts black and gray industry, and Unity-developed games have become the hardest hit by attacks. Hacking and reversing tools for Unity engine are endless, such as: reversing tools Il2CppDumper, dnSpy, resource parsing tool AssetStudio and so on.<!-- more -->  

Next, we will analyze the features of these tools through case studies, and analyze how to deal with the reverse and hack problems in Unity engine games, and put forward effective solutions.

◆ Il2CppDumper

In Unity il2cpp mode, all the class/property/string information in C# will be recorded in global-metadata.dat file. il2cpp will read the required class/property information from this file when it starts.

This mechanism is convenient for plugin creation/game hack. IL2cppDumper can parse the global-metadata.dat file and translate the class name/property name information into Native code, which is very convenient for reverse analysis.

![315_21](/assets/res/2025/IL2cppDumper1.png)  
▲ IL2cppDumper can parse .cs/.json files without encryption

Drag the parsed .cs file into the Visual Studio parsing tool to analyze the source code directly:

![315_21](/assets/res/2025/VisualStudio.png)  
▲ Visual Studio can parse the code in a .cs file

◆ dnSpy

In Unity mono mode, the game C# code is compiled into IL (intermediate code) and generate dll file, then the DLL is typed into the game package file. However, since IL is very easy to be analyzed and reversed by professional decompilers such as ILSpy / dnSpy, the security of the game is extremely poor without protection.

dnSpy is an open source, cross-platform .NET debugger and decompiler that allows you to debug and modify code without source code. With support for languages such as IL and C#, dnSpy is able to decompile .NET program binaries into source code.

![315_21](/assets/res/2025/dnspy1.png)  
▲ Unencrypted source code parsed by dnspy function

◆ AssetStudio

AssetStudio is an open source Unity resource parsing tool that recognizes Unity's binary resource file format and decodes it into readable data structures. Simply import the resource file, and you will be able to easily view and export 3D models, textures, audio, and various other resource types supported by Unity.

![315_21](/assets/res/2025/AssetStudio.png)  
▲ AssetStudio can parse out a large number of game resources

**Based on more than ten years of experience in game security, JikGuard has developed a set of mature and perfect solutions for Unity engine. With a number of exclusive technologies as the cornerstone, it has built a comprehensive Unity game protection matrix and provides customized solutions, including the following features:**

**File/code tampering prevention**

High-strength encryption for mono DLL / global-metadata.dat / libil2cpp.so files in Unity engine.

**Mono DLL encryption**

JikGuard goes deep into the game engine and builds the third generation encryption method - DLL structure virtualization. It customizes and reconstructs the file structure of the DLL and encrypts the file structure data with high strength.

After the encryption process, all the tools can not parse out any data, the encryption scheme can effectively raise the threshold of hack, to avoid the game being hacked by reverse analysis.

![315_21](/assets/res/2025/dnspy2.png)  
▲ Error parsing dnspy function after encryption

**Encrypt global-metadata.dat file**

Encrypt the global-metadata.dat file and make it transparent to developers. The developer only needs to run a command line with the hardening tool to realize the encryption, and does not need to upload additional files.

**Encrypting libil2cpp.so files**

To encrypt libil2cpp.so file, it is necessary to deeply encrypt libil2cpp.so because IL2cppDumper relies on the string address in the global-metadata.dat file corresponding to libil2cpp.so.

After encrypting libil2cpp.so, even if libil2cpp.so is dumped from memory, it will not be recognized by IL2cppDumper, the result is as below:

![315_21](/assets/res/2025/IL2cppDumper2.png)  
▲ After encryption, IL2cppDumper cannot parse it.

**Unity AB Resource Encryption Program**

JikGuard's exclusive resource encryption solution supports Android, iOS, PC, H5 and Hongmeng. The encryption solution goes deep into the bottom layer of the game engine, combining the structure of the game resource file and loading mechanism to carefully construct.

It can provide high-intensity encryption protection for game resources, and at the same time, it has the features of high compatibility, low running consumption, no performance impact, and supports online update of resources.

In addition, the solution optimizes the access process, realizing features such as no need for development docking and access, and encryption/decryption transparency to development.

**In addition to the above in-engine file/code/resource encryption, JikGuard also provides anti-cheat and anti-hack functions, which are tightly coupled with the engine hardening function to enhance the game protection effect.**
 
**Anti-Cheat Functions**

In response to a series of cheats modification risks faced by the game, JikGuard has developed a behavioral detection solution with a 300+ dimensional intelligent sensing system, which can kill all kinds of cheats and their variants to achieve effective protection.
 
**Anti-Hack Function**

JikGuard's industry-exclusive technology, “No API Signature Verification Technology”, encrypts the game's engine and code from the bottom up. It can perform multiple checks on game package signatures and file integrity, preventing the game from being implanted with malicious modules and removing advertisements.
 
**Anti-SpeedHack Function**

Adopting more underlying detection means and tested by a large number of real machines, and will immediately flashback the game once it detects a speedhack situation.
 
**Anti-debugging Function**

Prevent cheats authors from debugging the game, prevent static or dynamic analysis of the game, once IDA/frida and other debugging and analyzing tools are detected, the game will be flashed immediately.