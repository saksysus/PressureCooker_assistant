# 🍲 PRESSURE COOKER ASSISTANT
### Listen Smarter. Cook Better. Waste Less.

**What if your pressure cooker could tell you when it needs your attention?**

A pressure cooker is part of everyday life in millions of households. Yet, monitoring its whistles still depends entirely on human attention. Missed whistles, delayed intervention and unnecessary heating can mean wasted time and potentially wasted LPG.

<img width="402" height="202" alt="image" src="https://github.com/user-attachments/assets/d5111f90-5cf7-4d8c-9d56-76bd66c7d4f1" />

**Pressure Cooker Assistant** aims to make traditional pressure cookers smarter through intelligent sound monitoring.

Using a digital MEMS microphone and an RP2040-based microcontroller, the system captures and analyses pressure cooker sound patterns to identify meaningful acoustic events, recognize whistle patterns and provide timely alerts to users.


<img width="300" height="269" alt="image" src="https://github.com/user-attachments/assets/c8561e30-cd06-4234-a5f2-54ed08654933" />  <img width="269" height="269" alt="image" src="https://github.com/user-attachments/assets/c3e333eb-29e2-4ca3-89db-47d5a71fbd95" />


This is more than a whistle detector. It is an attempt to bring affordable embedded intelligence to an everyday kitchen appliance—with the potential to support better fuel usage, convenience and more responsible energy consumption.

> **Traditional pressure cooking. Reimagined with intelligence.**

---

## 💡 The Problem

Traditional pressure cookers rely on users to listen for whistles and manually monitor cooking.

This creates a few everyday challenges:

- **Constant monitoring:** Users need to remain attentive to the cooker.
- **Missed whistles:** Kitchen noise or distractions can make whistles difficult to notice.
- **Unnecessary heating:** Delayed intervention may lead to avoidable fuel consumption.
- **Limited intelligence:** Conventional cookers do not provide electronic sound-based alerts or monitoring.

## 🚀 My Solution

Pressure Cooker Assistant is an experimental embedded system designed to monitor pressure cooker acoustics and assist users through sound-based event detection.

The system is being developed around three core capabilities:

1. **Listen:** Capture cooker sounds using the INMP441 digital microphone.
2. **Analyse:** Process audio signals to distinguish relevant acoustic events from background noise.
3. **Alert:** Notify the user when a recognized event requires attention.

The long-term objective is to make pressure cooker monitoring more convenient while exploring opportunities to reduce unnecessary heating.

## ✨ Key Features

| Feature | Description |
|---|---|
| Acoustic Monitoring | Continuously captures sound using a digital MEMS microphone. |
| Whistle Recognition | Aims to identify pressure cooker whistle patterns. |
| Noise Differentiation | Works towards distinguishing cooker sounds from conversations and background noise. |
| Intelligent Alerts | Planned notifications for detected cooking events. |
| Embedded Processing | Designed around the Shrike Lite RP2040 platform. |
| Affordable Design | Explores a compact, accessible solution for conventional pressure cookers. |

*Features under development are distinguished from completed implementation in the progress section below.*

## ⚙️ System Architecture

The proposed system follows this processing pipeline:

```text
       PRESSURE COOKER
              │
              ▼
     INMP441 DIGITAL MIC
              │
              ▼
      I²S AUDIO ACQUISITION
              │
              ▼
      SHRİKE LITE RP2040
              │
              ▼
      SIGNAL PROCESSING
       ├── RMS Analysis
       ├── Noise Analysis
       └── FFT / Frequency Features
              │
              ▼
      ACOUSTIC EVENT DETECTION
              │
              ▼
       USER NOTIFICATION
```

*The architecture represents the planned system. Some processing and notification stages are still under development.*

## 🔧 Hardware & Technology Stack

### Hardware

| Component | Purpose |
|---|---|
| Shrike Lite RP2040 | Main microcontroller |
| INMP441 MEMS Microphone | Digital audio acquisition |
| Connecting wires | Hardware interfacing |

### Software & Technologies

- **Programming:** C++ 
- **Development Environment:** Arduino IDE
- **Microcontroller Platform:** RP2040
- **Communication Protocol:** I²S
- **Digital Signal Processing:** RMS analysis, FFT and acoustic feature extraction (planned)

## 🧪 Development Progress

This project is being developed through iterative hardware testing and data-driven signal analysis.

### Completed

- [x] Shrike Lite RP2040 setup.
- [x] INMP441 microphone interfacing.
- [x] I²S audio acquisition.
- [x] Digital audio sample extraction.
- [x] RMS calculation and smoothing.
- [x] Initial acoustic dataset collection under different sound conditions.

