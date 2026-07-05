Jammer: 
this is a devide that can interrupt bluetooh, wifi and frequency. This device jams things by making a lot of sounds at a certain frequency which makes devides to unable to work or function

NOTE: THIS IS VERY ILLEGAL PLS DO NOT USE THIS IN PUBLIC

Video Demo: https://www.youtube.com/watch?v=kmlDtXSCuc8

You can flash your esp32 with this: https://esp32-bluejammerflasher.pages.dev/

DO THIS AT YOUR RISK

The components that are needed:
- ESP32 Dev Module (Recommended: ESP32-32U CP2102, any ESP32 should work as long as it has the needed pins, 38P required!) $5.50
- nRF24L01+PA+LNA (2x)                                                                                                     $6.50 (2x)
- 10-100uF Capacitor (2x) (any voltage above 5V)                                                                           $0.40 (2x)
- 0.96" OLED Display I2C                                                                                                   $3.00
- Slide Switch (2x)                                                                                                        $0.60
- LEDs: 3mm LED box                                                                                                        $3.50
- Resistor kit :
              - R1 = 1kOhm
              - R2, R3, R5, R7 = 47kOhm
              - R4, R6 = 100kOhm


| 1st nRF24L01 module Pin | HSPI Pin (ESP32) | 10uf capacitor |
|---------------|------------------|--------------------|
| VCC           | 3.3V             | (+) capacitor |
| GND           | GND              | (-) capacitor |
| CE            | GPIO 16          |
| CSN           | GPIO 15          |
| SCK           | GPIO 14          |
| MOSI          | GPIO 13          |
| MISO          | GPIO 12          |
| IRQ           |                  |

### VSPI 
| 2nd nRF24L01 module Pin | VSPI Pin (ESP32) | 10uf capacitor |
|---------------|------------------|--------------------|
| VCC           | 3.3V             | (+) capacitor |
| GND           | GND              | (-) capacitor |
| CE            | GPIO 22          |
| CSN           | GPIO 21          |
| SCK           | GPIO 18          |
| MOSI          | GPIO 23          |
| MISO          | GPIO 19          |
| IRQ           |                  |

### Status LED
| ESP32 | 4.7k Ohm Resistor | 3mm Status LED (blue)|
|-------|-------------------|----------------------|
|  GND  |                   |       (-) LED        |
|       |      Resistor     |       (+) LED        |
|GPIO27 |      Resistor     |                      |

### OLED Display I2C (additional - make sure to use the correct firmware!)
| 0.96" OLED Display I2C | ESP32 |
|------------------------|-------|
|          GND           |  GND  |
|          VCC           | 3.3V  |
|          SCL           |GPIO 5 |
|          SDA           |GPIO 4 |

### Battery modification (additional)
| 3.7V Li-Ion battery | JST-PH2 connector    | TP4056 Charging Module | Mini Slide Switch | ESP32 |
|---------------------|----------------------|------------------------|-------------------|-------|
| (+) Battery         | (+) JST-PH2          | Bat +                  |                   |       |
| (-) Battery         | (-) JST-PH2          | Bat -                  |                   |       |
|                     |                      | OUT +                  | Switch in         |       |
|                     |                      | OUT -                  |                   |  GND  |
|                     |                      |                        | Switch out        |  3V3  |

Here is the origional repo for anyone who wants a more detail guide: https://github.com/EmenstaNougat/ESP32-BlueJammer
