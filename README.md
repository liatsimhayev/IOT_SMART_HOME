# **FEEDME - Smart IoT-Based Automatic Pet Feeder**

## **📌 Project Overview**
**FEEDME** is an **IoT-based automated pet feeding system** designed to ensure that pets receive food at regular intervals while providing real-time monitoring of food levels. The system automatically dispenses food when the weight in the feeding bowl falls below a predefined threshold and alerts the owner in case of critical shortages. Additionally, manual feeding can be triggered via a dedicated button in the user interface (GUI).

The system utilizes **MQTT communication**, **PyQt5 for GUI**, and **SQLite for data storage**, making it highly reliable, scalable, and easy to use.

---

## **🔧 System Components**

1️⃣ **Weight Sensor Emulator** (`WeightSensor.py`)  
   - Simulates a weight sensor by generating random weight values.  
   - Publishes weight data via MQTT every few seconds.  
   - Triggers an alert if the weight is below **3 grams** (critical level).  

2️⃣ **Relay Controller** (`RELAY.py`)  
   - Listens for weight updates via MQTT.  
   - Activates the relay to dispense food when the weight falls below **10 grams**.  
   - Turns off the relay when sufficient weight is detected.  

3️⃣ **Manual Feeding Button** (`BUTTON.py`)  
   - Provides an interface for manual food dispensing.  
   - Sends "Feed Now" and "Stop Feeding" messages via MQTT.  

4️⃣ **GUI Dashboard** (`iot_gui.py`)  
   - Displays real-time food levels, relay status, and alerts.  
   - Allows users to monitor feeding history from the database.  
   - Updates automatically with new sensor readings.  

5️⃣ **MQTT Communication & Data Manager** (`mqtt_init.py` and `data_manager.py`)  
   - Manages MQTT broker connections and topics.  
   - Stores all feeding events in an **SQLite database** (`iot_data.db`).  
   - Sends alerts for critical food shortages.  

---

## **🚀 How to Run the Project**

### **Prerequisites**
Ensure you have the following installed:  
- **Python 3.7+**  
- **PyQt5** (`pip install PyQt5`)  
- **Paho-MQTT** (`pip install paho-mqtt`)  
- **SQLite3** (included with Python)  

### **Running the System**

1️⃣ **Open the project folder in CMD (Command Prompt)**  

2️⃣ **Run the Weight Sensor Emulator**  

3️⃣ **Run the Relay Controller**  

4️⃣ **Run the Manual Feeding Button**  

5️⃣ **Run the GUI Dashboard**  

6️⃣ **Ensure the Data Manager is running**  

💡 **Note:** Each component should be executed in a **separate CMD window** to ensure full system functionality.

---

## **🖥 System Flow & Working Mechanism**

1️⃣ The **weight sensor** continuously checks the food level and publishes the weight to the **MQTT broker**.  
2️⃣ If the weight **drops below 10 grams**, the **relay is activated**, and food is dispensed.  
3️⃣ If the weight **drops below 3 grams**, a **critical alert** is sent to notify the owner.  
4️⃣ The **GUI updates** in real-time, displaying weight readings, relay status, and alerts.  
5️⃣ The **manual button** allows the owner to **trigger or stop feeding** manually.  
6️⃣ All feeding events and alerts are **logged in the database** for analysis.

---

## **📊 Data Logging & Storage**
- Every MQTT message is recorded in an **SQLite database** (`iot_data.db`).  
- The **GUI retrieves and displays** feeding history, relay activations, and critical alerts.  
- Stored data includes **timestamps, topics, and messages** for better tracking and analysis.  

---
## **🔍 Future Improvements**
✔️ **Dietary Tracking:** Implementing calorie tracking to prevent overfeeding.  
✔️ **Cloud Integration:** Storing feeding data on the cloud for remote access.  
✔️ **Advanced AI:** Using AI to predict pet eating patterns and optimize feeding schedules.  

---

## **💡 Contributors & Contact**
This project was developed as part of an **IoT course**.  

📧 **Emails:**  
- **Miri Yakobson** - [miriamyakobson200021@gmail.com](mailto:miriamyakobson200021@gmail.com)  
- **Liat Simhayev** - [liat191103@gmail.com](mailto:liat191103@gmail.com)  

📂 **GitHub Repository:**  
- **Miriam Yakobson** - [github.com/miri-y](https://github.com/miri-y)  
- **Liat Simhayev** - [github.com/liatsimhayev](https://github.com/liatsimhayev)  

---

🚀 **Thank you for using FEEDME!** 🚀
