# HomeConnect  

**HomeConnect** transforms traditional appliances into smart devices, offering integrated control via a user-friendly website. Instead of relying on smart appliances, this system makes the *switch* smart, enabling it to control all functions seamlessly.  

---

## Key Features  

- **Real-Time Updates**: Monitor live sensor values such as temperature, humidity, and light intensity for accurate control.  
- **Dual Control Modes**:  
  - **Automatic Mode**: Set thresholds for automated responses to sensor data.  
  - **Manual Mode**: Intuitively control devices using the web interface.  
- **Adjustable Thresholds**: Personalize automation by setting custom thresholds for comfort and convenience.  
- **Multi-Device Monitoring**: Track data such as temperature, humidity, heat index, soil moisture, and appliance status from a single interface.  
- **Secure Access Control**: Assign unique IDs and passwords for restricted device access.  
- **Multi-User Access**: Enable multiple authorized users to control devices over Wi-Fi.  
- **User-Friendly Website Interface**: Designed for simplicity, making smart home management accessible to everyone.  
- **Gas Leak Alerts**: Instant notifications on gas leaks to ensure safety.  
- **Organized Parent-Child Communication**: Efficient communication between microcontrollers ensures smooth operations.  
- **Timers**: Monitor the active duration of components for enhanced safety.  
- **Laundry Notifications**: Detect washing machine activity and manage it efficiently.  
- **Security Features**: Use light sensors to detect intrusions or unusual activities.  
- **Weather Adaptation**: Adjust indoor temperature based on outdoor weather conditions.  
- **Cost-Effective Solution**: Reduce setup complexity and cost by smartening traditional appliances.  
- **Centralized Control**: Manage all appliances through a single website interface.  

---

## System Architecture  

### Parent Controller  

#### **Client Interface**  
The client serves as the control hub, offering real-time monitoring and device management.  

- **Key Functions**:  
  - Displays sensor data:  
    - Temperature and humidity.  
    - Soil moisture levels.  
    - Gas leak alerts.  
    - Appliance statuses (e.g., lights, fans, heaters).  
  - Weather updates for user reference.  
  - Provides manual override options and allows threshold customization for automation.  

#### **ESP32 Microcontroller (Parent Node)**  
The central processor managing sensor data and automation rules.  

- **Primary Functions**:  
  - Processes sensor inputs and adjusts appliance states accordingly:  
    - Fan speed based on temperature and humidity.  
    - Water pump activation based on soil moisture.  
  - Alerts users to gas leaks via the MQ-5 gas sensor.  
  - Communicates real-time updates to the client interface.  

#### Sensors and Devices  

1. **DHT11 (Temperature & Humidity Sensor)**  
   - Monitors temperature and humidity.  
   - Adjusts fan speed or triggers devices based on predefined thresholds.  

2. **Soil Moisture Sensor**  
   - Determines soil conditions for irrigation needs.  
   - Activates the water pump if moisture levels are low.  

3. **MQ-5 Gas Sensor**  
   - Detects gas leaks and sends alerts for immediate action.  

4. **LDR (Light Dependent Resistor)** 
   - Measures light intesity of room.
   - Turn light on/off according to threshold light intensity of room. 

---

### Child Controller  

Handle auxiliary tasks like laundry monitoring and home security.  

#### Sensors and Devices 

1. **Vibration Sensor**  
   - Detects washing machine activity (active or idle).  

2. **LDR (Light Dependent Resistor)**  
   - Detects changes in light intensity for intrusion or unusual activity detection.  

#### **ESP32 Microcontroller (Child Node)**  
Processes input data and communicates with the parent node.  

- **Key Tasks**:  
  - **Laundry Monitoring**: Tracks washing machine status and reports activity.  
  - **Security Monitoring**: Alerts the system to potential intrusions.  

#### **Communication**  
- Child ESP32 communicates with the parent ESP32 wirelessly, centralizing decisions and updates.  

---

## How to Use  

1. **Setup ESP32**  
   - Install the necessary libraries for importing modules in `main.ino`. Edit the SSID and password in the file to match your device, which will enable the launch of the web interface. Finally, upload the updated `main.ino` file to the ESP32 microcontroller.  

2. **Hardware Configuration**  
   - Make proper connections as per the provided `circuit.pdf`.  

3. **Launch the Website**  
   - Access the web interface using the IP address displayed after running `main.ino` in the Arduino IDE. This IP address is accessible only on the device with the specified SSID (as defined in `main.ino`) and devices connected to the main device, ensuring enhanced security.  

4. **Control Devices**  
   - Use the website to monitor sensor data and control devices in real time.  

---

## Benefits  

- Cost-effective and straightforward to implement.  
- Reduces reliance on expensive smart appliances.  
- Offers centralized control for all household appliances.  
- Enhances safety and convenience with features like gas leak alerts and laundry notifications.  

---  

 


