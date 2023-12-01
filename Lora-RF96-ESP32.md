# Lora MINI KIT -> RF96 + ESP32-PICO-D4

### Lora RF96
*  https://www.thethingsnetwork.org/forum/t/lora-radio-node-v1-hope-rf96-setup-for-ttn/54944
*  https://microchip.ua/wireless/RF96_97_98.pdf

### MCU ESP32-PICO-D4
*  ESP32 contains two low-power Xtensa® 32-bit LX6 microprocessors. The internal memory includes:
```
  -  448 KB of ROM for booting and core functions.
  -  520 KB of on-chip SRAM for data and instructions.
  -  8 KB of SRAM in RTC, which is called RTC FAST Memory and can be used for data storage; it is accessed
  by the main CPU during RTC Boot from the Deep-sleep mode.
  -  8 KB of SRAM in RTC, which is called RTC SLOW Memory and can be accessed by the co-processor
  during the Deep-sleep mode.
  -  1 Kbit of eFuse: 256 bits are used for the system (MAC address and chip configuration) and the remaining
  768 bits are reserved for customer applications, including flash-encryption and chip-ID.
```
*  4-MB SPI flash
*  Bluetooth v4.2 +EDR
*  WiFi 802.11b/g/n
*  https://www.espressif.com/sites/default/files/documentation/esp32-pico-d4_datasheet_en.pdf

### Battery Charger TP4056
https://dlnmh9ip6v2uc.cloudfront.net/datasheets/Prototyping/TP4056.pdf

# Pin mapping
```
#define SCK     5    // GPIO5  -- SX1278's SCK
#define MISO    19   // GPIO19 -- SX1278's MISO
#define MOSI    27   // GPIO27 -- SX1278's MOSI
#define SS      18   // GPIO18 -- SX1278's CS
#define RST     14   // GPIO14 -- SX1278's RESET
#define DI0     26   // GPIO26 -- SX1278's IRQ(Interrupt Request)
```
???
```
#define LORA_POWER            21 // Low to off, High to on LoRa module
#define LORA_SS               25 // Mini - Must have pull up resistor
#define LORA_SCK              18 // Mini
#define LORA_MOSI             23 // Mini
#define LORA_MISO             19 // Mini
#define LORA_DIO0             26 // Mini
#define LORA_DIO1             35 // Mini
#define LORA_DIO2             34 // Mini
#define LORA_RESET            27 // Mini
```
