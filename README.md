# esphome_airconintl
Support for Acond Splits via ESPHome

Testing with unit Acond ASU...

Project goal:
- [x] Control unit. Looks like controling actualy works out of the box with original code
- [ ] Reading values from unit. (I used max485 so it will need flow control...)
  - [ ] ... 


This integration is still a little rough around the edges, but it works fully for controlling the AC and displays status info with only the occasional error. Most of those errors are related to less important things like outdoor unit temps, compressor speed, etc. It seems like some of the display errors may come from the unit itself reporting bad info.

I referenced the work of several others to make this happen:
* https://github.com/pslawinski/esphome_airconintl - original repo, many thanks to author
* https://community.home-assistant.io/t/working-on-integration-for-hisense-aeh-w4a1-module/146243
* https://github.com/deiger/AirCon/
* https://github.com/simoneluconi/hisense-aeh-w4a1

This thread in particular was quite useful:
https://github.com/deiger/AirCon/issues/1

I'm using an Wemos D1 mini board (ESP8266) with a serial to 485 adapter board (MAX485 based :( no flow control). I'll assume that if you're even thinking of replicating my results you're well capable of finding the necessary components on Amazon. Given how cheap PCBs are these days I may just spin a ESP-12F carrier board that can plug directly into the AC connector.

The pinout of the connector is:
1) (Black wire) GND
2) B-
3) A+
4) (Red wire) +5V
