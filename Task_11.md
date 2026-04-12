# Task 11: LED Toggle via ESP32 Web Server

---

### 1. Objective
To control an LED wirelessly from a phone or laptop. The ESP32 hosts a simple website; clicking buttons on the site sends a signal to the ESP32 to turn the LED on or off.

### 2. The Components 
* **ESP32:** The "brain" with built-in Wi-Fi. It runs the website.
* **LED:** The light we want to control .
* **Resistor:** Limits electricity to protect the LED .
* **USB Cable:** Provides power and uploads the code .
---



### 4. Lab Setup Visualization
Below is the  image showing the physical setup from the lab.

![Complete Lab Setup and Laptop](https://github.com/anvitapranjal18-glitch/Marvel_Induction_2026/raw/main/lab_setup.jpg)



---

### 5. How it Works 
1. **The Handshake:** The ESP32 connects to the Wi-Fi. It is assigned a unique number called an **IP Address**.
2. **The Server:** The ESP32 hosts a tiny web page. Typing the **IP Address** into a phone's browser shows "ON" and "OFF" buttons.
3. **The Trigger:** Clicking a button sends a request. The ESP32 receives it and sends electricity (HIGH signal) to **GPIO Pin 2**, lighting the LED.

