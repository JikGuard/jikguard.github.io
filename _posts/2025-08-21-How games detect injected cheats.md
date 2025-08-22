---
layout: post
title: "How games detect injected cheats"
date: 2025-08-21 16:30:00 +0800
categories: anti-cheat
tags: injected cheats  frida  IDA
---

In recent years, attacks by the black and grey industry for games have become increasingly diverse. If the protection of a game is breached at a certain point, cheats on the market will quickly iterate, causing serious damage to the game.
<!-- more --> 

In addition to common cheating methods such as memory modification and hacking, the black and grey industry for games also use ‘special plug-ins’ with relatively high barriers to entry. Special plug-ins are cheats customised for specific game play, also known as ‘injection cheats’.

![315_21](/assets/res/2025/securityissues.png)  
Games face a variety of security issues

These cheats often involve memory operations and have rich features, allowing them to inject functional modules into the game process space and execute the entry functions of the functional modules at the same time.

![315_21](/assets/res/2025/hook.png)  

In terms of the injection process, Android systems generally use SO injection, ptrace injection, Zygote injection, and ELF file infection to achieve the injection process. After jailbreaking, iOS systems can use the Cydia framework to inject dylib to achieve this.
 
After enabling the cheats and successfully injecting them into the game, the cheats call interface functions through menu operations, HOOK corresponding functions, rewrite parameters, or call logic to achieve the cheat functions.

![315_21](/assets/res/2025/apihook.png)  

Compared with modifier cheats, injection cheats are more flexible and diverse in modifying game code logic, and hackers will hide the injection module, making it more difficult and time-consuming to detect injection cheats.

In response to the risk of injection cheats in games, JikGuard has customised a special response strategy, which has been integrated into many popular games and has proven its excellent protection capabilities.

**Active identification of malicious module mechanism**

Unlike other security products on the market that require samples to be obtained before combating cheats, JikGuard's exclusive ‘active identification of malicious modules mechanism’ can actively identify suspicious modules in the game and, combined with online combat functions, achieve active defence, greatly shortening the cheat detection cycle.
 
**Anti-injector function**
Prohibits the use of various cheat module injectors such as Xposed and Frida to prevent various malicious behaviours such as modifying game memory after injection, and immediately crushes them once detected.
 
**Anti-debugging feature**
Prevents cheat authors from debugging the game and blocks static or dynamic analysis of the game. Once detected, it immediately crashes.