# AI/ML-Enabled Tennis Racket

This project involves the development of trend in smart sensor enabled device, such as sports sensor for greater insight. In this case, we examine the use case of the smart tennis racket that leverages sensor technology and embedded machine learning to enhance player performance. The system is designed to capture and analyze real-time motion and impact data, providing valuable insights and feedback to help players improve their game.

## Features

- **Real-Time Data Collection**: Integrated sensors capture motion, orientation, and impact forces during play.
- **Embedded AI/ML Processing**: On-device machine learning models classify swing types and detect performance patterns.
- **Wireless Communication**: Bluetooth and ANT capabilities for seamless data transfer to smartphones or other devices.
- **Power Management**: Optimized for low-power operation to extend battery life.
- **User Interaction**: Companion mobile app for detailed analytics, feedback, and device configuration.

## Goals

- Enhance player training through detailed performance insights.
- Provide real-time feedback to help improve technique and consistency.
- Offer a scalable platform for integrating additional sensors and features.

## Technologies Used

- **Hardware**: Sparkfun nRF52840 Mini - Bluetooth Development Board, Nordic Thingy:53, Bosch BMI270, LSM6DSV16X - 6DoF IMU, Poly Lithium Ion Battery LiPo 3.7V 250mAh
- **Software**: Zephyr RTOS, TensorFlow Lite Micro, Edge Impulse
- **Communication**: Bluetooth Low Energy (BLE), ANT

## Repository Structure

```
smart-tennis-racket/
├── README.md
├── system-architecture-overview.md      # Layered hardware/software architecture description
├── software-engineering-design-elements.md  # Software design principles and module breakdown
└── security-architecture.md             # Security model including MCUBoot, DFU, and encryption
```

## Development Status

This repository is currently in the **architecture and design phase**. The documents present define the intended system design across hardware, software, and security layers. Firmware implementation has not yet begun.

### What exists

- System architecture documentation covering sensor acquisition, data processing, communication, power management, and the application layer.
- Software engineering design covering the RTOS task model (Zephyr), sensor driver abstraction, embedded ML integration (TensorFlow Lite Micro / Edge Impulse), BLE/ANT communication stack, and power management strategy.
- Security architecture covering MCUBoot secure boot, OTA firmware update (DFU), AES-256 on-device encryption, BLE secure pairing, and rollback protection.

### Planned next steps

1. **Set up the Zephyr workspace** - initialise a west workspace targeting the SparkFun nRF52840 Mini and Nordic Thingy:53 boards.
2. **IMU driver bring-up** - implement Zephyr sensor drivers for the Bosch BMI270 and STMicroelectronics LSM6DSV16X over SPI/I2C.
3. **Sensor fusion and feature extraction** - develop pre-processing pipelines (filtering, normalisation) and extract swing-relevant features for the ML pipeline.
4. **Edge Impulse model integration** - train a swing-classification model via Edge Impulse, export as a TensorFlow Lite Micro library, and integrate into the Zephyr build.
5. **BLE peripheral application** - implement the GATT service for streaming sensor data and inference results to a companion mobile app.
6. **MCUBoot and DFU** - integrate MCUBoot as the secure bootloader and configure OTA firmware update support.

### Getting started (once firmware exists)

The firmware will be built with the [Zephyr RTOS](https://docs.zephyrproject.org/latest/develop/getting_started/index.html). The anticipated setup steps are:

```bash
# Install west and initialise the workspace
pip install west
west init -m https://github.com/danny-cagney/smart-tennis-racket.git smart-tennis-racket
cd smart-tennis-racket
west update

# Build for the SparkFun nRF52840 Mini
west build -b sparkfun_pro_nrf52840_mini app/

# Flash via JLink or DFU
west flash
```

These steps will be updated and validated as the firmware develops.

## Contributing

Contributions are welcome. If you would like to help with firmware bring-up, sensor driver development, or ML model training, please fork the repository and open a pull request. For significant changes, consider opening an issue first to discuss the approach.
