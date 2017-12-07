# RTC Example

The following guide describes how you can use the Real Time Clock (RTC).
To measure longer times it is recommended to make use of the RTC.
If the RTC is initialized the standard C date and time functions can be used.

> Epoche-converts are available to get the Unix timestamp to inizialize the RTC. [LINK](https://www.epochconverter.com/) 

## Step 1: Download mbed CLI

* [Mbed CLI](https://docs.mbed.com/docs/mbed-os-handbook/en/latest/dev_tools/cli/#installing-mbed-cli) - Download and install mbed CLI.

## Step 2: Import RTC-Example project

Import mbed RTC-Example project from GitHub.

```
mbed import https://github.com/mbed-Infineon-XMC/RTC-Example.git
```

## Step 3: Install ARM GCC toolchain

* [GNU ARM toolchain](https://launchpad.net/gcc-arm-embedded) - Download and install the last stable version of the ARM GCC toolchain.
* Open the file "mbed_settings.py" and add the ARM GCC install path.

Example:
```
#GCC_ARM_PATH = "home/bin/arm_gcc_toolchain/gcc-arm-none-eabi-5_4-2016q2/arm-none-eabi/bin"
```
## Step 4: Compile project

Navigate into the project folder and execute the following command:
```
cd RTC-Example.git/
mbed compile -m XMC_4500_RELAX_KIT -t GCC_ARM
```
mbed creates a BUID directory where you can find the executables (bin, elf, hex ...).

## Step 5: Flash to board

* [Segger JLink](https://www.segger.com/downloads/jlink) - Install the JLink software for your platform.
* Navigate to the BUILD directory and execute the following JLinkExe commands.
```
$ JLinkExe
J-LINK> device xmc4500-1024
J-LINK> h
J-Link> loadfile Blinky-Example.git.hex
J-Link> r
J-Link> g
```
* Choose SWD, 4000kHz as interface settings!!
