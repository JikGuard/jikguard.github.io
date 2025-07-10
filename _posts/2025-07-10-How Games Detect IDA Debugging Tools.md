---
layout: post
title: "How Games Detect IDA Debugging Tools"
date: 2025-07-10 16:30:00 +0800
categories: anti-cheat
tags: frida  IDA  Debugging
---

IDA, known as Interactive Disassembler Professional, is an interactive static disassembly tool that can directly disassemble the assembly code of binary files, and is one of the most powerful tools in the field of reverse analysis.<!-- more -->  

IDA supports multiple platforms such as Windows, Linux and dozens of instruction sets, and is widely used in reverse analysis thanks to its ubiquity and friendly graphical interface.

However, IDA is also used by hackers. Many hackers use IDA to analyse the logic of game code and look for key functions for hook operation, so as to achieve the purpose of bypassing the protection and hacking the game.

![315_21](/assets/res/2025/IDAinterface.png)  
IDA interface 

Thanks to the powerful disassembly ability, the application of IDA greatly reduces the threshold of game cracking, and the steps are as follows: 

1. Open the executable file of the target game in IDA, and then it can be analysed, and the binary file can be disassembled and converted into easy-to-read and analyse assembly code.

2. Use IDA's graphical interface to browse the analysed code and function calls and other relationships. By analysing the relationships between the codes, you can better understand the code logic of the game.

3. Find key functions through IDA's search features, such as character attack, win/loss logic, etc. By double-clicking on the key functions, you can view the detailed code and find out the points where you can carry out hook operation, so as to complete the hacking of the game.

![315_21](/assets/res/2025/IDAandFrida.png)  
IDA and Frida joint debugging APK 

In addition to powerful disassembly capabilities, IDA can also achieve remote debugging SO files and direct debugging of pseudo-code, so IDA can also be used to bypass the existing protection within the game.

![315_21](/assets/res/2025/IDAremote.png)  
IDA remote debugging SO library 

From the perspective of game security, in order to combat debugging attacks, you need to start from the shelling protection, anti-debugging two aspects. JikGuard for the game encountered the above problems, to provide customized solutions, the protection solution has been accessed a number of popular games and verified the excellent protection ability.

**No import function SO shelling technology**

JikGuard's exclusive technology provides the strongest level of encryption protection deep into the game's bottom layer, protecting the game code from being analysed and preventing further operations by hackers.

**Anti-debugging features**

Prevents cheats authors from debugging the game, prevents static or dynamic analysis of the game, and immediately flashes back once IDA/frida and other debugging and analysis tools are detected.

**Anti-hack features**

JikGuard's exclusive API-free signature checking technology deeply encrypts the game's engine and code, and performs multiple checks on game package signatures and file integrity to prevent the game from being implanted with malicious modules, culling advertisements, and so on.