# Custom-Android-OS-for-Enhanced-Security-and-Performance

Welcome to the repository for the Custom Android ROM project aimed at enhancing the security and performance of Android-based devices. This project focuses on customizing Android ROMs, primarily targeting single board computers (SBCs) like the Tinker Board SBC, but the techniques and findings are widely applicable across various Android devices.

Demonstration -> https://drive.google.com/drive/folders/1-ZNw_5wmsorDUuDSf8XjflzoCVJzSgBB?usp=drive_link

## Table of Contents
- [Introduction](#introduction)
- [Vulnerabilities in Android Systems](#vulnerabilities-in-android-systems)
- [Potential Solutions to Android Vulnerabilities](#potential-solutions-to-android-vulnerabilities)
- [Project Implementation](#project-implementation)
- [Customization & Removing Bloatware](#customization--removing-bloatware)
- [Background Launching of Apps](#background-launching-of-apps)
- [Foreground Launching of Apps](#foreground-launching-of-apps)
- [Background vs Foreground Comparison](#background-vs-foreground-comparison)
- [Experimental Evaluation](#experimental-evaluation)
- [Applicability to Wider Range of Devices](#applicability-to-wider-range-of-devices)
- [Future Work](#future-work)
- [Conclusions](#conclusions)

## Introduction

In the contemporary landscape of technology, operating systems play an integral role in managing diverse tasks. Android, with its vast user base, has not only revolutionized the smartphone industry but has also gained prominence in powering single board computers (SBCs), Internet of Things (IoT) devices, and even server systems. The open-source nature of Android and its capacity for customization cater to the requirements of myriad devices, thus offering remarkable opportunities for developers and researchers. However, such opportunities often come coupled with significant challenges, primarily in the fields of security and performance.

This project emerges from the intersection of these opportunities and challenges. Our focus is on enhancing the security and performance of Android-based devices, specifically single board computers, by customizing Android ROMs. This approach involves the eradication of unwanted applications or bloatware, which often consume critical system resources and pose potential security threats.

## Vulnerabilities in Android Systems

- **Potential Security Threats:** Android's widespread use and open-source nature make it a common target for cyberattacks. These threats can range from sophisticated malware to data leakage due to insecure app permissions.

- **Privacy Concerns:** Some pre-installed applications (bloatware) can have excessive permissions, leading to potential privacy concerns.

- **Real-life example - 'xHelper' Malware:** First discovered in 2019, the 'xHelper' malware, pre-installed on some Android devices, underscored the significant security risks associated with bloatware.

## Potential Solutions to Android Vulnerabilities

- **Building an OS from Scratch:** While offering maximum control, this option requires substantial resources and expertise in OS development.

- **Minimalist Operating Systems and Microkernel Architecture:** These OSs aim to minimize the attack surface but may lack certain Android functionalities.

- **Customizing Existing Android OS (Android ROMs):** This method involves removing unnecessary applications and integrating desired applications into the Android Open Source Project (AOSP).

## Project Implementation

- **Custom ROM for Tinker Board SBC:** This project involves customizing an Android ROM for ARM-based Tinker Board S R2.0 SBC, primarily targeting performance and security enhancements.

- **Customization & Bloatware Removal:** We identified and removed unnecessary apps and bloatware during the ROM build process.

- **Background and Foreground Launching of Apps:** We implemented two methods for launching custom applications - as a background process during system boot or as a foreground process post-system boot.

## Customization & Removing Bloatware

- **UI Customization:** We located system files responsible for wallpapers and icons, modifying them to suit our preferences.

- **Bloatware Identification:** We identified non-essential or rarely used system packages and libraries, classifying them as bloatware.

- **Bloatware Removal:** We modified Android Make files to exclude identified bloatware, effectively removing them during the build process.

## Background Launching of Apps

- **Integrating custom app into boot sequence:** In this module, we modified core OS files (SystemServer.java & CustomBoot.java) to incorporate the custom app into the system boot sequence, enabling it to run as a background process during boot.

## Foreground Launching of Apps

- **Modifying app manifest and adding receiver code:** The foreground method involved altering the custom app's manifest and adding specific receiver code. This allowed the app to listen for the BOOT_COMPLETED broadcast intent and start up as a foreground process after boot.

## Background vs Foreground Comparison

- **Load times:** The background method offers faster load times, while the foreground method may face performance penalties if multiple apps are started.

- **Security concerns:** Background method might pose security risks due to root privileges, while foreground method provides user-level privilege, offering more security after boot.

- **Virus/Malware Threat:** The background method could enable virus/malware running at boot time, while the foreground method does not have this issue.

## Experimental Evaluation

**Comparison : Stock Android 12 vs Customized Android**

| Metric                                  | Stock Android 12 | Customized Android |
|-----------------------------------------|------------------|--------------------|
| **Uptime**                              | 123 hours        | 156 hours          |
| **MTBF (Mean Time Between Failures)**   | 150 hours        | 190 hours          |
| **MTTR (Mean Time To Repair)**          | 2 hours          | 1.5 hours          |
| **Vulnerabilities**                     | 27               | 20                 |
| **Errors/Crashes**                      | 53               | 28                 |

## Applicability to Wider Range of Devices

- **Android Platform Universality:** The Android platform's versatility and widespread usage across devices provide a broad application base for our research.

- **Customization Flexibility:** The customization principles applied in our project can be adapted to optimize Android ROMs on a wide array of devices, including smartphones, IoT devices, and other SBCs.

## Future Work

- **Development of Android Application:** Future work includes developing an Android application designed to launch as a background process and manage permissions for all apps on the device.

- **Testing and Integration:** The remaining work involves refining the code, testing its functionality, and ensuring seamless integration with the customized Android ROM.

## Conclusions

- **Systematic Approach:** We provided a systematic methodology for analyzing and customizing Android ROMs for heightened security and performance.

- **Performance Optimization:** We streamlined the Android ROM by eliminating unnecessary applications, enhancing overall system performance and reliability.

- **Visual Customization:** We personalized UI elements for a visually appealing user experience, enhancing the user interface as per the user's preferences.

- **Startup Applications:** We showcased detailed guidelines for modifying source code to add custom applications and automatically launch specific applications at startup.
