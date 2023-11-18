# Automatic-ambient-light-sensing-LED-that-changes-brightness-based-on-ambient-lighting
The project involves the process of designing a smart display brightness system for a mobile device that changes the brightness of an LED based on ambient light sources sensed through a Light Dependent Resistor (LDR). An
Procedure:
Step 1: Open the Wokwi Online Simulator and take the ESP32 Board.

Step 2: Make the connections as per the circuit diagram.
- Connect the LDR to an input pin on your ESP32 microcontroller.
- Connect the LED to a digital output pin via a current-limiting resistor.
- Connect the other end of the LED to the ground (GND).
- Connect the other end of the LDR to 5V.

Step 3: Write the Arduino Code in the IDE which reads the LDR's value, and maps it to LED brightness (0-
255), and sets the LED's brightness accordingly. We can adjust the delay and map range to fine-tune
the responsiveness.

Step 4: By clicking the Run button, we can observe the ambient light values.

Step 5: Test the automatic ambient light sensing LED system in various lighting conditions to ensure it
adjusts the LED brightness accordingly.

Code:
const int LDR_PIN = 34; // Define the pin connected to the LDR
const int LED_PIN = 12; // Define the pin connected to the LED
void setup() {
pinMode(LDR_PIN, INPUT);
pinMode(LED_PIN, OUTPUT);
}
void loop() {
int sensorValue = analogRead(LDR_PIN); // Read the LDR value (0-4095)
int brightness = map(sensorValue, 0, 4095, 0, 255); // Map to LED brightness
(0-255)
analogWrite(LED_PIN, brightness); // Set LED brightness
delay(100); // Add a small delay for stability
}
