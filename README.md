🔆 Arduino Street Light Code
This repository contains a simple yet effective Arduino sketch for simulating an automatic street light system using an LDR (Light Dependent Resistor) sensor. The light automatically turns ON in low-light conditions and OFF in bright conditions, mimicking how real-world street lights operate.

🛠️ Features
📟 Automatic Light Control: Turns the LED (representing a street light) ON when it gets dark and OFF when it's bright.

📈 LDR Sensor Integration: Uses analog input from a photoresistor to detect ambient light levels.

🔧 Threshold Customization: Easily adjust the sensitivity to ambient light using the threshold value.

🪵 Serial Output: Real-time light sensor readings are displayed via the Serial Monitor for debugging and calibration.

🧾 Code Overview
cpp
Copy
Edit
const int ledpin = 13;       // LED connected to digital pin 13
const int lightpin = A2;     // LDR sensor connected to analog pin A2
const int threshold = 100;   // Light threshold value to toggle LED

void setup() {
  Serial.begin(9600);
  pinMode(ledpin, OUTPUT);
  pinMode(lightpin, INPUT);
}

void loop() {
  int lightsens = analogRead(lightpin); // Read LDR sensor value
  Serial.print("LDR Value: ");
  Serial.println(lightsens);

  if (lightsens < threshold) {
    digitalWrite(ledpin, HIGH);  // Turn on LED in darkness
    delay(1500);
  } else {
    digitalWrite(ledpin, LOW);   // Turn off LED in light
  }
}
🧰 Hardware Requirements
Arduino Uno or compatible board

LDR (Light Dependent Resistor)

10kΩ resistor (for LDR voltage divider)

LED

Breadboard and jumper wires

USB cable for programming

⚙️ How It Works
The LDR measures the light intensity and sends an analog value to pin A2.

This value is compared to a pre-defined threshold.

If the value is less than 100, the environment is dark → turn the LED ON.

If the value is greater than or equal to 100, the environment is bright → turn the LED OFF.

Serial output provides continuous sensor readings for calibration or monitoring.

📦 Applications
Smart street lighting

Home automation lighting systems

Energy-saving lighting in public spaces

Basic IoT or embedded systems project

📌 Notes
You can fine-tune the threshold value depending on your environment's brightness.

For better energy efficiency and scaling, this code can be extended with relay modules or multiple sensors.

📄 License
This project is open-source under the MIT License.
