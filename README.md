# STM32_ADC_LED_Project
STM32 ADC and LED Control Project

This project utilizes an STM32F417VGT6 microcontroller to convert analog signals into digital values using the ADC (Analog-to-Digital Converter) and control an LED based on these values. The voltage applied to the PC1 pin is read by the ADC, converted to a digital value, and then used to determine the duration for which an LED connected to the PD4 pin will be lit.

Project Overview:
ADC (Analog to Digital Converter): The ADC converts analog signals (voltages) into digital values. In this project, voltages between 0-3.3V applied to the PC1 pin are converted into digital values.
LED Control: After converting the ADC value to a voltage, the LED will remain lit for a duration corresponding to the voltage value. For example, if 1V is read, the LED will stay on for 1 second; if 2V is read, it will stay on for 2 seconds.
Components Used
STM32F417VGT6 Microcontroller

PC1 Pin: The analog voltage input pin connected to the ADC1 module.

PD4 Pin: The output pin connected to the LED. The LED will be controlled based on the voltage.

LED: The LED will turn on or off depending on the voltage value read from the ADC.

How It Works:
A voltage between 0 and 3.3V is applied to the PC1 pin from an external power source (such as a power supply).
The ADC module converts this analog voltage into a digital value (0-4095).
The digital ADC value is converted back to a voltage value between 0-3.3V.
The voltage value is used as a time unit, and the LED will be lit for the corresponding number of seconds.
For example, 1V = 1 second of LED on-time.
This process repeats continuously in a loop, with the voltage being measured each time.
File Structure

main.c: The main file containing the logic for reading the ADC and controlling the LED.

stm32f4xx_hal_adc.c: The STM32 HAL ADC library file.

stm32f4xx_hal_gpio.c: The STM32 HAL GPIO control library file.

How to Run:
Open the project in STM32CubeIDE and build it.
Flash the program to the STM32F417VGT6 microcontroller.
Connect an external power source (e.g., a power supply) to the PC1 pin, applying a voltage between 0 and 3.3V.
The LED connected to the PD4 pin will stay on for a duration corresponding to the voltage read from the ADC.
As the voltage increases, the LED will stay on longer; as the voltage decreases, the LED will stay on for a shorter period.

Use Cases:
Sensor Data Processing: Convert analog signals from a sensor into digital signals and control an output based on these signals.
Power Monitoring: Monitor and control system components based on varying voltage levels.
Light Control: Adjust the brightness or on-time of LEDs based on input voltage.

Requirements:
STM32CubeIDE
STM32F417VGT6 microcontroller
Power supply (0-3.3V voltage source)
LED and resistor
