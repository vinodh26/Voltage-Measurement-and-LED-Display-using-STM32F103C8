# Voltage-Measurement-and-LED-Display-using-STM32F103C8

1. Introduction
   
This project aims to measure voltage using the STM32F103C8 microcontroller's built-in Analog-to-Digital Converter (ADC) and display the voltage reading on an LED. The STM32F103C8 is a popular microcontroller based on the ARM Cortex-M3 architecture and is commonly used in various embedded applications.

3. Hardware Components

- STM32F103C8 microcontroller board
- Voltage source (e.g., battery or variable power supply)
- Potentiometer (optional, for testing voltage range)
- LED and current-limiting resistor
- Breadboard and jumper wires

3. Software Tools
   
- STM32CubeIDE: Integrated Development Environment for STM32 microcontrollers
- STM32CubeMX: For configuring the microcontroller peripherals and generating initialization code
- Standard Peripheral Library (SPL) or STM32Cube HAL: For STM32F1 series peripherals and GPIO management

4. Project Implementation

4.1. Hardware Setup

- Connect the voltage source (e.g., battery or variable power supply) to the ADC input pin (e.g., PA0) of the STM32F103C8.
- Connect an optional potentiometer between the voltage source and the ADC input pin to simulate variable voltage for testing.
- Connect an LED with a current-limiting resistor to one of the GPIO pins (e.g., PC13) of the STM32F103C8.

4.2. STM32CubeMX Configuration

- Open STM32CubeMX and create a new project for the STM32F103C8 microcontroller.
- Configure the ADC peripheral to use the appropriate channel (e.g., ADC1_IN0) for reading the voltage.
- Configure the GPIO pin (e.g., PC13) to control the LED.

4.3. ADC Initialization

- Initialize the ADC module with appropriate settings for continuous conversion mode and ADC channel selection.
- Set the ADC conversion resolution (e.g., 12-bit resolution).
- Set the ADC clock source and prescaler.

4.4. Voltage Measurement

- Start the ADC conversion and wait for it to complete.
- Read the ADC value from the data register.
- Convert the ADC value to voltage using the formula: `voltage = (adcValue * Vref+) / 4095`, where Vref+ is the reference voltage (e.g., 3.3V).

4.5. LED Control

- Use a simple threshold approach to control the LED brightness based on the voltage reading.
- Scale the voltage reading to control the LED brightness (e.g., 1V corresponds to full brightness, 0V is off).
- Use a GPIO pin (e.g., PC13) to control the LED state (ON/OFF) directly.

4.6. Main Loop

- In the main loop, continuously read the voltage and update the LED state based on the voltage reading.

5. Testing and Verification
   
- Test the voltage measurement and LED display functionality with a known voltage source (e.g., battery or potentiometer).
- Verify that the LED brightness corresponds to the measured voltage.

6. Conclusion
   
The Voltage Measurement and LED Display project using the STM32F103C8 microcontroller successfully demonstrates the use of the ADC module to measure voltage and the GPIO to control an LED based on the voltage reading. This project can be used in various applications where real-time voltage monitoring and display are required, such as battery voltage monitoring, power supply monitoring, or sensor interfacing. The project can be extended to add more features, such as serial communication to transmit voltage data to a PC or display the voltage reading on an LCD screen.
