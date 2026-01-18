# smart_plant_monitor

Raspberry Pi server application for the solar-powered smart plant management system.  
This software receives sensor data from `smart_plant_ctrl`, stores logs, visualizes data,  
and can also **send control commands back via UDP** for remote configuration.

## Features
- 📡 Receives sensor data via UDP sockets
- 🗂️ Parses and logs soil moisture, temperature, humidity, pressure, light, and power data
- 📊 Web dashboard with interactive charts using **Flask + Plotly + Bootstrap**
- 🏡 Local-first design (no cloud dependency, runs on home server)
- 🔧 Simple setup on Raspberry Pi
- 🔄 **Two-way communication**: send configuration/commands to `smart_plant_ctrl` via UDP for remote control

## Remote Control (Two-way Communication)
The server can send configuration values (e.g., soil moisture threshold, pump runtime, reporting interval)  
to the AtomS3 Lite running `smart_plant_ctrl`.

- Protocol: UDP  
- Example commands:
  - Set soil moisture threshold  
  - Change reporting interval (e.g., every 5 minutes)  
  - Manually trigger pump ON/OFF  

This enables **remote irrigation control and system tuning** without physical access.

## Requirements
- Raspberry Pi 4B (or similar, running Linux)
- Python 3.9+
- Flask
- Plotly
- Bootstrap
- SQLite (optional, for persistent logging)

## Installation
```bash
git clone https://github.com/hino581/smart_plant_monitor.git
cd smart_plant_monitor
python -m venv pyvenv
(macOS) . pyvenv/bin/activate
(windows) "pyvenv/Scripts/activate.bat"
pip install -r requirements.txt
python run.py
```
