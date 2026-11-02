# Cooker Assistant – INMP441 Audio Dataset

An experimental audio-intensity dataset collected using the **INMP441 MEMS microphone** and **Shrike Lite RP2040** for the development of an intelligent Cooker Assistant system.

This dataset captures RMS (Root Mean Square) variations across different real-world sound conditions to support acoustic analysis and future sound-event classification.
<img width="1564" height="1600" alt="WhatsApp Image 2026-11-02 at 9 23 46 PM" src="https://github.com/user-attachments/assets/910ec1f4-c213-470c-b106-efc2c478e931" />


## Project Overview

The Cooker Assistant aims to use acoustic sensing to identify relevant cooking-related sound patterns, particularly pressure cooker whistles, while distinguishing them from everyday background sounds.

As the first stage of development, an INMP441 digital microphone was interfaced with the Shrike Lite RP2040 to capture audio samples and calculate RMS values.

## Hardware & Configuration

| Parameter | Configuration |
|---|---|
| Microcontroller | Shrike Lite RP2040 |
| Microphone | INMP441 MEMS Digital Microphone |
| Communication | I²S |
| Programming Environment | Arduino IDE (C++) |
| Sampling Frequency | 16,000 Hz |
| Buffer Size | 256 samples |
| Audio Processing | RMS Calculation |
| Data Format | Excel (.xlsx) |

## Dataset Overview

The dataset contains **3,342 experimentally recorded RMS samples** across four sound conditions.

| Sound Condition | Number of Samples |
|---|---:|
| Quiet Room | 800 |
| Normal Conversation | 1,079 |
| Exhaust Fan ON | 709 |
| Pressure Cooker Whistle | 754 |
| **Total** | **3,342** |

*Water-boiling readings have been intentionally excluded.*

## Dataset Structure

The Excel workbook contains three sheets:

### 1. Raw Dataset
Contains individual experimental readings.

- Sample ID
- Sound Condition
- Raw RMS
- Smooth RMS
- Units

### 2. Summary
Provides statistical information for each sound condition:

- Sample count
- Mean RMS
- Median RMS
- Minimum RMS
- Maximum RMS
- Mean Smooth RMS

### 3. README
Documents the experimental setup, dataset parameters, definitions and limitations.

## Understanding the Features

**Raw RMS:** Represents the signal's amplitude over the sampling window after DC component removal.

**Smooth RMS:** A smoothed version of the RMS signal used to reduce rapid fluctuations and observe changes in sound intensity.

These values are expressed in raw digital sample units, not calibrated sound-pressure levels (dB).

## Experimental Observations

- Quiet environments generally produce lower RMS values.
- Human conversation produces varying RMS levels.
- Exhaust fans generate sustained background acoustic activity.
- Pressure cooker whistles produce substantially higher RMS values in the recorded experiments.

These observations provide an initial basis for acoustic feature analysis.

**Important:** RMS alone cannot reliably distinguish a pressure cooker whistle from other loud sounds. Additional frequency-domain features will be investigated.

## Future Development

The next stages of the project include:

1. **FFT Analysis:** Identify dominant frequencies and spectral patterns.
2. **Feature Extraction:** Calculate spectral energy and other acoustic features.
3. **Dataset Expansion:** Collect additional labelled audio recordings under controlled conditions.
4. **Sound Classification:** Investigate distinguishing cooker whistles from conversation and background noise.
5. **Embedded Intelligence:** Develop an efficient audio-classification pipeline for the RP2040 platform.


## Important Notes

- All readings are based on actual experimental data.
- No synthetic samples have been added.
- RMS values are not calibrated dB measurements.
- The dataset is intended for preliminary acoustic analysis, not as a validated machine-learning classification dataset.

## Project Status

**Current Stage:** INMP441 Microphone Integration & RMS-Based Acoustic Data Collection.

**Next Milestone:** FFT-Based Frequency Analysis.

---

*Part of the Cooker Assistant project – developing intelligent acoustic sensing for smarter cooking experiences.*
