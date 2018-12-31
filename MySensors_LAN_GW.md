    MISO # MySensors LAN Gateway W5500
> from rhdw, Dez. 2018

Used parts:
* Arduino NANO
* WizNET W5500 Module
* NRF24L01+ Transceiver Module
***

Connection list:
( the wire color is only required for the breadboard )

| HT7333-A | Arduino NANO | WizNET W5500 | NRF24L01+ | wire color |
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
***VIN

Compiled with Arduino 1.8.8  
Processor: ATmega328P (Old Bootloader)  
"Ethernet2.h" by Various Version 1.0.4  
"MySensors.h" by The MySensors Team Version 2.3.1
***

My Schematics  
![png](https://user-images.githubusercontent.com/21333959/50541348-0c468100-0ba4-11e9-853b-54b6de234a19.png)
***

```ino
/*----------------------------------------------
  MySensors_EN_GW_W5500.ino
  ----------------------------------------------
  DESCRIPTION
  My Ethernet Gateway for Domoticz
  Arduino Nano + WizNET W5500 + NRF24L01+
  ----------------------------------------------
  REVISION HISTORY
  ----------------------------------------------
  v1.1 - 31.12.2018
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
