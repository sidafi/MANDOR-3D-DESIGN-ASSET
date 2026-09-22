MANDOR - 3D Mechanical Designs 🛠️

Welcome to the 3D design repository for the MANDOR (Machine Analytics & Network Diagnostic Operations Router) project.

This repository contains all the mechanical CAD models, enclosures, and mounting brackets required to build the physical prototype of the MANDOR predictive maintenance conveyor system.

⚠️ Disclaimer

Please note that I am not a professional mechanical engineer or a highly experienced 3D designer. These models were created as a functional prototype to bring the MANDOR project to life. As such, the designs might have room for improvement regarding structural optimization, precise tolerances, or standard mechanical practices. Constructive feedback, suggestions, or contributions to improve the designs are highly appreciated!

📖 About the Prototype

MANDOR is an IoT and Edge AI-based predictive maintenance system designed for closed-loop industrial control. The 3D models in this repository represent the physical testing rig, which includes a miniature conveyor belt, a centralized control enclosure, and precise mounting mechanisms for non-contact telemetry sensors (MPU6050 and MLX90614).

The mechanical design is optimized for:

Split Power/Logic Placement: Safe housing for the ESP32 microcontroller, motor drivers, and power regulators.

Interference-Free Sensor Mounting: Strategic placement of vibration and infrared sensors on the DC Motor gearbox without obstructing moving mechanical parts.

Modular Assembly: Easy-to-print and assemble parts for rapid prototyping.

🖼️ 3D Design Gallery

(Replace the placeholder URLs with the actual paths to your images, e.g., images/isometric-view.png)

1. Full Isometric View

This is the complete mechanical assembly of the miniature conveyor machine, showing the integration of the main control panel on the side of the conveyor frame.

2. Control Panel Enclosure (Edge AI & IoT Hub)

The main enclosure box houses the hardware edge computing components. It protects the ESP32 microcontroller and motor driver, and features an external mount for the OLED physical interface.

3. Sensor Mounting on DC Motor Gearbox

Close-up view of the main drive area powered by the DC gearbox motor. It highlights the strategic placement of the vibration sensor directly on the motor casing and the infrared temperature sensor aimed at the motor body for accurate, non-contact telemetry.

📂 File Structure

/Assemblies/ - Complete assembled 3D models (e.g., STEP, IGES files).

/Parts/ - Individual components (Conveyor frame, brackets, rollers).

/3D_Printing/ - Ready-to-print STL files for the enclosure and sensor mounts.

/Renders/ - High-quality rendered images of the design.

⚙️ Recommended Manufacturing

Enclosures & Brackets: 3D Printed (PLA, PETG, or ABS/ASA for higher temperature resistance near the motor).

Frame: Standard aluminum extrusions (e.g., 2020 v-slot) as per the CAD dimensions.

👥 Authors

Team RESTU MAMAH PAPAH

Bintang Shobri Al Chakim

Ilham Nur Fiqri

Muhammad Daffi Izzuddin
(Politeknik Manufaktur Bandung)