### In Progress / Planned

- [ ] FFT-based frequency-domain analysis.
- [ ] Identification of pressure cooker whistle characteristics.
- [ ] Background noise differentiation.
- [ ] Acoustic event classification.
- [ ] Real-time whistle detection.
- [ ] User notification mechanism.
- [ ] Testing across different cookers and kitchen environments.
- [ ] Controlled evaluation of potential fuel savings.

## 📊 Acoustic Dataset

To understand how the microphone responds to different environments, an initial dataset was collected using the INMP441 microphone and Shrike Lite RP2040.

**Total observations: 3,342 RMS readings**

| Sound Condition | Samples |
|---|---:|
| Quiet Room | 800 |
| Normal Conversation | 1,079 |
| Exhaust Fan ON | 709 |
| Pressure Cooker Whistle | 754 |
| **Total** | **3,342** |

### Dataset Observations

| Sound Condition | Mean Raw RMS |
|---|---:|
| Quiet Room | 5,244.26 |
| Normal Conversation | 30,384.63 |
| Exhaust Fan ON | 34,954.32 |
| Pressure Cooker Whistle | 128,166.94 |

*RMS values are raw digital signal measurements, not calibrated sound-pressure levels or decibels.*

### Download the Dataset

[**INMP441 Acoustic Dataset – Excel Workbook**](Dataset/Cooker_Assistant_INMP441_Dataset.xlsx)

The workbook includes raw readings, smoothed RMS values, summary statistics and documentation.

**Important:** RMS readings alone cannot reliably classify all acoustic events because sound conditions can overlap. The next stage involves capturing waveform data and extracting frequency-domain features for more reliable recognition.

## 🌱 Sustainability Impact

Pressure Cooker Assistant explores how intelligent monitoring of everyday appliances could contribute to more responsible household energy usage.

The project aligns with the following United Nations Sustainable Development Goals:

<p align="center">
  <img src="https://open-sdg.github.io/sdg-translations/assets/img/goals/en/7.png" width="110" alt="SDG 7 - Affordable and Clean Energy"/>
  <img src="https://open-sdg.github.io/sdg-translations/assets/img/goals/en/12.png" width="110" alt="SDG 12 - Responsible Consumption and Production"/>
  <img src="https://open-sdg.github.io/sdg-translations/assets/img/goals/en/13.png" width="110" alt="SDG 13 - Climate Action"/>
</p>

### SDG 7 – Affordable and Clean Energy
Explores ways to reduce avoidable LPG consumption through timely user intervention and intelligent monitoring.

### SDG 12 – Responsible Consumption and Production
Encourages more mindful household energy consumption by helping users monitor cooking events.

### SDG 13 – Climate Action
Potentially contributes to reducing emissions associated with avoidable fuel consumption, subject to actual fuel-saving measurements.

*These are intended contributions, not independently measured environmental outcomes. The project is not affiliated with or endorsed by the United Nations.*

Official SDG resources: [United Nations – Sustainable Development Goals](https://www.un.org/sustainabledevelopment/)

## 🔮 Future Scope

The long-term vision is to evolve Pressure Cooker Assistant into an affordable smart accessory for conventional pressure cookers.

Potential future developments include:

- Machine-learning-based whistle recognition.
- Adaptive acoustic thresholds for different kitchen environments.
- Mobile notifications and a user-friendly interface.
- Cooking-event history and monitoring.
- Testing across different pressure cooker models.
- Controlled experiments to quantify LPG consumption and potential savings.

## 🎯 Our Vision

We believe intelligent technology should not be limited to expensive smart appliances.

By combining embedded systems, digital signal processing and practical engineering, Pressure Cooker Assistant explores how an ordinary household appliance can become more responsive to the people who use it.

**A smarter way to listen. A better way to assist. Making Every Whistle Count.**

---


## 👩‍💻 Project Information

| Category | Details |
|---|---|
| Project | Pressure Cooker Assistant |
| Domain | Embedded Systems, IoT & Digital Signal Processing |
| Microcontroller | Shrike Lite RP2040 |
| Audio Sensor | INMP441 MEMS Microphone |
| Programming Language | C++ |
| Development Environment | Arduino IDE |
| Project Status | Prototype Development |

---

**Disclaimer:** This is an experimental monitoring and alerting system. It does not control the gas supply, replace cooker safety mechanisms, or guarantee cooking completion. Users must continue following the manufacturer's instructions and monitoring requirements.
