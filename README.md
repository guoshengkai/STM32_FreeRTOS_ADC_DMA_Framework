# STM32 FreeRTOS ADC DMA Framework

A modular embedded firmware framework based on the STM32L476RG microcontroller for real-time multi-channel data acquisition and embedded signal processing.
The project demonstrates how to combine FreeRTOS (CMSIS-RTOS V2), multi-channel ADC with DMA circular mode, UART communication, and CMSIS-DSP into a scalable software architecture suitable for embedded sensing and edge intelligence applications.

---

## Features

- STM32CubeMX generated project
- CMSIS-RTOS V2 (FreeRTOS)
- Multi-thread architecture
- Multi-channel ADC scan mode
- DMA Circular Mode
- DMA Half/Full Transfer Callback
- Channel de-interleaving
- UART communication (to ATK-BLE05 BLE module)
- Modular ADC driver (`app_adc.c`)
- CMSIS-DSP library integrated
- Ready for FFT, digital filtering and feature extraction

---

## Hardware/Tools

- STM32 NUCLEO-L476RG board & ATK-BLE05 Module
- STM32CubeIDE
- STM32CubeMX

---

## Software Architecture
                +---------------------+
                |   Physical Sensors (optional)  |
                +----------+----------+
                           |
                           v
                +---------------------+
                | Multi-Channel ADC   |
                +----------+----------+
                           |
                           v
                +---------------------+
                | DMA Circular Buffer |
                +----------+----------+
                           |
          +----------------+----------------+
          |                                 |
          v                                 v
 Half Transfer Callback           Full Transfer Callback
          |                                 |
          +----------------+----------------+
                           |
                           v
                +---------------------+
                | ADC Buffer Manager  |
                | (app_adc.c)         |
                +----------+----------+
                           |
                           v
                +---------------------+
                | FreeRTOS Task       |
                +----------+----------+
                           |
                           v
                +---------------------+
                | CMSIS-DSP           |
                +----------+----------+
                           |
                           v
                +---------------------+
                | UART / BLE          |
                +---------------------+


| Function | Status |
|----------|--------|
| FreeRTOS (CMSIS-V2) | ✅ |
| ADC Multi-channel | ✅ |
| DMA Circular | ✅ |
| Half / Full Callback | ✅ |
| UART Debug | ✅ |
| CMSIS-DSP Integration | ✅ |
| BLE Transmission | ✅ |
