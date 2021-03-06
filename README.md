# Pi-XO
Raspberry Pi Zero game console for use with PICO-8.   
The hardware and software is still under development!  

## In Action

[![Pi-XO Gaming](https://img.youtube.com/vi/vgGREFB0JgY/0.jpg)](https://www.youtube.com/watch?v=vgGREFB0JgY)

## Errata

Rev. 01. board  error:
  - *Error:* Speaker- an audio amp. output- connected to GND.  
    *Solution:* Do not wire speaker and audio amp. output (PAD5 and PAD6) to PCB, please connect speaker to audio amp. output via wire.  
    *Drawback:* Headphone connector not working 
  - *Error:*  ADC input direct connected to batterie A result in applying ~0.6 V to 3.3 V supply if battery is attached and device is off.  
    *Solution:* Do not assemble MCP3202 (IC1).  
    *Drawback:* No battery monitoring possible.

## Features

- **Multiple display options** - 160x128 or 320x240   
- **Audio (speaker / headphone)**
- **Classic dual NiMH AA-Batteries supply**
- **Battery monitoring**
- **GPIOs (LED bar)**
- **Vibration motors**
- **Low cost**

## OS installation

- Download latest Raspjamming-Image https://github.com/GrazerComputerClub/Raspjamming-Image and flash to SD card
- Unzip PICO-8-rasp.zip (https://www.lexaloffle.com/pico-8.php) to boot partition (Executable needed pico-8/pico8) from 
- Activate line 'include Pi-XO.txt' in config.txt file
- Activate correct Display Option 1-3 including resolution in Pi-XO.txt file 
   * Display 1: 320x240 Display mounted far right side (9 pin, BK-LED regulation)
   * Display 2: 160x128 Display mounted right side (8 pin, BK-LED regulation) 
   * Display 3: 160x128 Display mounted left side  (11 pin, BK-LED fixed on) 

## Functions

- Fn-Button and Up/Down-Button: Volume control
- Fn-Button and Left/Right-Button: Display brightness (Display 1 and 2)
- Fn-Button and P-Button: Shutdown


![PCB Top](https://github.com/GrazerComputerClub/Pi-XO/raw/master/Pi-XO.png)

![Circuit diagram](https://github.com/GrazerComputerClub/Pi-XO/raw/master/circuit_diagram.png)

![Pi-XO](https://github.com/GrazerComputerClub/Pi-XO/raw/master/Pi-XO.jpg)

# Assembling

## Components list
	
 1 x Female pin header socket 2x20  (JP1)
 1 x Switch 3-pin (S9, Device on/off)  
 1 x 2Pin + Jumper or Switch 2-pin (JP6, vibration motors on/off)    
 8 x Tactile switch 6x6mm (S1-S8)  
     https://www.reichelt.com/at/en/short-stroke-key-6x6-mm-height-5-0-mm-12-v-vertical-taster-9302-p44579.html  
 1 x Audio amplifier board PAM8302 (JP3, do not connect PAD5 and PAD6)  
     https://www.ebay.de/sch/i.html?_nkw=PAM8302  
 1 x DD0606SA_3V7 - DC/DC Step Up Converter to 3.7V (JP2)  
     https://www.google.com/search?q=DD0606SA_3V7  
 1 x Speaker 8 Ohm (connect to amplifier board PAM8302 Output via wire, SP1)  
     https://www.reichelt.com/at/en/metal-speaker-soldered-connection-lsm-36m-b-p145887.html  
     https://www.neuhold-elektronik.at/catshop/product_info.php?products_id=6645  
 1 x LED bar 8 segments (LB10, align right site)  
     https://www.ebay.at/sch/i.html?_from=R40&_trksid=m570.l1313&_nkw=8-Segment+Red+Color+Bar  
 1 x Resistor array 1K (RN1)  
     https://secure.reichelt.at/resistor-network-8-res-9-pin-1-0-k-x2126-sil-9-8-1-0k-p18012.html  
 2 x Vibration motor (JP4, JP5)  
     https://www.neuhold-elektronik.at/catshop/product_info.php?products_id=6971  
 2 x AA Batterie holder (needs DC/DC Step Up Converter) or dual AAA Batteries holder (no DC/DC Step Up Converter needed) (PAD1, PAD2, PAD3, PAD4)  
     https://secure.reichelt.at/battery-holder-1x-mignon-aa-halter-1xaap-p113168.html  
     https://secure.reichelt.at/holder-for-1-mignon-cell-aa-solder-tag-halter-1xum3-lf-p8434.html  
     https://secure.reichelt.at/battery-holder-2x-mignon-aa-halter-2xaaz-p113169.html  
 2 x BC547B transiior (T1, T2)  
     https://secure.reichelt.at/npn-to-92-transistor-45-v-0-1-a-0-5-w-bc-547b-p5006.html  
 1 x BC557B transistor (Q2)  
     https://secure.reichelt.at/transistor-pnp-to-92-45-v-0-1-a-0-5-w-bc-557b-p35845.html  
 2 x Resistor 2K2 Ohm (Transistor base vibration motor: R1, R2)  
 1 x Resistor 270 Ohm (Audio filter: R3)  
 1 x Resistor 150 Ohm (Audio filter: R4)  
 3 x Resistor 1K Ohm (protection UART: R5, R6; transistor background LED display: R7)   
 1 x Capacitor 33 nF (C1)  
 1 x Electrolytic capacitor 10 uF/6.3 V (C2)  
 1 x Capacitor 100 nF (C5)  
 1 x Electrolytic capacitor 330 uF/6.3 V (C6)  
 1 x MCP3202 (IC1, do not connect)  
     https://www.conrad.at/de/p/microchip-technology-mcp3202-ci-p-datenerfassungs-ic-analog-digital-wandler-adc-extern-pdip-8-651461.html  
 1 x Headphone connector (X2, do not connect)  
     https://secure.reichelt.at/jack-socket-3-5-mm-pcb-with-switch-contact-ebs-35-p7301.htm  
 2 x Diode 1N4001 (D2 or D4, D1 or D3)  
     https://secure.reichelt.at/rectifier-diode-do41-50-v-1-a-1n-4001-p1723.html  
 1 x 1,8" Display 160x128 ST7735 11-pin (JP7) or 8-pin (JP11) - https://www.ebay.de/sch/i.html?_nkw=1.8+128x160+ST7735  
     2,2" Display 320x240 ILI9341 9-pin (JB8) - https://www.ebay.de/sch/i.html?_nkw=2.2+ILI9341+240x320  
 
 
