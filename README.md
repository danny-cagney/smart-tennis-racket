# AI/ML-Enabled Tennis Racket

This project involves the development of a smart tennis racket that leverages advanced sensor technology and embedded machine learning to enhance player performance. The system is designed to capture and analyze real-time motion and impact data, providing valuable insights and feedback to help players improve their game.

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

- **Hardware**: Sparkfun nRF52840 Mini - Bluetooth Development Board, Nordic Thingy:53, Bosch BMI270, LSM6DSV16X - 6DoF IMU
- **Software**: Zephyr RTOS, TensorFlow Lite Micro, Edge Impulse
- **Communication**: Bluetooth Low Energy (BLE), ANT

## Getting Started

1. **Clone the repository**: `git clone https://github.com/danny-cagney/tennis-racket-AI-ML.git`
2. **Hardware Setup**: Instructions on integrating sensors and microcontrollers.
3. **Software Setup**: Guidelines for setting up the development environment, including toolchains and dependencies.
4. **Running the Project**: Steps to compile and flash the firmware, along with basic usage instructions.

## Contributing

Contributions are welcome! Please fork the repository and create a pull request with your enhancements or bug fixes.
