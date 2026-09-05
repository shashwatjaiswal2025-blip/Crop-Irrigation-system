# Crop-Irrigation-system
Pitch:
Traditional farming blindly sprays chemicals over entire fields, wasting money and destroying runoff water. AgriSmart is a zero-waste, autonomous precision agriculture ecosystem. Our Python backend generates a live NPK density map of the farm, identifying exact micro-zones of nutrient depletion. It then wirelessly dispatches our solar-powered, IMU-guided rover to that exact coordinate to dispense a micro-dose of fertilizer—healing the soil autonomously without a single drop of waste.

Idea Objectives:
Zero-Waste Precision Agriculture: Eradicate blanket fertilizing by deploying a rover to dispense micro-doses of liquid nutrients only to specific coordinates experiencing depletion.

Soft-Sensing AI Mapping: Generate a spatial NPK density heatmap by continuously integrating synthesized biochemical data with environmental telemetry to predict soil health across a grid.

Self-Sustaining Energy Loop: Create an autonomous energy architecture where a solar panel actively trickle-charges the primary lithium battery while the rover is in operation.

Untethered Indoor Navigation: Bypass the limitations of indoor GPS by using IMU dead-reckoning for precise rover routing and targeted payload delivery on the judging table.



# Software Stack
Edge Firmware: C/C++ via Arduino IDE/ESP-IDF handling Wi-Fi (WiFi.h), IMU sensor fusion, and hardware PWM for motor speed control.

Data Pipeline & Backend: Python Flask or FastAPI to broker the HTTP requests between the rover and the AI.

Machine Learning & Analytics: Python utilizing scikit-learn for Random Forest classification and scipy.interpolate / matplotlib to generate the spatial density heatmaps.

Frontend Dashboard: Streamlit, React, or standard HTML/JS to render the live NPK heatmap, rover telemetry, and AI targets.

#Master Execution Plan test
Hours 0–6 (Power & Mobility): Solder and tune the solar-to-battery-to-converters power loop. Assemble the chassis, wire the L298N motor driver, and test basic forward/turn movements.

Hours 6–14 (Navigation & Telemetry): Mount the MPU6050 IMU. Write the C/C++ firmware to read the IMU data and translate it into precise 90-degree turns and straight-line driving.

Hours 14–22 (AI & Backend): Build the Python API. Generate the NPK density heatmap using the synthesized coordinate data and establish the Random Forest targeting logic.

Hours 22–28 (Integration): Close the loop. The Python backend selects the "Red Zone" target from the heatmap and wirelessly sends driving coordinates to the ESP32.

Hours 28–32 (Payload Actuation): Mount the water pump and relay. Program the ESP32 to trigger the pump for 3 seconds only when the IMU confirms the rover has reached the target coordinates.

Hours 32–36 (Polish & Pitch): Clean up wire management, finalize the dashboard UI, and rehearse the live physical demo.




# Hardware Stack

ESP32 Development Board
The Power Architecture:
   10000mAh 3.7V Li-ion Battery. Charging: 5V Mini Solar Panel + TP4056 Charging Module
   CA6009 Boost Converter
    LM2596S Buck Converter
The Chassis & Mobility:
2WD Smart Robot Car Chassis (Acrylic frame, wheels, casters).

2x DC Gear Motors.

L298N Motor Driver Module (Bridges ESP32 PWM signals to the 12V motors).

MPU6050 IMU (Inertial Measurement Unit for gyroscope/accelerometer dead-reckoning).

The Payload (Actuation):

5V 1-Channel Optocoupler Relay.

Horizontal Mute Sounds Mini Submersible Pump (DC 3V-5V).

Clear payload tank and silicone drip tubing.
