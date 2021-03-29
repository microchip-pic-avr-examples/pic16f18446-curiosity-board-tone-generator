[![MCHP](images/microchip.png)](https://www.microchip.com)

# Tone Generator Using NCO

In this project the NCO of the PIC16F18446 is used to generate a square wave with a desired frequency.

## Related Documentation
- [PIC16F18446 Product Family Page](https://www.microchip.com/design-centers/8-bit/pic-mcus/device-selection/pic16f18446)
- [PIC16F18446 datasheet](http://ww1.microchip.com/downloads/en/DeviceDoc/40001985B.pdf) for more information or specifications.



## Software Used
- MPLAB® X IDE 5.30 or newer [(microchip.com/mplab/mplab-x-ide)](http://www.microchip.com/mplab/mplab-x-ide)
- MPLAB® XC8 2.10 or newer compiler [(microchip.com/mplab/compilers)](http://www.microchip.com/mplab/compilers)
- MPLAB® Code Configurator (MCC) 3.95 or newer [(microchip.com/mplab/mplab-code-configurator)](https://www.microchip.com/mplab/mplab-code-configurator)
- MPLAB® Code Configurator (MCC) PIC10/PIC12/PIC16/PIC18 library v1.79 or newer [(microchip.com/mplab/mplab-code-configurator)](https://www.microchip.com/mplab/mplab-code-configurator)

## Hardware Used
- PIC16F18446 PDIP20 with Curiosity Development Board [(DM164137)](https://www.microchip.com/Developmenttools/ProductDetails/DM164137)
- Generic earphones
- 3.5mm female jack break-out board
- 1kOhm resistor

## Setup

<br><img src="images/demo.png" width="600">

In this demo,
- PIC16F18446 (20-pin, PDIP) MCU is used to generate an adjustable frequency square signal.
- The Curiosity development board is used as it has got on-board programmer and debugger.
- A set of headphones in used to hear the output sound.

The frequency is adjusted using the POT1 on the Curiosity Board. The POT1 is read using the PIC's ADCC. In order to hear the sound, the headphone set must be connected in series with 1k resistor to RC1 and GND.

### Demo Hardware Setup

- Plug the PIC16F18446 MCU into its socket on the Curiosity board
- Connect a set of earphones in series with 1k resistor to RC1 and GND

### MCC Settings

This section shows the settings used in the demo/example for various MCU modules configuration. These settings were done using the Microchip Code Configurator (MCC). Open MCC to look at the settings of the modules.

### System Module Settings

The MCU uses the high frequency internal oscillator (HFINTOSC), and the clock is set to 8 MHz. Watchdog Timer is not used in this demo, so it is disabled.

<br><img src="images/oscillator.png" width="600">

### ADCC Settings

ADCC is used to read the POT1. It is configured to operate in basic mode, with a clock of Fosc/64.

<br><img src="images/adcc.png" width="600">

### NCO1 Settings

NCO1 is used to generate the square signal on a specific frequency. It is configured to operate in fixed duty cycle (FDC) mode, with output active high, and clock source Fosc.

<br><img src="images/nco.png" width="600">

### Pin Manager Settings

The pins are configured as follows:
- ADCC input on RC0, named channel_ANC0
- NCO1 output is connected to pin RC1

<br><img src="images/pin.png" width="600">

<br><img src="images/pin_mod.png" width="600">

## Demo

1. After making the above hardware connections, connect the headphones in series with 1k resistor to RC1 and GND.
2. Connect the Curiosity board to PC using the USB cable.
3. Build demo firmware and load the generated hex file onto the PIC16F18446 MCU. When the demo firmware is loaded, a tone will be heard in the headphones.
4. Move the POT1 to adjust the tone frequency.

## Conclusion

This example shows how easy it is to use the PIC16F18446 and MCC to make a simple tone generator.
