---
aliases: 
created: 2022-04-28, 8:58:06 am (Thursday, April 28th)
updated: 2022-05-03, 9:34:13 pm (Tuesday, May 3rd)
---
All versions after Teensy 2.0 (LC, 3.x and beyond) support [teensyduino](https://www.pjrc.com/teensy/td_download.html), a sort of plugin for [Arduino's IDE](https://www.arduino.cc/en/software) that allows you to load programs onto an Arduino.

Follow the instructions on the teensyduino page (the link in the previous paragraph).

I think the only bits I got myself into some trouble were:
- Step 2: Once you download the Arduino package *don't run the install script in the package*. Least not until *after* you ran the teensyduino installer
- Step 5: Doesn't exist and probably is self-explanatory but sometimes I need things spelled out for me: *Now* run the Arduino install script

When running Arduino IDE, don't forget to:
- Select Teensy as the board
    - `Tools > Board > TeensyDuino > Teensy <version>`
- Select USB type as **Raw HID**
    - `Tools > USB Type > Raw HID`
        - kudos to this [forum](https://forum.pjrc.com/threads/54413-after-upgrading-to-Arduino-IDE-1-8-7-and-Teensy-loader-1-44-no-teensy-boards-detected)
        - **NOTE**: It seems like you only have to do this once and then can change the USB Type back to **Serial**.
            - See #2 [here](https://www.pjrc.com/teensy/troubleshoot.html)