---
layout: post
title: "Unity Mono Encryption Solution"
date: 2025-07-10 16:30:00 +0800
categories: anti-cheat
tags: Unity  Unity Mono Encryption  Unity Encryption
---

Unity Mono is the default scripting runtime environment of the Unity engine, which is very important in game development. Mono is implemented by the cross-platform open source .NET framework, which allows developers to write game logic in programming languages such as C#. It has been adopted by many games because of its easy-to-use development environment and efficient script compilation speed.<!-- more -->  

In Mono mode, the game C# code is compiled into IL (Intermediate Language) and generates a DLL file, which is then typed into the game package file.

![315_21](/assets/res/2025/Monomode.png)  
The scripts are compiled and run in Mono mode

However, since IL is very easy to be analysed and reversed by professional decompiler such as ILSpy / .NET Reflector, it is very difficult for hackers to analyse it without protection, and the security of the game is very poor, so how to effectively encrypt Unity Mono has become an important issue for the industry.

![315_21](/assets/res/2025/NETReflector.png)  
.NET Reflector can almost restore the C# file

The encryption solution for DLLs has gone through three generations of technological evolution, starting with the first generation of encryption - DLL encryption as a whole.

The principle is to modify the mono_image_open_from_data_with_name function in the Mono source code to encrypt the DLL script as a whole. The disadvantages of this encryption method are more obvious, it will be decrypted once before loading, during the game running process, there is a decrypted complete DLL in the memory, you can use some tools to get the DLL file from the memory.

The second generation of DLL encryption - DLL function encryption. The advantage of this encryption method is that only the method will be decrypted, while the general game running process will not use all the methods, so that there will not be a complete DLL in memory. The effect of the method decryption is shown in the following figure: 

![315_21](/assets/res/2025/dnspy1.png)  
The original unencrypted dnspy function parsing results

![315_21](/assets/res/2025/dnspy2.png)  
Function encrypted dnspy function parsing error 

The second generation of Game Hardening solution still has a disadvantage, the use of parsing tools The second-generation DLL hardening solution still has shortcomings, using a parsing tool, you can see the function name and part of the function, there are certain security risks.

JikGuard has developed the third generation of DLL hardening solution - DLL structure virtualization. The file structure of the DLL can be customised and reconstructed, and the file structure data can be encrypted with high strength.

After processing, all tools can no longer parse out any data, even for professional hackers, it is very difficult to decrypt the structure data inside.

The data structure used by DLL scripts is the same as the executable files under Windows, they are all PE structure. When the DLL is not virtualised, 010Editor can parse out the normal PE structure. But after using DLL structure virtualization, 010Editor can't parse it normally, the effect is as follows: 

![315_21](/assets/res/2025/010Editor.png)  
DLL structure after virtualization can't be parsed by 010Editor 

JikGuard Game Protection has developed a set of mature and perfect countermeasure solution, which can be used against mono DLL / global-metadata.dat / libil2cpp.so etc. in Unity engine, and has also developed a Unity Assetbundle resource encryption solution that is common to all three ends.

In addition, JikGuard Game Protection also provides other protection features, including anti-memory modification, anti-speed hack, anti-debugging, file integrity checking and many other features, which can effectively solve the security problems faced by the game.