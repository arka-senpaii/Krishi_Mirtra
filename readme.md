# Krishi Mitra

## Overview
The IoT-Based Agro Car Web Server acts as a bridge between ESP32, a Machine Learning (ML) model, and Firebase for real-time data storage and retrieval. The web server handles user authentication, real-time sensor data display, data forwarding to the ML model, and results visualization.

## Features
### User Authentication
- Login Page
- Register Page (with location, soil type, and irrigation type)

### Dashboard
- Real-time sensor data from ESP32
- Crop prediction based on ML model response
- Data visualization for farmers

### Data Flow
1. ESP32 sends real-time data to the web server.
2. The web server forwards this data to an ML model endpoint.
3. The ML model responds with crop predictions.
4. The web server displays predictions and sensor data to the user.
5. Data is stored in Firebase for historical analysis.

## Tech Stack
### Hardware
- ESP32
- Soil Moisture Sensor
- DHT11 (Temperature and Humidity Sensor)
- Power Supply (Battery/Adapter)
- FS-i10B (For controlling the IoT car)

### Backend
- **Framework:** Flask (Python) / Django (Python) / Node.js (JavaScript)
- **Database:** Firebase (NoSQL database for real-time storage)
- **ML Integration:** API calls to an external ML model
- **Hosting:** AWS / Heroku / DigitalOcean
- **API Communication:** REST API using FastAPI/Express.js

### Frontend
- **Framework:** React.js / Vue.js
- **UI Design:** Tailwind CSS / Bootstrap
- **Charts & Visualization:** Chart.js / D3.js
- **State Management:** Redux / Vuex

### Communication Protocols
- **ESP32 to Web Server:** HTTP / HTTPS (via REST API)
- **Web Server to ML Model:** HTTP API calls
- **Web Server to Firebase:** Realtime Database API

### Development Tools
- **Code Editor:** VS Code / PyCharm / Sublime Text
- **Version Control:** Git / GitHub
- **API Testing:** Postman
- **Containerization:** Docker (optional for deployment)

## API Endpoints
### ESP32 Data Submission
**Endpoint:** `/api/data`  
**Method:** POST  
**Payload:**
```json
{
    "Temperature": 50.0,
    "Humidity": 20,
    "Soil type": "Clay loam",
    "Irrigation": "Spray",
    "Season": "Zaid"
}
```

### ML Model Prediction Request
**Endpoint:** `https://9f21-34-28-95-124.ngrok-free.app/predict`  
**Method:** POST  
**Payload:**
```json
{
    "Temperature": 50.0,
    "Humidity": 20,
    "Soil type": "Clay loam",
    "Irrigation": "Spray",
    "Season": "Zaid"
}
```

### ML Model Response
**Response Example:**
```json
{
    "All Probabilities": {
        "Arecanut": 0.44,
        "Blackgram": 0.0,
        "Cardamum": 0.24,
        "Cashew": 0.19,
        "Cocoa": 0.61,
        "Coconut": 39.12,
        "Coffee": 0.0,
        "Cotton": 0.0,
        "Ginger": 0.55,
        "Groundnut": 4.53,
        "Paddy": 17.98,
        "Pepper": 0.0,
        "Tea": 36.34
    },
    "Confidence (%)": 39.12,
    "Predicted Crop": "Coconut"
}
```

## Firebase Integration
- Stores real-time sensor data.
- Stores ML predictions.
- Enables historical analysis and visualization.

## System Architecture
1. **ESP32** → Sends data to → **Web Server**
2. **Web Server** → Forwards data to → **ML Model**
3. **ML Model** → Sends predictions to → **Web Server**
4. **Web Server** → Displays predictions on → **Dashboard**
5. **Web Server** → Stores data in → **Firebase**

## Installation and Setup
### 1. Clone the Repository
```sh
git clone https://github.com/your-repository.git](https://github.com/arka-senpaii/Krishi_Mirtra
cd Krishi_Mitra
```

### 2. Install Dependencies
```sh
pip install flask firebase-admin requests
```

### 3. Run the Web Server
```sh
python app.py
```

### 4. Frontend Setup
```sh
cd frontend
npm install
npm start
```

## Future Enhancements
- Implement multi-language support for farmers.
- Add mobile app support.
- Optimize ML model accuracy.

## Contributors
- **Arka Mahajan** - Project Lead
- **Ishika Haldar** - Developers
- **Sayan Mukherjee** - Developers

## License
This project is licensed under the MIT License.

