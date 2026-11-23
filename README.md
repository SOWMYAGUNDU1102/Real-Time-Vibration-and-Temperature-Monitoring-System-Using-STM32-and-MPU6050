
# Real-Time Vibration and Temperature Monitoring System Using STM32 and MPU6050

## Overview

This project presents an embedded predictive maintenance system that combines vibration and temperature monitoring with machine learning-based condition classification.

The system uses an STM32 ARM Cortex-M microcontroller, MPU6050 MEMS accelerometer, and an analog temperature sensor to continuously monitor machine operating conditions.

Sensor measurements are processed to extract statistical features, which are used to distinguish between normal and abnormal machine behavior.

A lightweight machine learning approach is explored for real-time condition monitoring using TinyML.

## Project Objectives

- Develop a low-cost predictive maintenance system.
- Monitor vibration and temperature simultaneously.
- Acquire tri-axial acceleration data using MPU6050.
- Perform statistical feature extraction.
- Generate structured sensor datasets using Python.
- Compare machine learning classification algorithms.
- Explore TinyML deployment on STM32.
- Detect abnormal operating conditions with low latency.

## Hardware Architecture

| Component | Purpose |
|---|---|
| STM32 Microcontroller | Main processing unit |
| MPU6050 | Three-axis vibration measurement |
| Analog Temperature Sensor | Thermal monitoring |
| LEDs | Normal and fault indication |
| UART | Serial communication and data logging |

## Technologies Used

**Programming:** Python, Embedded C

**Machine Learning:** Scikit-learn, Random Forest, SVM, Logistic Regression

**Embedded Systems:** STM32, ARM Cortex-M

**Communication:** I2C, UART

**Development Tools:** STM32CubeIDE, STM32CubeMX, Python, TensorFlow Lite Micro

## System Workflow

The project follows the following processing pipeline:

1. Sensor data acquisition.
2. Signal preprocessing.
3. Dataset generation.
4. Feature extraction.
5. Machine learning model training.
6. Model comparison.
7. Embedded inference.
8. Fault indication.

## Dataset Generation

Real-time sensor measurements are collected using the STM32 microcontroller.

A Python-based serial interface is used to capture and organize the sensor measurements into CSV format.

The recorded parameters include:

- Raw ADC values
- Voltage measurements
- Temperature readings
- Vibration detection status
- Timestamp

## Data Preprocessing

The collected sensor data is prepared for machine learning through:

- Removal of insufficient or noisy samples.
- Normalization of temperature and voltage measurements.
- Segmentation into predefined time windows.
- Preparation of feature vectors.
- Assignment of operating-condition labels.

## Feature Engineering

Statistical features are extracted from vibration signals.

| Feature | Description |
|---|---|
| Mean | Average signal value |
| RMS | Effective vibration magnitude |
| Standard Deviation | Signal variability |
| Peak-to-Peak | Difference between maximum and minimum values |
| Temperature Deviation | Change from baseline temperature |
| Temperature Change Rate | Rate of thermal variation |

These features help characterize machine operating conditions.

## Machine Learning Models

The following supervised classification algorithms were evaluated:

1. Random Forest
2. Support Vector Machine (SVM)
3. Logistic Regression

The models were compared using classification metrics.

## Experimental Results

Reported model performance:

| Model | Accuracy | Precision | Recall | F1-Score |
|---|---:|---:|---:|---:|
| Random Forest | 83.3% | 83.3% | 100% | 88.9% |
| SVM | 83.3% | 66.7% | 66.7% | 66.7% |
| Logistic Regression | 72.2% | 50.0% | 66.7% | 55.6% |

Random Forest achieved the highest reported F1-score and recall among the evaluated models.

These results are from the experimental evaluation described in the research paper. They should not be interpreted as a benchmark on an independent production dataset.

## TinyML Deployment

The selected machine learning approach is prepared for embedded implementation.

The proposed deployment workflow includes:

1. Train the model using extracted sensor features.
2. Convert the trained model into a lightweight representation.
3. Integrate the model into STM32 firmware.
4. Acquire sensor readings continuously.
5. Extract features from incoming measurements.
6. Perform local condition classification.
7. Indicate the detected operating condition through LEDs.

TensorFlow Lite Micro is used as the embedded inference framework.

## Real-Time Monitoring

The system identifies two primary operating conditions:

**Normal Condition**
- Stable vibration measurements.
- Temperature within the expected operating range.
- Green LED indication.

**Fault Condition**
- Abnormal vibration measurements.
- Excessive temperature rise.
- Red LED indication.

UART communication provides sensor readings and diagnostic information through a serial terminal.

## Applications

- Industrial motor monitoring
- Predictive maintenance
- Rotating machinery diagnostics
- Embedded condition monitoring
- TinyML-based fault classification

## Future Improvements

- Expand the experimental dataset.
- Investigate frequency-domain feature extraction.
- Evaluate additional ML algorithms.
- Optimize inference time and memory utilization.
- Investigate model generalization under different operating conditions.

## Research Publication

Real-Time Vibration and Temperature Monitoring System Using STM32 and MPU6050.

DOI: https://doi.org/10.1109/ICICCS67901.2026.11502839

## Author

**Gundu Naga Sowmya**

M.Tech – Embedded Systems  
Amrita Vishwa Vidyapeetham, Bengaluru

GitHub: [SOWMYAGUNDU1102](https://github.com/SOWMYAGUNDU1102)
