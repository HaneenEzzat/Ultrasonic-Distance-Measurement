# Ultrasonic Distance Measurement with LED Indicator

This project demonstrates how to use an ultrasonic sensor to measure the distance of an object and display it on an LCD. An LED is used as an indicator that lights up when the object is within a specific range (less than 30 cm).

## Features

- Measures distance using an HC-SR04 ultrasonic sensor.
- Displays the measured distance on a 16x2 LCD.
- LED indicator lights up when the object is closer than 30 cm.
- Error handling for sensor timeouts or invalid readings.

## Hardware Requirements

- ATmega32 microcontroller
- HC-SR04 ultrasonic sensor
- 16x2 LCD display
- LED
- Resistors (as needed for LED)
- Breadboard and jumper wires
- Power supply (5V)

## Pin Configuration

### Microcontroller Pins

| Component       | Pin          |
|-----------------|--------------|
| LCD RS          | PD0          |
| LCD EN          | PD1          |
| LCD Data Pins   | PD4 to PD7   |
| Ultrasonic TRIG | PC0          |
| Ultrasonic ECHO | PC1          |
| LED             | PB0          |

## Software Requirements

- AVR-GCC compiler
- AVRDUDE for uploading code
- Atmel Studio or any other AVR development environment

## How It Works

1. The ultrasonic sensor sends out a sound wave via the TRIG pin.
2. The ECHO pin listens for the sound wave's reflection.
3. The time difference between sending and receiving the sound wave is measured.
4. The distance is calculated using the formula:
   
   ```
   Distance = (Time * Speed of Sound) / 2
   ```

5. The distance is displayed on the LCD.
6. The LED is turned on if the distance is less than 30 cm, otherwise it remains off.

## Code Overview

- **lcd_init()**: Initializes the LCD in 4-bit mode.
- **lcd_command()**: Sends commands to the LCD.
- **lcd_print()**: Displays text on the LCD.
- **lcd_set_cursor()**: Sets the cursor position on the LCD.
- **ultrasonic_init()**: Initializes the ultrasonic sensor pins.
- **ultrasonic_trigger()**: Sends a trigger pulse to the ultrasonic sensor.
- **get_pulse_width()**: Measures the width of the ECHO pulse.
- **led_control()**: Controls the LED based on the measured distance.
- **main()**: The main function loops continuously, measuring distance and updating the LCD and LED.

## Usage Instructions

1. Connect the components as per the pin configuration.
2. Upload the provided code to the ATmega32 microcontroller using an AVR programmer.
3. Power up the circuit.
4. Observe the distance displayed on the LCD and the LED behavior.

## Notes

- Ensure the ultrasonic sensor is positioned properly for accurate distance measurements.
- Modify the distance threshold in the code (`led_control()`) if needed.
- Use appropriate resistors with the LED to prevent damage.

## License

This project is open-source and available under the MIT License. Feel free to use, modify, and distribute it as needed.

---

Happy Coding!
