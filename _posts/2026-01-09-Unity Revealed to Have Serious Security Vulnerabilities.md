---
layout: post
title: "Unity Revealed to Have Serious Security Vulnerabilities"
date: 2026-01-09 16:30:00 +0800
categories: anti-cheat
tags: Unity  Security Vulnerabilities
---

Recently, security researcher RyotaK discovered a critical security vulnerability (CVE ID: CVE-2025-59489) in the Unity engine. This vulnerability stems from a security flaw in Unity's execution environment when handling Intents on the Android platform.<!-- more --> 

Vulnerability Exploitation Mechanism
Unity sets UnityPlayerActivity to exported by default to support debugging applications on Android devices. This means other applications can send Intents directly to it.

Attackers can manipulate command-line arguments passed to Unity applications via malicious Intents, particularly by exploiting the `-xrsdk-pre-init-library` parameter to specify arbitrary shared library paths.

Analysis of the Unity runtime binary using Ghidra reveals that values from relevant command-line arguments are directly passed to the `dlopen` function. This causes the specified path to be loaded as a native library, enabling arbitrary code execution.

![315_21](/assets/res/2026/01091.jpg) 
Official Vulnerability Description: https://unity.com/cn/security/sept-2025-01

Scope of Vulnerability Impact
The scope of this security vulnerability is extremely broad. Affected versions include Unity 2017.1 and all subsequent releases, extending even to discontinued versions such as 2018.4. 2018.3. 2018.2. 2018.1. and 2017.4. The official recommendation is for users of 2019.1 and later versions to implement the patch immediately.

From a platform perspective, Android applications face the highest risks, which can lead to code execution and privilege escalation. Windows, Linux desktop, Linux embedded, and macOS platforms primarily face privilege escalation risks.

Vulnerability Exploitation Scenarios
Attackers can exploit this vulnerability to launch attacks in both local and remote scenarios.

Local Attack:

A malicious application installed on the same device can exploit this vulnerability by following these steps: First, extract the native libraries where the android:extractNativeLibs attribute in AndroidManifest.xml is set to true. Then, launch the Unity application using the -xrsdk-pre-init-library parameter, whose value points to the path of the malicious library. The Unity application will then load and execute the malicious code, granting it all permissions of the application.

Remote Attack:

The conditions are relatively stringent, requiring two criteria to be met:

The application exports a UnityPlayerActivity or UnityPlayerGameActivity that includes the android.intent.category.BROWSABLE category;

The application writes files containing attacker-controlled content to its private storage (e.g., via a caching mechanism).

Negative Impact of Vulnerabilities
Upon the announcement, multiple games including Hearthstone, Pillars of Eternity II, Among Us, and Marvel Ultimate Reversal were urgently taken down or updated.

This vulnerability poses serious security risks. Failure to update and patch promptly may result in the game violating Google Play's “Device and Network Abuse” policy, leading to penalties that prevent the release of application updates.

Vulnerability Fix Recommendations
In response to this high-risk vulnerability, Unity has taken action and provided two primary remediation solutions.

For developers using Unity 2019.1 and later versions, Unity has released security patches. Developers should immediately download the latest version of the Unity Editor, recompile their applications, and release updates.

![315_21](/assets/res/2026/01092.jpg) 

For projects unable to upgrade immediately, Unity provides dedicated binary patch tools that allow developers to fix vulnerabilities without a full recompilation.

Developers still using versions 2017.1 through 2018.4 should note that official patches may not be available for these discontinued versions. It is recommended that these developers upgrade to a supported version as soon as possible.

Complete Official Announcement: https://discussions.unity.com/t/unity-platform-protection-take-immediate-action-to-protect-your-games-and-apps/1688031