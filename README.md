
# FAN-SPEED-CONTROLLER-SYSTEM-USING-TEMPERATURE-SENSOR
# EXP 1(A) FAN SPEED CONTROLLER SYSTEM USING TEMPERATURE SENSOR

## Aim:
	To measure the Temperature using DHT11/DHT22/TMP36  sensor with Arduino UNO Board/ESP-32 using Tinker CAD.

## Hardware / Software Tools required:
	PC/ Laptop with Internet connection
    Tinker CAD tool (Online)
	Arduino UNO Board/ESP-32
	Temperature Sensor (DHT11/DHT22/TMP36)

##  Circuit Diagram:

---
<img width="1042" height="569" alt="image" src="https://github.com/user-attachments/assets/362bbd59-92fe-4cc4-ac20-fe3b4f0453fe" />

--

##  Procedure

Step 1: Open Tinkercad

- Log in to Tinkercad using your web browser. 
 
- Go to Circuits → click Create New Circuit.

Step 2: Place Components

- Drag an Arduino Uno board into the workspace.

- Place a TMP36 temperature sensor on the breadboard.

- Add a breadboard for easier wiring.

- Use wires to connect the parts.

Step 3: Connect the TMP36 Sensor

- Pin connections of TMP36 (flat face towards you, left → right):

- Vs (Pin 1, left) → Arduino 5V (via breadboard + rail).

- Vout (Pin 2, middle) → Arduino A0.

- GND (Pin 3, right) → Arduino GND (via breadboard – rail).

- Breadboard power rails:

- Connect Arduino 5V to the breadboard + rail.

- Connect Arduino GND to the breadboard – rail.

- Connect TMP36 pins to these rails as shown in the circuit.

Step 4: Set Up the Code Editor

- In Tinkercad, click on the Code button.

- Switch to Text mode to prepare for writing the program.

Step 5: Simulate the Circuit

- Click Start Simulation.

- Open the Serial Monitor to observe the temperature readings.

Step 6: Troubleshoot

- If no output is shown, check wiring (Vs → 5V, GND → GND, Vout → A0).

- Ensure the sensor is correctly placed on the breadboard.

Step 7: Save the Project

- Click Stop Simulation when done.

- Save the circuit for future use.
 
# Program

```
const int analogIn = A0;

int humiditysensorOutput = 0;

// Defining Variables

int RawValue= 0;

double Voltage = 0;

double tempC = 0;

double tempF = 0;

void setup(){

 Serial.begin(9600);
 
 pinMode(A1, INPUT);
 
}

void loop(){

 RawValue = analogRead(analogIn);
 
 Voltage = (RawValue / 1023.0) * 5000; // 5000 to get millivots.
 
 tempC = (Voltage-500) * 0.1; // 500 is the offset
 
 tempF = (tempC * 1.8) + 32; // convert to F
 
 Serial.print("Raw Value = " );
 
 Serial.print(RawValue);
 
 Serial.print("\t milli volts = ");
 
 Serial.print(Voltage,0); //
 
 Serial.print("\t Temperature in C = ");
 
 Serial.print(tempC,1);
 
 Serial.print("\t Temperature in F = ");
 
 Serial.println(tempF,1);
 
 humiditysensorOutput = analogRead(A1);
 
 Serial.print("Humidity: "); // Printing out Humidity Percentage
 
 Serial.print(map(humiditysensorOutput, 0, 1023, 10, 70));
 
 Serial.println("%");
 
 delay(5000); //iterate every 5 seconds
 
}
```
## Output



https://github.com/user-attachments/assets/57f6c2c5-9802-4e92-8a7b-84f0f2ed2f63


## Result

Thus the Fan speed controller system using temperature sensor is executed successfully.
