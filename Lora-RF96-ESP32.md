# Lora MINI KIT -> RF96 + ESP32-PICO-D4

### Lora RF96
*  https://www.thethingsnetwork.org/forum/t/lora-radio-node-v1-hope-rf96-setup-for-ttn/54944
*  https://microchip.ua/wireless/RF96_97_98.pdf

![](https://github.com/PhamDuyAnh/ReadME_ESP-Lora-LoraWAN/blob/main/REF/HopeRF%20RFM95.jpg)

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
## Javascript Uplink decoder
https://thingsboard.cloud/integrationsCenter/converters

```
// Decode an uplink message from a buffer
// payload - array of bytes
// metadata - key/value object

/** Decoder **/

// decode payload to string
var payloadStr = decodeToString(payload);

// decode payload to JSON
var data = decodeToJson(payload);

var deviceName = 'rf210_11';
var deviceType = 'CKD_test_device';
var customerName = 'RFThings RF210';
var groupName = 'test devices';
var manufacturer = 'Titops';
// use assetName and assetType instead of deviceName and deviceType
// to automatically create assets instead of devices.
// var assetName = 'Asset A';
// var assetType = 'building';

// Result object with device/asset attributes/telemetry data
var result = {
    // Use deviceName and deviceType or assetName and assetType, but not both.
    deviceName: deviceName,
    deviceType: deviceType,
    // assetName: assetName,
    // assetType: assetType,
    // customerName: customerName,
    groupName: groupName,
    attributes: {
        model: 'RF210',
        serialNumber: 'RF210-11',
        integrationName: metadata['integrationName'],
        manufacturer: manufacturer
    },
    telemetry: {
        rawData: payloadStr,
        EUI: data.EUI,
        data: hex2a(data.data),
        freq: data.freq,
        dr: data.dr,
        port:data.port,
        ts: data.ts
    }
};

/** Helper functions **/
function hex2a(hexx) {
    var hex = hexx.toString();//force conversion
    var str = '';
    for (var i = 0; i < hex.length; i += 2)
        str += String.fromCharCode(parseInt(hex.substr(i, 2), 16));
    return str;
}

function decodeToString(payload) {
    return String.fromCharCode.apply(String, payload);
}

function decodeToJson(payload) {
    // covert payload to string.
    var str = decodeToString(payload);

    // parse string to JSON
    var data = JSON.parse(str);
    return data;
}

return result;
```
