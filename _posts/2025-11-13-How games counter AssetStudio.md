---
layout: post
title: "How games counter AssetStudio"
date: 2025-11-13 16:30:00 +0800
categories: anti-cheat
tags: AssetStudio  AssetBundle  Unity
---

Game resource files contain vital components such as code, images, videos, and audio. Should these be decrypted, it would inflict severe detrimental effects upon game operations.<!-- more -->

Beyond disrupting operational schedules, resource extraction poses significant security risks. Images, videos, or scripts within game assets constitute intellectual property. Should these fall into the hands of hackers or competitors for plagiarism, the repercussions for the game would be incalculable.

![315_21](/assets/res/2025/11131.png)  
Halo 4 experienced an incident where its art assets were plagiarised

AssetStudio is a commonly used resource extraction tool. This article analyses how games should address hacking issues through case studies and proposes effective solutions.

AssetStudio is a cross-platform application requiring no complex configuration files, operating solely through its GUI interface. For instance, game resource files can be directly imported into AssetStudio for analysis, displaying key information about each resource within the list.

![315_21](/assets/res/2025/11132.png)  
Resource analysis upon import

Additionally, AssetStudio supports resource export functionality, enabling batch packaging and export of selected resources for subsequent processing.

![315_21](/assets/res/2025/11133.png)  
Supports batch export of game assets

AssetStudio's user-friendly design significantly lowers the barrier to hacking game assets. Consequently, effectively encrypting game resources to raise this barrier and safeguard assets has become essential for game developers.

Addressing game asset encryption, the JikGuard team developed a solution based on in-depth analysis of game engines, loading mechanisms, and file structures:

This solution balances robust encryption protection with minimal runtime overhead, offering the following advantages:
 
**◆ Rapid, imperceptible processing**

Encryption targets only critical core areas, exerting negligible impact on game loading speeds or operational workflows, achieving seamless integration.
 
**◆ High encryption strength**

Customised obfuscation of encryption/decryption algorithms prevents reverse engineering. Resource encryption effectiveness is demonstrated by the following comparison:
 
**◆ High Compatibility**

Implemented via Android SO packing or iOS static hooking for pure native solutions, it supports all 32-bit and 64-bit instruction sets.
 
**◆ Rapid Decryption**

Core file blocks remain compact and independent of overall resource file size. Testing on mainstream smartphones shows decrypting 300 resource files simultaneously adds less than 10ms to decryption time.

The encryption algorithm employs high-intensity custom obfuscation. This obfuscation is meticulously designed to enhance complexity while maintaining efficiency, resulting in minimal runtime overhead.
 
**◆ Cross-Platform Compatibility with Hot Updates**

JikGuard's resource encryption solution supports Android, iOS, and PC platforms, enabling online hot updates for resources.
 
**◆ User-Friendly Operation with Low Integration Cost**

Implementation is remarkably straightforward, requiring only a single command line to encrypt all game resources.

Additionally, the JikGuard hardening solution can incorporate multiple protective features based on configuration options, including anti-hack, anti-cheat, anti speed hack, anti-debugging, anti virtual machine, and anti cloud phone capabilities. This provides enhanced security for games, effectively addressing various security challenges. The solution has been integrated into multiple popular games and has demonstrated outstanding protective capabilities.