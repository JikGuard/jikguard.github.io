---
layout: post
title: "How to Encrypt Unity AssetBundle Resources"
date: 2025-11-27 16:30:00 +0800
categories: anti-cheat
tags: Unity  AssetBundle  Resources
---

AssetBundles are a type of compressed resource storage package provided by Unity. They contain game assets such as images, models, textures, audio/video files, and code files.<!-- more -->

Due to their advantages—including flexible storage, support for hotfixes, compact package sizes, and ease of management—AssetBundles have become the mainstream method for compressing game resources in the industry.

AssetBundle files containing images, models, videos, and other resources are critical assets for games. If cracked by hackers or competitors to extract their contents, this could lead to severe issues such as plagiarism by rival products and damage to intellectual property rights.

![315_21](/assets/res/2025/112701.png)  
Halo 4 experienced an incident of art asset plagiarism

Furthermore, cracking AssetBundle resources can severely impact game operations. For instance, in content-driven games, AssetBundles may store unreleased event assets. If these are prematurely unlocked and spoiled, it diminishes player surprise and event immersion, negatively affecting the game's operational rhythm.

In competitive shooter games, hacking or tampering with game assets can unexpectedly create cheat-like effects. This severely undermines gameplay fairness, leading to player attrition and financial losses for developers.

![315_21](/assets/res/2025/112702.gif)  
Certain game assets have been cracked, resulting in the emergence of Extra Sensory Perception Cheats.

Next, we will focus on analyzing how to encrypt AssetBundle resources.

Numerous methods for encrypting AssetBundle resources exist on the market, and related encryption articles can be found online, such as encrypting entire resources. While this approach meets the need for resource encryption, its drawbacks are significant. AssetBundle resources constitute a large portion of a game's overall size. Encrypting them entirely would severely impact game performance.

How to encrypt game assets while ensuring minimal decryption overhead and reducing performance burden has become a major challenge for many games.

To address this, the Jikguard R&D team invested significant time conducting black-box analysis of the Unity engine. By deciphering the loading mechanism and file structure of AssetBundles, they meticulously designed an encryption solution:

First, by parsing the structure of AssetBundle files, the core file blocks within resource files are identified and encrypted. During game runtime, monitoring points are embedded at the Unity engine's AssetBundle loading triggers, where the core file blocks are decrypted at these monitoring points.

This construction approach not only fulfills encryption protection requirements but also features low operational overhead, addressing the industry pain point of game resource encryption. It offers the following advantages:

**▶ High Speed, Imperceptible**

The encryption scheme targets only core critical areas, having virtually no impact on game loading speed or runtime processes, achieving imperceptibility.

**▶ High Encryption Strength**

The encryption and decryption algorithms have been custom-obfuscated to prevent the hacker from analyzing the algorithms.

**▶ High Compatibility**

Pure native solutions imported via Android SO packing or iOS static hooking support all 32-bit and 64-bit instruction sets.

**▶ Extremely Fast Decryption Speed**

Core file blocks are compact and remain consistent regardless of the entire resource file size. On mainstream smartphones, decrypting 300 resource files simultaneously adds less than 10ms to the decryption time.

The encryption algorithm employs highly customized obfuscation. This obfuscation is meticulously designed to increase complexity while maintaining efficiency, resulting in minimal runtime overhead.

**▶ Supports Android / iOS / PC platforms**

**▶ Easy to operate with low integration costs**

Extremely simple to use—just run a single command line to encrypt all game resources.

This command line encrypts game resources while also applying mono DLL encryption or il2cpp encryption to in-game scripts.

Additionally, based on configuration options, multiple features can be added to further fortify game protection, including anti-hack, anti-cheat, anti-speed modification, anti-debugging, anti-virtual machine, and anti-cloud phone capabilities. This effectively addresses various security challenges faced by games. Currently, this solution has been integrated into multiple popular games and has demonstrated outstanding protection capabilities.