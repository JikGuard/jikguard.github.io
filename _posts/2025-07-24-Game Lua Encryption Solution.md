---
layout: post
title: "Game Lua Encryption Solution"
date: 2025-07-24 16:30:00 +0800
categories: anti-cheat
tags: Zygisk  IL2CppDumper  JikGuard
---

Lua with its small and fast characteristics has gradually become the majority of game developers must study, so the security of Lua for game developers is very important.<!-- more -->  

**I. The use of Lua in mobile game scenarios**

**1. Cocos2dx Engine**

In Cocos2dx engine, the main scripting languages available are Lua and Javascript, which are widely used because they are more suitable for making non-h5 games.

![315_21](/assets/res/2025/724011.png)  

**2. Unity3d Engine**

The native scripting language of Unity3d engine is C#, but due to iOS system security restriction, it is impossible to hot update C#, so there are many hot update frameworks using Lua, such as toLua / uLua / xLua, etc. These frameworks will take the Unity3d engine to the next level. These frameworks encapsulate the Unity3d engine APIs into Lua interfaces, giving game developers the ability to develop game logic/interfaces using Lua scripts. When a hot update is needed, the server can dynamically send the Lua script and the client can load the new Lua script to update the game logic/interface.

**II. Lua Script Security Issues**

Since Lua is an interpreted language, Lua VM can directly interpret and execute Lua source code, which leads many game developers to directly put Lua source code in apk/ipa, which is equivalent to directly leaking the game source code, greatly reducing the threshold of cheats production, and more likely to be copied or stolen.

In actual development, developers can choose to use official Luac or LuaJIT to compile Lua scripts into bytecode, but they both face similar security issues.
 
**1. Official Lua**

Developers can use Luac to compile Lua source code into Lua bytecode.

![315_21](/assets/res/2025/724022.png)  

Looking at the bytecode above, it no longer contains source code, only function names and strings. However, Lua bytecode is very easy to be decompiled by tools like luadec / unluac, and the decompiled Lua code is almost the same as the source code.

**2. LuaJIT**

Since LuaJIT can improve the efficiency of Lua code execution dozens of times when JIT is enabled, many games/frameworks use LuaJIT to replace the official Lua virtual machine.

![315_21](/assets/res/2025/724033.png)  

Accordingly, developers can use the luajit executable to compile Lua source code into luajit bytecode.

![315_21](/assets/res/2025/724044.png)  

There are also decompilers for luajit bytecode, such as ljd, luajit-decomp.

**III. Common Lua protection solutions**

**1. Cocos2dx xxtea encryption**

The cocos compile command provides parameters such as --lua-encrypt to encrypt Lua scripts:

Lua related parameters:
--lua-encrypt  Enables XXTEA encryption features.
--lua-encrypt-key LUA_ENCRYPT_KEY  Specifies the key field for the XXTEA encryption features.
--lua-encrypt-sign LUA_ENCRYPT_SIGN  Specify the sign field of XXTEA encryption features.

But this encryption is very easy to hack, as shown below, cheats can easily find the key of xxtea in libcocos2dlua.so, and then decrypt the script.
 
**2. Custom Lua opcodes**

Some games have custom Lua opcodes, so that regular luadec / unluac can't decompile the bytecode. A large turn-based game adopts this protection method, which can raise the threshold of making cheats, but due to the insufficient protection strength of the code itself, the opcodes can be easily restored and then decompiled.

![315_21](/assets/res/2025/724055.png)  

**IV. Lua protection solution by JikGuard**

JikGuard has launched a new Lua script protection solution based on in-depth understanding of Lua language features and the underlying virtual machine to ensure that Lua scripts can not be analysed and hacked from all aspects.
 
**1. Deep encryption of bytecode files**

Cocos2dx uses xxtea to encrypt the whole script file, which is not only easy to be analysed to find out the encryption key, but also easy to be hooked luaL_loadbuffer to get the plaintext file. We use deep encryption to ensure that Lua scripts cannot be decrypted directly, and that plaintext scripts cannot be intercepted by hooking luaL_loadbuffer / lua_reader.

Normal bytecode:

![315_21](/assets/res/2025/724066.jpg)  

The bytecode after we protect it:

![315_21](/assets/res/2025/724077.png)  

**2. Runtime dynamic protection**

JikGuard goes deep into the virtual machine engine and uses compression/obfuscation/dynamic deformation to customise unique runtime information, further increasing the difficulty of reverse analysis.
 
**3. Lua Virtual Machine Code Protection**

Lua VM code is not easily reverse-analysed with strong so hardening. Normal Lua VM Native layer code has a lot of Lua interfaces:

![315_21](/assets/res/2025/724088.png)  

JikGuard processed Lua virtual machine Native layer code, no interface can be seen:

![315_21](/assets/res/2025/724099.png)  

**4. Easy access**

No need to change the upper layer of Lua script code when accessing, transparent to developers.
 
**5. Support Platform**

iOS, Android, and PC platforms are fully covered.

JikGuard examines the Lua script security issue from multiple attack perspectives, and launches a new Lua script protection solution from various levels of the Lua language, which can provide high strength protection for Lua code. JikGuard supports official Lua and LuaJIT, Cocos2dx engine, and Unity3d plugins such as uLua / toLua / xLua.