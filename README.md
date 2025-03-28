**Smart Waste Management System - Arduino Code**

This project is an  IoT-based Smart Waste Management System using an  Arduino microcontroller. The system integrates sensors to monitor dustbin fill levels and detect harmful gases, sending SMS alerts when necessary.

Features

- **Automatic Dustbin Lid Operation**  
  - Uses an  IR sensor to detect waste disposal.  
  - Controls a servo motor to open/close the lid.  

- **Waste Level Monitoring**  
  - Uses an ultrasonic sensor to measure dustbin fill levels.  
  - Maps the distance to a percentage-based fill level.  
  - Sends an SMS alert when the bin exceeds 80% capacity.  

- **Gas Leakage Detection**  
  - Uses a gas sensor to detect harmful gases.  
  - Sends an SMS alert if gas concentration exceeds safe levels.  


 **Components Used**

- Arduino Board (e.g., NodeMCU or Arduino Uno)  
- Servo Motor (for automated lid control)  
- Ultrasonic Sensor (HC-SR04) (for distance measurement)  
- IR Sensor (to detect waste disposal)  
- Gas Sensor (MQ-135 or similar) (to detect hazardous gases)  
- GSM Module (for SMS notifications)  


**Code Breakdown**

1️⃣ **Setup and Initialization**
- Initializes serial communication for debugging (`Serial.begin(9600)`).  
- Defines sensor input/output pins (`pinMode()` and `Servo.attach()`).  

 2️⃣ **Distance Measurement with Ultrasonic Sensor**
- Sends a trigger pulse and measures the echo time using `pulseIn()`.  
- Converts time to distance (10 cm) and maps it to fill level (95 %).  
- If the bin is more than 80% full, an SMS alert is sent.  

3️⃣ **IR Sensor-Based Lid Operation**
- Detects if waste is placed near the sensor.  
- Opens the servo motor lid (`myServo.write(90)`).  
- Closes it after a 5-second delay.  

4️⃣ **Gas Sensor Detection**
- Reads gas concentration using `analogRead(A0)`.  
- Sends an SMS alert if gas levels exceed 1000.  

5️⃣ **SMS Alert System (GSM Module)**
- Uses AT commands to send alerts via SMS.  
- Sends messages when dustbin is full or harmful gases are detected.  


**Usage Instructions**
1. Connect the sensors and GSM module to the Arduino board. 
2. Upload the code using Arduino IDE.
3. Monitor the serial output for real-time status.
4. Receive SMS alerts for waste level and gas detection.

**Future Enhancements**
🔹 Cloud Integration – Store data on a remote server for analytics.  
🔹 Mobile App Alerts– Use a mobile app instead of SMS for notifications.  
🔹 Multiple Bin Monitoring – Extend the system to monitor multiple bins in a network.  

**Contributors**
- DHANUSHREE D – Code & Implementation  
- Ms. S. GOMATHI ME.,AP/CSE  – Project Mentor
