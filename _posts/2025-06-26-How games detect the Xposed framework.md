---
layout: post
title: "How games detect the Xposed framework"
date: 2025-06-26 16:30:00 +0800
categories: anti-cheat
tags: Xposed  framework  injection cheats
---

Among the security risks faced by games, in addition to common cheats such as memory modification, speed hack and hacking, there is also a category of seriously harmful cheats - “injection cheats”.<!-- more -->  

According to statistics, injection cheats accounted for as much as 21% of the security risks faced by games. Such a high percentage shows the seriousness of the harm caused by injection cheats.

![315_21](/assets/res/2025/JikGuardstatistics.jpg)  
JikGuard statistics: the proportion of game security risks

The realization principle of injection cheats is also very diversified, Android system can use SO injection, ptrace injection, Zygote injection and infected ELF files and other ways to realize.

In this article, we will focus on the injection principle and solution of Xposed framework.

![315_21](/assets/res/2025/Xposedframework.jpg)  

In Android system, all application processes are incubated by Zygote processes, and the principle of Xposed is to control Zygote processes by replacing /system/bin/app_process program. Whenever a game process is started, the Xposed-replaced file is launched first and the relevant code is loaded to complete the injection.

After the injection, you can use the Xposed framework's Hook feature, which is expressed as inserting custom code logic before or after the execution of the target function, so as to customize and modify the behavior of the function.

As an early open-source framework, the Xposed framework's features and compatibility have been constantly upgraded. The EdXposed framework was derived, and based on it, it was compatible with Magisk, and developed into the LSPosed framework.

![315_21](/assets/res/2025/LSPosedframework.png)  
LSPosed framework

From the point of view of cheating principle, Xposed framework avoids the traditional way of modifying the system, such as recompiling, flashing ROM, etc. The modification method of Xposed framework is more flexible and convenient, and it can modify the numerical module of the game and the operation logic without affecting the signature and integrity of the application. And there are several detection difficulties as follows:

Xposed framework has been open source for a long time, with a large number of variants, cheating angle is more diversified, increasing the difficulty of detection and investigation.

Xposed framework is currently placed in the virtual machine, virtual framework, through the use of Magisk and other plug-ins, you can realize the game to hide cheats tool process to avoid detection.

**JikGuard has customized a special strategy to deal with the risks of injection cheats faced by games, and the solution has been accessed by a number of popular games and verified its excellent protection ability.**

**Active Recognition of Malicious Modules**

Unlike other security products on the market, which need to obtain samples and then fight against cheats, JikGuard's Active Malicious Module Recognition Mechanism actively recognizes suspicious modules, and together with the online combat features, it provides proactive defense, which significantly shortens the cycle of cheats detection.

**Anti-Injector Features**

Prohibit the use of Xposed, Frida and other cheats module injectors to prevent the injection of game memory modification and other malicious behaviors, once found immediately flashback.

**Anti-debugging features**

Prevent cheats authors from debugging the game, prevent static or dynamic analysis of the game, and immediately flashback once found.

**Security environment detection features**

Unlike other products on the market, JikGuard Hardening adopts a more underlying detection method, which can accurately identify all kinds of risky environments such as virtual frameworks, virtual machines, jailbreaks, ROOT, cloud phones, etc., and provide personalized flashing strategies.