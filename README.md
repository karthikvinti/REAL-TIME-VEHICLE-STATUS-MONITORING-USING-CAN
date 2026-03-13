# 🏎️ Real-Time Vehicle Status Monitoring Using CAN

## 📌 Overview
This project implements a **real-time vehicle monitoring system** using the **Controller Area Network (CAN) protocol**.  
The system continuously monitors important vehicle parameters and displays them on an **LCD dashboard**.

The project demonstrates how different **vehicle subsystems communicate through CAN bus** to share information efficiently.

The system monitors:

- ⛽ Fuel Level
- 🔁 Vehicle Indicators (Left / Right)
- 💥 Airbag Status (Accident Detection)

All nodes communicate through the **CAN bus**, enabling **real-time data exchange**.

---

# 🎯 Aim
To design and implement a **real-time vehicle monitoring system using CAN protocol** that displays important vehicle parameters such as:

- Fuel percentage
- Indicator status
- Airbag activation

---

# ⚙️ System Architecture

The system consists of **three nodes connected through a CAN bus**:

                                                  +-------------+
                                                  |  Fuel Node  |
                                                  +-------------+                  
                                                         \                         
                                                          \                        
                                                           +---------+             
                                                           | CAN BUS | 
                                                           +---------+             
                                                          /                        
                                                         /                         
                                                +-------------------+              
                                                |  Indicator Node   |  
                                                +-------------------+              
                                                        \                          
                                                         \                         
                                                          +---------+              
                                                          | CAN BUS |         
                                                          +---------+              
                                                               |                   
                                                               v                   
                                                     +------------------+  
                                                     | Main Dashboard   |
                                                     | Node (LCD)       |
                                                     +------------------+


Each node performs a **specific task** and communicates using **CAN messages**.

---

# 🧠 Project Nodes

## 1️⃣ Main (Dashboard) Node
This is the **central node** responsible for displaying vehicle status.

Functions:
- Displays fuel percentage on LCD
- Displays airbag status
- Sends indicator signals to indicator node
- Receives fuel information from fuel node
- Reads accelerometer data for accident detection

---

## 2️⃣ Fuel Node
Responsible for **fuel monitoring**.

Functions:
- Reads fuel sensor using ADC
- Converts ADC value into fuel percentage
- Sends fuel information to main node through CAN

---

## 3️⃣ Indicator Node
Responsible for **vehicle indicators**.

Functions:
- Receives CAN messages from main node
- Controls left and right LED indicators

---

# 🧰 Hardware Requirements

| Component | Description |
|--------|-------------|
| LPC2129 Microcontroller | Main controller |
| MCP2551 | CAN transceiver |
| LCD (20x4) | Display dashboard |
| MMA7660 | Accelerometer sensor |
| LEDs | Indicator simulation |
| Push Buttons | Indicator switches |
| Fuel Gauge / Potentiometer | Fuel input simulation |
| USB-UART Converter | Programming interface |

---

# 💻 Software Requirements

- Embedded C
- Keil µVision IDE
- Flash Magic
- CAN communication libraries

---

# 🛠️ Project Modules

## 📺 LCD Module
Displays:

- Fuel percentage
- Indicator status
- Airbag status
- Dashboard information

---

## 📈 ADC Module
Reads fuel sensor value and converts it into **fuel percentage**.

---

## 🚖 CAN Module
Handles **communication between nodes**.

Operations:
- Transmit data
- Receive data
- Frame formatting

---

## 🚨 Interrupt Module
Handles **external interrupts** for:

- Left indicator
- Right indicator

---

## 📄 I2C Module
Used for communication with the **MMA7660 accelerometer sensor**.

---

## ⛓️‍💥 Accelerometer Module
Reads **X, Y, Z acceleration values** and detects accidents.

If acceleration exceeds threshold → **Airbag is triggered**.

---

# 📡 CAN Message Format

| CAN ID | Data | Description |
|------|------|------|
| 1 | Fuel Percentage | Sent from Fuel Node |
| 2 | 0x01 | Left Indicator |
| 2 | 0x02 | Right Indicator |

---

# 🔄 Project Workflow

1️⃣ Fuel node reads fuel value using ADC.  

2️⃣ Fuel percentage is calculated.  

3️⃣ Fuel data is transmitted to main node using CAN.  

4️⃣ Main node receives fuel data and displays it on LCD.  

5️⃣ External interrupt detects indicator button press.  

6️⃣ Indicator command is sent to indicator node via CAN.  

7️⃣ Indicator node receives command and activates LEDs.  

8️⃣ Accelerometer detects sudden movement.  

9️⃣ If crash detected → airbag status is displayed.

---

# 📊 Output

The LCD dashboard displays:

      ------DASHBOARD------
      Fuel: ███  70%
      AIRBAG STATUS: OFF/ON
      Indicator: ← →
      
### 🧩 Overall Hardware Connection


### 🔕 When No Accident Occurs
![WhatsApp Image 2026-03-12 at 4 05 46 PM](https://github.com/user-attachments/assets/1b96663e-8e30-419a-a844-bdfd5cad5217)

### 🔔 When Accident Occurs
![WhatsApp Image 2026-03-12 at 4 05 46 PM (1)](https://github.com/user-attachments/assets/499f3161-2205-4815-8689-d24fb6f6efff)

---

# 🚀 Features

✔ Real-time vehicle monitoring  
✔ CAN-based distributed architecture  
✔ Fuel level monitoring  
✔ Indicator control system  
✔ Airbag accident detection  
✔ LCD dashboard display  

---

# ✨ Applications

- Automotive monitoring systems
- Vehicle dashboard systems
- Safety systems in vehicles
- CAN-based embedded systems

---

# 💡 Future Enhancements

- Add GPS for real-time vehicle tracking  
- Integrate GSM module for accident alerts  
- Monitor additional parameters (temperature, tire pressure, battery)  
- Develop mobile/web dashboard for remote monitoring  
- Implement cloud or SD card data logging

---

# 🏁 Conclusion

This project demonstrates how **CAN protocol enables reliable communication between multiple vehicle subsystems**.

The system improves:

- **Vehicle safety**
- **Real-time monitoring**
- **Efficient communication between nodes**

---

# 👨‍💻 Author

**Karthik Vinti**   
Electronics and Communication Engineering  
Developer of *Real-Time Vechicle Status Monitoring Using CAN*

---

# 📜 License

This project is developed for academic and learning purposes. You are free to modify and enhance it with proper credit.

⭐ If you find this project useful, consider giving it a star on GitHub.
