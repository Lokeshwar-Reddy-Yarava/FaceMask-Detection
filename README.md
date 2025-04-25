# Face Mask Detection

---

## 🧠 Project Overview

This project focuses on enhancing safety during the COVID-19 pandemic by detecting whether individuals are wearing face masks and controlling door access accordingly.  
When a mask is detected on the user's face, the door automatically opens; otherwise, entry is denied.

✅ Real-time **Face Detection**  
✅ **Mask vs No Mask** Classification  
✅ **Door Automation** integrated via **ThingSpeak** and hardware simulation.

---

## 🚀 Techniques and Tools

- **Python 3.8+**
- **TensorFlow / Keras**
- **OpenCV** (for real-time webcam feed)
- **MTCNN** (for face detection)
- **CNN Model** (for mask classification)
- **Google Colab** (for model training & testing)
- **ThingSpeak API** (to send detection results to hardware)
- **Arduino UNO + ESP8266 WiFi** for door automation

---

## 📁 Project Structure

```
FaceMask-Door-Detection/
├── hardware/
│   ├── circuit_diagram.png
│   ├── simulation_code.ino    # Arduino + ESP8266 simulation code
├── notebook/
│   └── Team_Lokesh_face_mask_detection.ipynb
├── dataset/
├── test/
│   ├── m/     # masked images
│   └── nm/    # non-masked images
├── train/
│   ├── m/     # masked images
│   └── nm/    # non-masked images
├── README.md

```

---

## ⚙️ How it Works

1. **Face Detection**:  
   MTCNN is used to detect faces from a live webcam feed.

2. **Mask Classification**:  
   A Convolutional Neural Network (CNN) is trained to classify faces as **masked** or **unmasked**.

3. **Cloud Communication**:  
   Based on prediction, the result is sent to **ThingSpeak**, which simulates opening/closing the door.

4. **Door Automation**:  
   - If a mask is detected ➔ Door Opens ➔ LCD shows "Masked: Entry Granted"
   - No mask ➔ Door remains closed ➔ LCD shows "No Mask: Entry Denied"

---

## 🔧 Arduino Hardware Code

The Arduino UNO connects to the ThingSpeak cloud API to fetch the latest mask detection status.  
- If a mask is detected (`'m'`): Motor turns ON (door opens), LED OFF, LCD shows "You are masked".
- If no mask detected (`'n'`): Motor OFF (door closed), LED ON, LCD shows "No mask no entry".
- If no scan detected: Shows "Please scan yourself".

**Simulation code** is provided in [`hardware/arduino_simulation.ino`](hardware/arduino_simulation.ino).

---

## 📈 Dataset Details

- Two classes: **With Mask** and **Without Mask**
- Image augmentation used during training
- Balanced and preprocessed dataset

---

## 🛠️ Hardware Components (for Deployment)

- Arduino UNO
- Servo Motor (to simulate door lock)
- ESP8266 Wi-Fi Module (for ThingSpeak connectivity)
- LCD Display (16x2)
- Red LED
- Power supply (Battery or USB)

---

## 📚 References

- Loey, Mohamed, et al., "Face Mask Detection in the era of the COVID-19 pandemic", *Measurement Journal* (2021)
- OpenCV Python Documentation
- TensorFlow/Keras Documentation

---

## 🧠 Future Improvements

- Extend detection to multiple faces simultaneously
- Improve classification accuracy with more real-world data
- Direct ESP32 integration for faster operations
- Add temperature sensor before entry as an additional health check

---

## 🤝 Acknowledgements

This project was submitted as a part of Bachelor of Engineering (BE) curriculum under the Department of Computer Science & Engineering, MVJ College of Engineering, affiliated to VTU University.

---
