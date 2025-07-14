# 🎯 YoloBit Extension – AI Camera (Offline Mode)

This repository provides a MicroPython-based extension for working with an **offline AI camera module** using **Yolo:Bit** or similar boards (e.g., ESP32). It supports both **UART-based communication** and **REPL (stdin)** simulation, and is designed for educational and AI-robotics applications.

---

## 📌 Project Overview

This extension helps students and developers:
- Interface with an offline AI camera via UART
- Receive classification results (`class_name;confidence`)
- Integrate camera results into Yolo:Bit Blockly environment
- Build AI-driven interaction projects

---

## 📁 File Structure

camera-AI-offline/

├── camera_ai.py # Main MicroPython library for AI camera

├── config.json # Metadata for extension manager

├── definition.js # Define blocks for Blockly interface

├── toolbox.xml # Structure of blocks inside the Blockly toolbox

├── languages/ # Multilingual support (vi.json, en.json, etc.)

├── poster.png # Visual for documentation or UI

└── README.md # This file

yaml
Sao chép
Chỉnh sửa

---

## 🧠 Features

- Supports both **UART** and **REPL** communication
- Parses AI results in the format: `"class_name;confidence"`
- Provides:
  - `update()` – fetches latest camera data
  - `get_classname()` – returns detected object
  - `get_prediction()` – returns confidence in %
  - `check(class_name, prediction, reversed=False)` – logic check
- Designed for use in block-based programming (Blockly/Yolo:Bit)

---

## 🚀 How to Use

### 1. With UART (hardware connection)
```python
from camera_ai import AI_CAMERA

cam = AI_CAMERA(rx_pin=17, tx_pin=16)
while True:
    cam.update()
    if cam.check('apple', prediction=70):
        print("Apple detected with high confidence!")
2. With REPL (for testing in console)
python
Sao chép
Chỉnh sửa
cam = AI_CAMERA()  # no RX/TX → will read from stdin
🛠 Compatibility
Yolo:Bit (OhStem)

Any MicroPython-compatible board with UART (e.g., ESP32, STM32)

AI Camera module that sends data via UART like: cat;0.89\n

🔗 About
This extension is built to expand the capabilities of Yolo:Bit's block-based platform by enabling AI interaction. It can be used in:

Smart robots

Educational STEM kits

Voice/gesture/object-controlled devices

📬 Contact
Created by: Nguyen Minh
📧 [Nminh59001@gmail.com]
