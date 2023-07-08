---
layout: post
title: The Arm Architecture
date: 2023-07-07 17:39:00
description: Explore the Arm architecture, processors, and the Thumb-2 instruction set that provide low-cost, efficient, and versatile computing for a wide range of devices and applications.
---
# Arm

[Arm](https://www.arm.com/company) is a semiconductor and software design company headquartered in Cambridge, England. It is a fabless company, which means that it does not manufacture silicon. Instead, Arm develops the architectures and licenses them to other companies. One of the advantages of Arm processors is that they are designed for low costs, minimal power consumption, and lower heat generation. These features make Arm processors highly desirable for light, portable, battery-powered devices including smartphones, laptops, tablet computers, and embedded systems.

The Arm architecture is based on the Reduced Instruction Set Computing (RISC) approach, which emphasizes simplicity and efficiency in instruction execution. Arm offers a variety of processors, including Cortex-A, Cortex-R, Cortex-M, Neoverse, and SecurCore. The Cortex-A processors are designed for high performance and are commonly found in smartphones and tablets. Cortex-R processors are used for real-time applications, such as in automotive systems. Cortex-M processors are designed for microcontrollers and other low-power, cost-sensitive applications. Neoverse processors are designed for cloud-to-edge infrastructure, while SecurCore processors excel in providing anti-tampering features for smart card applications.

As I use [STM32F107VC](https://www.st.com/en/microcontrollers-microprocessors/stm32f107vc.html) MCUs in the lectures, my focus will primarily be on [Arm Cortex-M3](https://developer.arm.com/Processors/Cortex-M3) MCUs.  For a detailed comparison of the different Arm Cortex families, you can refer to [Differences Among Arm® Cortex® Families](https://microchipdeveloper.com/32arm:differences-among-arm-cortex-families). 

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/82fff374-7d0a-4831-92fa-2a0e5ce68b01/Untitled.png)

Armv7 refers to the seventh version of the Arm architecture, specifically a 32-bit instruction set architecture (ISA). ARMv7 gained widespread adoption and compatibility across various devices. ARMv7 introduced significant improvements and features such as the Thumb-2 instruction set, TrustZone security extension, virtualization support, and the NEON (Advanced SIMD) instruction set extension for multimedia and signal processing tasks.

The Thumb-2 instruction set is a notable extension within the Arm architecture. It combines the benefits of both the traditional Arm (32-bit) and compact Thumb (16-bit) instruction sets. It offers improved code density by allowing more instructions to fit in a given memory space. Thumb-2 instructions can switch between 16-bit and 32-bit modes seamlessly, offering flexibility in instruction size based on the complexity of the operation. This extension retains compatibility with existing Thumb code and provides access to the full functionality and performance of the ARM instruction set when required.

Overall, Arm's architecture, combined with its diverse processor offerings and extensive features, has made it a popular choice in various industries and applications. The focus on low power consumption, efficiency, and compatibility has enabled Arm processors to thrive in the market, powering a wide range of devices and systems.

Additional Resources:

ARM Architecture Reference Manual

[Cortex-M resources](https://community.arm.com/arm-community-blogs/b/architectures-and-processors-blog/posts/cortex-m-resources#intro)

Coursera course to follow: [Arm Cortex-M Processors Overview](https://www.coursera.org/learn/arm-cortex-m-processors-overview-course1)