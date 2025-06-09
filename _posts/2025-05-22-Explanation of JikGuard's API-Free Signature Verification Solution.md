---
layout: post
title: "Explanation of JikGuard's API-Free Signature Verification Solution"
date: 2025-05-22 16:30:00 +0800
categories: anti-hack
tags: Solution  JikGuard  Signature Verification
---

As we all know, when Android system installs games, in order to ensure that the game package has not been tampered with, it will verify the authenticity and integrity of the game files, at this time, it is necessary to verify the signature of the game package, and the installation will be successful only after the verification is correct.<!-- more -->  

Signature is equivalent to writing a fingerprint in the game package, after the fingerprint is written, any modification of the package will lead to the invalidation of the fingerprint, so that hacked games will be excluded from the signature verification process of the installation.

In order to ensure security and uniqueness, the signature consists of two parts: the summary and the private key signature. The same hash algorithm will be used to calculate the summary and the private key will be used to decrypt the signature information, and the decrypted data will be compared with the summary, and if the two are the same, it means that the game hasn't been tampered with.

![315_21](/assets/res/2025/signature.jpg)  
▲ The process of game signature and signature verification  

When hackers make hacked games, they usually use reverse modification tools, such as MT Manager for Android, which comes with signature checksum removal.

After removing the signature checksum, you can modify the game values, game logic and implant function menus through various analyzing and debugging means, so as to make hacked games.

So how do these hacked games with altered contents pass the signature verification?

The answer is: by forging the genuine signature through the hook API function, so that the normal signature verification is invalidated.

The specific principles and operations are as follows:

API (Application Program Interface) is a definition of the application and the operating system or other software interaction between the specification, which contains a large number of system functions.

Under normal circumstances, the operation and interaction of a game needs to be executed by calling the API, and subsequently the results are returned to the game client and then presented to the user.

![315_21](/assets/res/2025/hookAPI.png)  
▲ Diagram of hook API flow  

After the hook API, it is equivalent to intercepting the normal interaction, and customized programs can be interspersed in it, so as to intercept and change the execution process of the program without modifying the original code.

Embodied in the process of forging signatures is: the hacker will be with the genuine signature of the package with the hacked version of the package integrated together, in the game start for signature verification, access to the genuine signature, while the game runs the hacked version of the package content.

This is often reflected in the size of the package, the hacked version of the package size is nearly twice the size of the original. 

![315_21](/assets/res/2025/packagesize.png)  
▲ Comparison of the package size of the original and hacked version of a game  

For a game, the outflow of hacked version will cause the fairness of the game to be damaged, resulting in the loss of a large number of genuine players, and there is also the possibility of the code and art resources in the game being stolen and dramatized.

**JikGuard has developed a customized strategy to deal with the risk of game hack. The solution has already been applied to a number of popular games and has been proven to have excellent protection capabilities.**  

**Anti-hack Features**

JikGuard's industry-exclusive “No API Signature Verification Technology” deeply encrypts the game's engine and code, and performs multiple checks on game package signatures and file integrity, greatly reducing the likelihood of being bypassed, and preventing the game from being implanted with malicious modules and culling advertisements.

**Active Recognition of Malicious Module Mechanism**

Unlike other security products on the market, which require the acquisition of samples to combat cheats, JikGuard's exclusive “active identification of malicious module mechanism” can actively identify suspicious modules within the game, and with the online hackdown function to achieve proactive defense, significantly shortening the cheats detection cycle.

**Anti-debugging Features**

Prevent cheats authors from debugging the game, prevent static or dynamic analysis of the game, and immediately flashback once found.

**Security Environment Detection Features**

Unlike other products on the market, JikGuard adopts a more fundamental detection method, which can accurately identify various risky environments such as virtual frameworks, virtual machines, jailbreaks, ROOT, cloud phones, etc., and provide personalized flashing strategies.
