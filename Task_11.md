## **Task 11: IoT Integration — ESP32 Web Server Control**

### **Description**

The core objective of this task was to transcend local hardware control by developing a standalone **IoT Web Server** using the **ESP32 development board**. Unlike the Arduino Uno, the ESP32 features an integrated Wi-Fi stack, enabling it to host a website that can be accessed by any device on the same network. This task involved programming the board to handle **Asynchronous HTTP Requests**, allowing for the remote toggling of a physical LED via a browser-based UI. This project serves as a foundational exercise in **Full-Stack Embedded Engineering**, bridging the gap between web interfaces and hardware actuators.

### **Detailed Process**

- **Network Handshake & Station Mode:** I initiated the task by configuring the ESP32 in **Station (STA) Mode**. I used the `WiFi.h` library to pass my local SSID and Password to the board. I implemented a `while` loop to poll the connection status, ensuring the code only proceeded once a local IP address was successfully assigned by the router.
  ```cpp
  while (WiFi.status() != WL_CONNECTED) {
    delay(500);
    Serial.print(".");
  }
  Serial.println("IP address: ");
  Serial.println(WiFi.localIP());
  ```
- **HTML/CSS UI Injection:** To create a user interface without an external hosting service, I embedded a raw HTML string within the Arduino sketch. This string included CSS for styling buttons and the logic for the browser to send GET requests to the ESP32's IP address.
- **Route Handling & GPIO Execution:** I utilized the `WebServer.h` library to define "Routes" or endpoints. I mapped the `/H` URL path to a function that sets the LED pin to `HIGH` and the `/L` path to a function that sets it to `LOW`.
  ```cpp
  // Server endpoint for turning the LED ON
  server.on("/H", []() {
    digitalWrite(ledPin, HIGH);
    server.send(200, "text/html", "<h1>LED is ON</h1><a href='/L'>Turn OFF</a>");
  });
  ```
- **Real-time Debugging & Testing:** Once the server was live, I accessed the IP address from my mobile phone. I monitored the **Serial Monitor** at 115200 baud to track incoming HTTP headers and ensured that the ESP32 handled the requests without crashing or dropping the Wi-Fi connection.

### **Control Logic Table**

| Component        | Function          | Communication Type   | Pin / State             |
| :--------------- | :---------------- | :------------------- | :---------------------- |
| **ESP32 SoC**    | Host Server       | Wi-Fi (802.11 b/g/n) | Station Mode            |
| **HTTP Request** | User Action       | GET Method           | URL Endpoint (/H or /L) |
| **LED**          | Physical Actuator | Digital Output       | GPIO 2 (Built-in)       |
| **Router**       | Gateway           | DHCP                 | Local IP Assignment     |

### **Technical Skills Gained**

- **📡 Wireless Stack Management:** Mastered the process of connecting microcontrollers to local networks and managing IP telemetry.
- **🌐 Web-to-Hardware Interfacing:** Understanding how the HTTP request-response cycle can be used to trigger physical electrical signals.
- **🔌 Asynchronous Programming:** Learning to design code that listens for network traffic while simultaneously maintaining the hardware state.
- **🛠️ Full-Stack Prototyping:** Gaining the ability to write HTML/CSS code that lives entirely within a C++ microcontroller environment.

---

## **Task 12: Advanced Soldering & PCB Component Assembly**

### **Description**

The core objective of this task was to master the high-precision skill of **Soldering**, which is essential for transforming a temporary breadboard circuit into a permanent, ruggedized electronic device. This involved using a **Soldering Iron** to melt a filler metal (Solder) onto a **Printed Circuit Board (PCB)** to create a joint that is both electrically conductive and mechanically strong. The task emphasized the physics of thermal conduction, flux activation, and the proper sequence of through-hole component assembly.

### **Detailed Process**

- **Workstation Preparation & Safety:** I began by setting up a safe environment, including a fume extractor and a stable iron stand. I calibrated the soldering iron to approximately **350°C** and "tinned" the tip with a fresh layer of solder to prevent oxidation and ensure the fastest possible heat transfer to the PCB pads.
- **The "Through-Hole" Soldering Cycle:** I developed a disciplined, repeatable process for each joint to ensure consistency and avoid damage to the components:
  1. **Alignment:** I inserted the component leads through the PCB and bent them slightly to hold the part flush against the board.
  2. **Heating:** I applied the iron tip to the junction of the lead and the copper pad for exactly 2 seconds.
  3. **Feeding:** I introduced the solder wire to the _joint_, allowing the flux to clean the surface and the solder to "wick" around the lead.
  4. **Trimming:** Once cooled, I used diagonal cutters to snip the excess lead just above the solder cone.
- **Visual Audit & Troubleshooting:** I inspected every joint under a magnifying glass. I specifically looked for the **"Shiny Concave Cone"** shape. I identified a few "Dry Joints" (caused by moving the lead before the solder cooled) and corrected them by reapplying heat and a small amount of fresh flux.
- **Layered Assembly Strategy:** To keep the board manageable, I followed the "Lowest-Profile-First" rule. I soldered all resistors and diodes first, followed by IC sockets, and finally taller components like electrolytic capacitors and terminal blocks.

### **Technical Skills Gained**

- **🔥 Thermal Precision:** Learning the exact timing required to melt solder without "lifting" the copper pads or overheating sensitive semiconductors.
- **🏗️ Mechanical Reliability:** Understanding how a proper solder fillet provides structural support, preventing electrical failures due to vibration.
- **⚠️ Lab Safety Protocols:** Strict adherence to safety measures regarding lead exposure, high-temperature tools, and chemical fumes.
- **🔍 Hardware Debugging:** Developing the ability to visually diagnose circuit failures caused by solder bridges or cold joints.

---
