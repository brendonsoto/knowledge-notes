---
aliases: 
created: 2022-04-28, 8:58:01 am (Thursday, April 28th)
updated: 2022-04-29, 9:07:24 am (Friday, April 29th)
---
For the CLI route, there's this [page](https://www.pjrc.com/teensy/loader_cli.html ) for instructions from the Teensy site.
Essentially, it links to the [github repo](https://github.com/PaulStoffregen/teensy_loader_cli).
The repo also has a helpful link on packages other Linux distros needed to install.

## Solus
#to-do I need to revisit this section.
I made the mistake of doing both CLI version and Teensyduino back to back.
Then I went with Teensyduino since it was familiar to college days of using Arduino IDE.

When trying to set up the CLI route I wound up installing the following packages based on the link in the repo to other possibly needed packages and messing around with `make`:

- `avr-libc`
- `avr-gcc`
- `avr-binutils`
- `libusb-compat`
- `libusb-devel`
- `libusb-compat-devel`
- `isl-devel`
- `isl-32bit`
- `glibc-32bit`
- `libstdc++-32bit`
- `libgcc-32bit`

The `*-32bit` versions came from `make` outputting errors about 32bit stuff.
I think I just guessed the microcontroller was 32bit and thus tried installing those packages.