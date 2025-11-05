Python (OOP) + C parity + CI + docs.

---

# Project Description — SenseForge

SenseForge is a modular, open-source toolkit that bridges Embedded Systems, Data Science, and Machine Learning.
It provides a complete, hands-on framework for developing and testing Edge AI pipelines — from raw sensor data to real-time intelligence.

Built in Python (for rapid prototyping) and C (for embedded parity), SenseForge lets you:

  * Process and analyze time-series or vibration data

  *  Extract core signal features (RMS, mean, std, ZCR, etc.)

  * Validate embedded DSP algorithms against Python reference code

  * Build, test, and deploy in a reproducible Dockerized environment

  * Learn how to design scalable software for IoT, Avionics, Aerospace, Automotive, and Robotics applications

“From raw sensor waves to meaningful insight — forged at the edge.”

SenseForge bridges Data Science and Embedded Engineering with a  reproducible pipeline for sensor analytics, DSP parity, and Edge AI 
development.

---

# Quickstart (Ubuntu 24.04.3)
unzip week1-sensor-toolkit.zip -d ~/dev
cd ~/dev/week1-sensor-toolkit

# Optional venv
python3 -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt

# Build C lib and run tests
cmake -S . -B build && cmake --build build -j
ctest --test-dir build --output-on-failure

# Python tests (parity)
pytest -q

# Try the CLI on sample data
python -m sensorkit.cli --config configs/default.yaml summarize data/sample_vibration.csv
python -m sensorkit.cli --config configs/default.yaml plot data/sample_vibration.csv --out artifacts/eda.png
python -m sensorkit.cli --config configs/default.yaml features data/sample_vibration.csv --out artifacts/features.csv

---


