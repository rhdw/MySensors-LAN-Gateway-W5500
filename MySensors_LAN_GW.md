# MySensors LAN Gateway W5500
> from rhdw, Dez. 2018

***Update 2020: Since startup 2018 error free in use as gateway to Domoticz***

Used parts:
* Arduino NANO (clone with CH340 USB Chip)
* WizNET W5500 Module
* NRF24L01+ Transceiver Module
***

Connection list:
( the wire color is only required for the breadboard )

| HT7333-A | NANO | W5500 | NRF24L01+ | wire color |
| ----- | ----- | ----- | ----- | ----- |
| GND   | GND   | GND   | GND  | sw  |
| VIN   | +5V   |       |      |     |
| VOUT  |       | 3.3V  | V+   | rt  |
|       | 5     |       | CE   | gr  |
|       | 6     |       | CSN  | ge  |
|       | 10    | SCS   |      | or  |
|       | 11    | MOSI  |      | bl  |
|       | 12    | MISO  |      | vio |
|       | 13    | SCLK  |      | gn  |
|       | A0    |       | SCK  | gn  |
|       | A1    |       | MOSI | bl  |
|       | A2    |       | MISO | vio |

Compiled with Arduino 1.8.8  
Processor: ATmega328P (Old Bootloader)  
"Ethernet2.h" by Various Version 1.0.4  
"MySensors.h" by The MySensors Team Version 2.3.1
***

Schematics  
![en_gw](https://user-images.githubusercontent.com/21333959/50575213-224d7f00-0dfa-11e9-8db3-5578b2e287d1.png)
***

```ino
/*
 * The MySensors Arduino library handles the wireless radio link and protocol
 * between your home built sensors/actuators and HA controller of choice.
 * The sensors forms a self healing radio network with optional repeaters. Each
 * repeater and gateway builds a routing tables in EEPROM which keeps track of the
 * network topology allowing messages to be routed to nodes.
 *
 * Created by Henrik Ekblad <henrik.ekblad@mysensors.org>
 * Copyright (C) 2013-2018 Sensnology AB
 * Full contributor list: https://github.com/mysensors/MySensors/graphs/contributors
 *
 * Documentation: http://www.mysensors.org
 * Support Forum: http://forum.mysensors.org
 *
 * This program is free software; you can redistribute it and/or
 * modify it under the terms of the GNU General Public License
 * version 2 as published by the Free Software Foundation.
 *
 *******************************
 *
 * REVISION HISTORY
 * Version 1.0 - Henrik EKblad
 * Contribution by rhdw, 31.12.2018
 *
 *
 * DESCRIPTION
 * The EthernetGateway sends data received from sensors to the ethernet link.
 * The gateway also accepts input on ethernet interface, which is then sent out to the radio network.
 * I'm using this Ethernet Gateway for Domoticz
 * Parts: Arduino Nano + WizNET W5500 + NRF24L01+
*/

#define MY_DEBUG
#define MY_BAUD_RATE 9600

#define MY_RADIO_RF24
#define MY_RF24_PA_LEVEL RF24_PA_MAX
#define MY_RF24_DATARATE RF24_250KBPS
#define MY_RF24_CE_PIN 5
#define MY_RF24_CS_PIN 6

// IMPORTANT: Enable gateway ethernet module type ENC28J60
#define MY_GATEWAY_ENC28J60

#define MY_SOFTSPI
#define MY_SOFT_SPI_SCK_PIN 14
#define MY_SOFT_SPI_MISO_PIN 16
#define MY_SOFT_SPI_MOSI_PIN 15

#define MY_IP_ADDRESS 192,168,1,2

// IMPORTANT: Change the MAC Address to fit on your network
#define MY_MAC_ADDRESS 0xDE, 0xAD, 0xBE, 0xEF, 0xFE, 0xED

// If using static ip you can define Gateway and Subnet address as well
//#define MY_IP_GATEWAY_ADDRESS 192,168,1,1
//#define MY_IP_SUBNET_ADDRESS 255,255,255,0

// The port to keep open on node server mode
#define MY_PORT 5003

#include <Ethernet2.h>
#include <MySensors.h>

//---------------------------------------------------------
void setup() {}

//---------------------------------------------------------
void presentation() {}

//---------------------------------------------------------
void loop() {}
```
