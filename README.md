# R.E.S-Smart-Car-Parking-System

R.E.S Smart Car Parking System
An automated, embedded system-based solution designed to manage vehicle entry, exit, and real-time parking space monitoring. Built using the Arduino Uno platform, this project integrates hardware sensors and software logic to solve urban parking congestion and efficiency challenges.

# 🚀 Features
1. Automated Gate Control: Uses a servo motor to open/close gates based on vehicle detection.
2. Real-time Slot Monitoring: Tracks available parking spaces and displays them on a 16x2 I2C LCD.
3. Non-Volatile Data Storage: Utilizes EEPROM to retain the current slot count even after a power failure.
4. Intelligent Logic: Prevents gate triggers when the parking lot is full and displays a "Parking Full" notification.
5. Dual-Sensor System: Separate IR sensors for entry and exit to ensure accurate vehicle counting.

# 🛠️ Hardware Components
1. Microcontroller: Arduino Uno (ATmega328P)
2. Sensors: 2x IR Sensors (Entry/Exit)
3. Actuator: Servo Motor (Gate Control)
4. Display: 16x2 I2C LCD Module
5. Memory: Internal EEPROM (for data persistence)
6. Others: Breadboard, Jumper Wires, 5V Power Source

# 💻 Software & Concepts
1. The system is programmed in Embedded C/C++ via the Arduino IDE. Key technical concepts implemented include:
2. PWM (Pulse Width Modulation): To precisely control the angle of the servo motor.
3. I2C Communication: For efficient wiring and communication with the LCD.
4. Flag-based Logic: To manage state transitions and prevent multiple triggers from a single vehicle.
5. Input/Output Interfacing: Reading binary signals from sensors and driving digital/analog outputs.

# 📂 Methodology
1. Initialization: The system reads the last saved slot count from EEPROM and displays a welcome message.
2. Entry Detection: When IR1 is triggered, the system checks if Slot > 0. If true, the gate opens, the slot count decrements, and the new value is saved to EEPROM.
3. Exit Detection: When IR2 is triggered, the gate opens, the slot count increments (up to MAX_SLOT), and the update is saved.
4. Display Loop: The LCD continuously refreshes to show "WELCOME!" and the "Slot Left" count.

# ⚖️ License
This project was developed as part of the Bachelor of Science in Computer Science program (Fall 2025) at KIET.
