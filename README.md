# Automated Sky View Factor (SVF) and Solar Potential Tool

## Overview
This project develops an **automated tool** for estimating the **Sky View Factor (SVF)** and analyzing **solar potential** using Google Street View imagery.  
It integrates **image stitching, fisheye projection, sky segmentation, SVF calculation, and solar path analysis** into a single workflow.  

The project was developed as part of the **Interdisciplinary Project: "SVF and PV Potential Detector"** at Politecnico di Torino (ICT4SS, 2024–2025).  

## Features
- Retrieve 360° image tiles from **Google Street View API**  
- Stitch panoramas using **OpenCV**  
- Convert panoramas into fisheye projections  
- Perform **sky segmentation** using rule-based + semantic methods  
- Calculate SVF (Steyn, Watson & Johnson methods) with **annular weighting**  
- Overlay **sun path and irradiance analysis** using **pvlib**  
- Backend implemented with **Python (FastAPI, MongoDB, RabbitMQ)**  
- Cross-platform **frontend in Flutter** with map interface  

## Repository Structure
```
Interdisciplinary_project-main/
│── backend/            # FastAPI backend services
│── frontend/           # Flutter-based UI
│── image_process.py    # SVF calculation and segmentation functions
│── requirements.txt    # Python dependencies
│── Report_Team_A_v1.1.pdf  # Project report
│── README.md
```

## Installation

### Backend
1. Create a Python environment (>=3.9).  
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Set up environment variables:
   - `GOOGLE_API_KEY` (for Street View API)  
   - `MONGO_URI` (for MongoDB connection)  
   - `RABBITMQ_URI` (for RabbitMQ broker)

4. Run backend:
   ```bash
   uvicorn main:app --reload
   ```

### Frontend
1. Install [Flutter](https://flutter.dev/).  
2. Navigate to `frontend/` and run:
   ```bash
   flutter pub get
   flutter run
   ```

## Usage
- Select a point on the map in the frontend.  
- Backend retrieves images, stitches, processes fisheye, segments sky, and computes SVF.  
- Results include:
  - SVF value  
  - Segmented fisheye image  
  - Sun path visualization  
  - Irradiance data (EPW or clearsky model)

## Results
- SVF error < **3%** compared to reference tools.  
- Supports **real irradiance (EPW)** and **theoretical clearsky models**.  
- User study (21 participants) confirmed high usability and usefulness.  

## Future Work
- Improve segmentation with **deep learning (U-Net, Mask R-CNN)**  
- Support seasonal SVF/irradiance variations  
- Add mobile app support  
- Integration with **GIS urban analytics tools**  

## Authors
- Sima Shahbazian  
- Sasan Izadseta  
- Asal Malekshahi  
- M. Mahdi Azizian  

**Supervisors**: Prof. Fabio Dovis, Prof. Giacomo Chiesa  

## License
This project is released under the MIT License.

---
📌 Web App Demo: [SVF Calculator](http://polito-svf-calcuator.s3.us-east-1.amazonaws.com/index.html)  
📌 GitHub: [Interdisciplinary Project Repository](https://github.com/isadseta/Interdisciplinary_project)  
