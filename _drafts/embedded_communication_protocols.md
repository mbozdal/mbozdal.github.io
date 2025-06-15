---
layout: post
title:  Embedded Communication Protocols
date:   2023-05-20 16:40:16
description: communication protocols, synchronious, asynchronious
tags: 
categories: embedded systems, communication
permalink: /mcu/:title
---
There are various communication protocols exist for embedded systems to enable data exchange between different components or devices.
These protocols can be classied as sychronious and asynchronous acording to shared clock. 



Here are some of the most common communication protocols used in embedded systems:

1. Universal Asynchronous Receiver-Transmitter (UART): 
A simple serial communication protocol that transmits
 data in asynchronous manner.  It is a widely used serial
 communication protocol for transmitting data asynchronously,
 without the need for a separate clock signal.

2. Serial Peripheral Interface (SPI): A synchronous serial
 communication protocol commonly used for short-distance
 communication between microcontrollers and peripheral devices.
 It allows for high-speed data transfer and supports full-duplex
 communication.

3. Inter-Integrated Circuit (I2C): A multi-master, multi-slave
 synchronous serial communication protocol used for low-speed
 communication between integrated circuits on a circuit board.
 It allows multiple devices to share the same bus using unique
 device addresses.

4. Controller Area Network (CAN): A robust, asynchronous serial
 communication protocol designed for real-time applications in
 automotive and industrial environments. It supports multi-master
 communication and provides error detection and fault tolerance
 features.

5. Ethernet: A widely used networking protocol that enables
 communication over local area networks (LANs). Embedded systems
 can utilize Ethernet to connect to other devices, access networks,
 and exchange data over TCP/IP or UDP/IP protocols.

6. Universal Serial Bus (USB): A popular protocol for connecting
 peripherals to embedded systems. USB supports various data
 transfer rates and offers features like plug-and-play,
 power delivery, and multiple device connections.

7. Bluetooth: A wireless communication protocol commonly used for
 short-range communication between embedded systems and mobile
 devices or other Bluetooth-enabled devices. It supports low-power
 and low-latency data transmission.

8. Wi-Fi: A wireless communication protocol that allows embedded
 systems to connect to wireless networks and access the internet.
 Wi-Fi provides high-speed data transfer and supports TCP/IP
 networking.

9. Zigbee: A low-power, low-data-rate wireless communication
 protocol commonly used in home automation, industrial control,
 and sensor networks. It offers mesh networking capabilities and
 is designed for applications requiring low power consumption.

10. Modbus is a widely used communication protocol in the field
 of industrial automation and is commonly employed in embedded
 systems. It is a master/slave protocol that allows for
 communication between a supervisory computer system (master)
 and multiple devices or controllers (slaves) in a networked
 environment. 
 
11. LoRa
12. RS485

12. MQTT (Message Queueing Telemetry Transport): A lightweight
 messaging protocol designed for machine-to-machine communication
 and IoT applications. It uses a publish-subscribe model and
 is well-suited for constrained devices and low-bandwidth networks.

 wired and wireless
 speed, distance, master-slave, common usage, dublex, 
power consumption for rf



| Protocol | A/Sync | Shared Clock | Speed | Dublex | Power | Common Usage |
|-------|-----------|--------------|-------|--------|-------|--------------|
| UART  | Async     | No           |XXX    | S,H,F  |xxxxx  |              |
| SPI   | Async     | Yes          |XXX    | XXXX   |xxxxx  |              |
| I2C   | XXX       | XXX          |XXX    | XXXX   |xxxxx  |              |
| CAN   | XXX       | XXX          |XXX    | XXXX   |xxxxx  |              |
| XXX   | XXX       | XXX          |XXX    | XXXX   |xxxxx  |              |
| XXX   | XXX       | XXX          |XXX    | XXXX   |xxxxx  |              |
| XXX   | XXX       | XXX          |XXX    | XXXX   |xxxxx  |              |
| XXX   | XXX       | XXX          |XXX    | XXXX   |xxxxx  |              |
| XXX   | XXX       | XXX          |XXX    | XXXX   |xxxxx  |              |
| XXX   | XXX       | XXX          |XXX    | XXXX   |xxxxx  |              |
| XXX   | XXX       | XXX          |XXX    | XXXX   |xxxxx  |              |
| XXX   | XXX       | XXX          |XXX    | XXXX   |xxxxx  |              |
| XXX   | XXX       | XXX          |XXX    | XXXX   |xxxxx  |              |
| XXX   | XXX       | XXX          |XXX    | XXXX   |xxxxx  |              |
