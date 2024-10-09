Raspberry Pi Pico USB-UART Bridge, modified for CBUS
=================================

This program bridges the Raspberry Pi Pico HW UARTs to two independent USB CDC serial devices in order to behave like any other USB-to-UART Bridge controllers.

When the transmitter is off, the TX pin is reconfigured to not drive the line. That way, when tx and rx are connected, we get a single-duplex one-wire connection. This is used by CBUS.

# No-echo mode
Pin 6 (GP6) is used to configure line echo. It's configured with an internal pullup, but if tied to gnd, the RX pin is disabled while transmitting, so we're no longer echoing the bytes we send.


Disclaimer
----------

This software is provided without warranty, according to the MIT License, and should therefore not be used where it may endanger life, financial stakes, or cause discomfort and inconvenience to others.

Raspberry Pi Pico Pinout
------------------------

| Raspberry Pi Pico GPIO | Function |
|:----------------------:|:--------:|
| GPIO16 (Pin 21)        | UART0 TX |
| GPIO17 (Pin 22)        | UART0 RX |
| GPIO4 (Pin 6)          | UART1 TX |
| GPIO5 (Pin 7)          | UART1 RX |
