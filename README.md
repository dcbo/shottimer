# espresso shot timer 

## features
 - 7-Seg style graphic output on I2C-OLED display
 - temperature display 
 - control of baristlight during shot (digital or PWM)
 
by  Dario Carluccio (user dondario of http://www.kaffee-netz.de) <shottimer.at.carluccio.de>

based on idea and hardware from 
 - David Kißling (user mactree of http://www.kaffee-netz.de )
 

## todo
- [ ] change switch input to valve and measure preinfusion seperate
- [ ] design new display output if inactive
- [ ] store values in eeprom
  - no. of shots longer than MIN_SHOT_TIME - UNSIGNED LONG
  - seconds of pump operation - UNSIGNED LONG
- [x] add barista light control 

## changelog
- v2.1 rev 002 - baristalight added with many configuration options
  (pin configuration, polatity high/low active, pwm speed on/off, timeout)                
- v2.1 rev 001 - Complete code rewritten, baristalight still missing

## connections
  - OLED display
    - GND   connected to GND
    - SDA   connected to SDA
    - SCL   connected to SCL
    - VCC   connected to 5V 
  - switch input
    - D5    LOW ACTIVE
  - pump input
    - D6    LOW ACTIVE
  - DS1820 temperature sensor (optional)
    - GND   connected to GND
    - Data  connected to Port 2 and to a 4k7 resistor
    - VCC   connected to 5V and to the other pin of the 4k7 resistor 
  - Barista Light via relais - ON-OFF only (optional)
    - 13    polarity configurable 
  - Barista Light via MOSFET - dimmable (optional)
    - 10    polarity configurable 

## libraries needed
  - [Bounce2, Version 2.21](https://github.com/thomasfredericks/Bounce2/)
  - [DallasTemperature, Version 3.7.7](https://github.com/milesburton/Arduino-Temperature-Control-Library)
  - [MicroLCD](https://github.com/stanleyhuangyc/MultiLCD/tree/master/MicroLCD)
  - [OneWire](https://github.com/PaulStoffregen/OneWire)
  - Wire - part of Arduino installation
