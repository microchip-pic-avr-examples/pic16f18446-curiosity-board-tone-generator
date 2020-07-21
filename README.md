<div id="readme" class="Box-body readme blob js-code-block-container">
  <article class="markdown-body entry-content p-3 p-md-6" itemprop="text"><p><a href="https://www.microchip.com" rel="nofollow"><img src="https://camo.githubusercontent.com/5fb5505f69a28ff407841612dfe2b7004f210594/68747470733a2f2f636c6475702e636f6d2f553071684c7742696a462e706e67" alt="MCHP" data-canonical-src="https://cldup.com/U0qhLwBijF.png" style="max-width:100%;"></a></p>

# Introduction

In this project I use the NCO of the PIC16F18446 to generate a square wave with a desired frequency.

![Demo](image/demo.png)

# Description

In this demo,
*    PIC16F18446 (20-pin, PDIP) MCU is used to generate an adjustable frequency square signal.
*    The Curiosity development board is used as it has got on-board programmer and debugger.
*   A set of headphones in used to hear the output sound.

The frequency is adjusted using the POT1 on the Curiosity Board. The POT1 is read using the PIC's ADCC. In order to hear the sound, the headphone set must be connected in series with 1k resistor to RC1 and GND.

# Software Tools

Make sure the latest MCC libraries for PIC16F18446 MCU are installed. The demo/example uses the following version of software tools from Microchip:

*    MPLAB® X IDE v5.30
*    MPLAB® Code Configurator (Plugin) v3.95
*    MCC Core v4.85
*    Microcontrollers and peripherals Library v1.79

# Demo Hardware Setup

*    Plug the PIC16F18446 MCU into its socket on the Curiosity board
*    Connect a set of headphones in series with 1k resistor to RC1 and GND

# MCC Settings

This section shows the settings used in the demo/example for various MCU modules configuration. These settings were done using the Microchip Code Configurator (MCC). Open MCC to look at the settings of the modules.

### System Module Settings

The MCU uses the high frequency internal oscillator (HFINTOSC), and the clock is set to 8 MHz. Watchdog Timer is not used in this demo, so it is disabled.

![System Module settings](image/oscillator.png)

### ADCC Settings

ADCC is used to read the POT1. It is configured to operate in basic mode, with a clock of Fosc/64.

![ADCC settings](image/adcc.png)

### NCO1 Settings

NCO1 is used to generate the square signal on a specific frequency. It is configured to operate in fixed duty cycle (FDC) mode, with output active high, and clock source Fosc.

![NCO1 settings](image/nco.png)

### Pin Manager Settings

The pins are configured as follows:
* ADCC input on RC0, named channel_ANC0
* NCO1 output is connected to pin RC1

![Pin Manager](image/pin.png)

![Pin Module](image/pin_mod.png)

# Operation

1. After making the above hardware connections, connect the headphones in series with 1k resistor to RC1 and GND.
2. Connect the Curiosity board to PC using the USB cable.
3. Build demo firmware and load the generated hex file onto the PIC16F18446 MCU. When the demo firmware is loaded, a tone will be heard in the headphones.
4. Move the POT1 to adjust the tone frequency.

# Conclusion

This example shows how easy it is to use the PIC16F18446 and MCC to make a simple tone generator.
