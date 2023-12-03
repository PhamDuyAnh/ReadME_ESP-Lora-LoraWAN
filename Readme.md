## ESP Lora Gateway
*  MakePython - https://github.com/PhamDuyAnh/ESP-Lora-Gateway-2CH-by-MakePython
  https://wiki.makerfabs.com/MaESP_ESP32_Lora_Gateway.html

*  IoTThinks - https://github.com/PhamDuyAnh/ESP-Lora-Gateway-by-IoTThinks
*  IoTThinks - https://github.com/PhamDuyAnh/ESP-Lora-Gateway_v2.1-by-IoTThinks

## ESP Lora Node
*  Makerfabs - https://github.com/Makerfabs/Project_IoT-Irrigation-System

## ESP LoraWAN Gateway
*  IoTThinks - https://github.com/PhamDuyAnh/ESP-LoraWAN-Gateway-by-IoTThinks
*  things4u - https://github.com/PhamDuyAnh/ESP-LoraWAN-Gateway-1CH-by-things4u
*  things4u - https://github.com/PhamDuyAnh/ESP-LoraWAN-Gateway-1CHv5.0-by-things4u
*  pulsartronic - https://github.com/PhamDuyAnh/ESP-LoraWAN-Gateway-1CH-by-pulsartronic
*  Zupayruna1 - https://github.com/PhamDuyAnh/ESP-LoraWAN-Gateway-1CH-up2-2CH
  
## ESP LoraWAN Node
*  HelTecAutomation - https://github.com/PhamDuyAnh/ESP-LoRaWAN-Node-by-HelTecAutomation
*  sparkfun - https://github.com/PhamDuyAnh/ESP-LoraWAN-Node-1CH-by-sparkfun

## Lora Mesh
*  https://github.com/nootropicdesign/lora-mesh
*  https://github.com/LoRaMesher
*  
## Other
*  https://github.com/CongducPham
*  https://github.com/phatvu1294/he-thong-nha-kinh-iot-ung-dung-lora
*  https://emanuelepagliari.it/2020/10/12/how-to-build-lorawan-gateway-heltec-esp32-lora/
*  https://emanuelepagliari.it/2020/10/13/what-is-lorawan-internet-of-things-protocol/
*  https://www.instructables.com/How-to-Program-ESP32-As-LoRa-Gateway-With-Arduino/
*  https://electronicsinnovation.com/diy-lorawan-gateway-with-rfm95-wemos-d1-mini-pro-how-to-make-single-channel-lora-gateway/
*  https://github.com/PaulStoffregen/RadioHead/blob/master/RHDatagram.cpp

## VN frequency AS_923_2 - AS923 Group 2 --> AS923-925 ("AS2") ?
*  https://lora-alliance.org/wp-content/uploads/2020/11/rp_2-1.0.1.pdf
*  https://github.com/TheThingsNetwork/lorawan-frequency-plans/blob/master/AS_923_2.yml
*  https://github.com/TheThingsArchive/ttn/issues/491
*  https://www.thethingsnetwork.org/docs/lorawan/frequency-plans/#as923-925-as2

```
// CKD add AS_923_2 frequency 921.4-922.8 MHz
#elif defined(AS_923_2)
vector freqs[] = {
  { 921400000, 125, 7, 12, 921400000, 125, 7, 12 },  // Channel 0, 921.4 - SF7BW125 to SF12BW125
  { 921600000, 125, 7, 12, 921600000, 125, 7, 12 },  // Channel 1, 921.6 - SF7BW125 to SF12BW125
  { 921800000, 125, 7, 12, 921800000, 125, 7, 12 },  // Channel 2, 921.8 - SF7BW125 to SF12BW125
  { 922000000, 125, 7, 12, 922000000, 125, 7, 12 },  // Channel 3, 922.0 - SF7BW125 to SF12BW125
  { 922200000, 125, 7, 12, 922200000, 125, 7, 12 },  // Channel 4, 922.2 - SF7BW125 to SF12BW125
  { 922400000, 125, 7, 12, 922400000, 125, 7, 12 },  // Channel 5, 922.4 - SF7BW125 to SF12BW125
  { 922600000, 125, 7, 12, 922600000, 125, 7, 12 },  // Channel 6, 922.6 - SF7BW125 to SF12BW125
  { 922800000, 125, 7, 12, 922800000, 125, 7, 12 }   // Channel 7, 922.8 - SF7BW125 to SF12BW125
  //{ 924500000, 250, 7, 7, 924500000, 250, 7, 7 },    // Channel 8, 924.5 - SF7BW250
  //{ 924800000, 125, 7, 12, 924800000, 125, 7, 12 },  // Channel 9, 924.8 - FSK
  //{ 0, 0, 0, 0, 923200000, 125, 10, 10 }             // Channel 10, 923.2 - SF10BW125 (RX2)
};
```

## TTN MAC & PHY version --> 1.0.2???
AS_923_2 TTN support LoRaWAN version --> LoRaWAN Specification 1.0.4

https://huongdan.cytrontech.vn/sending-data-from-node-to-the-things-stack.html
