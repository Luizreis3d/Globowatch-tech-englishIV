# GloboWatch Installation Guide

## Introduction
This guide provides comprehensive instructions to install and run GloboWatch, an application for voice-activated camera switching and real-time traffic monitoring in Recife. With a React frontend and two Python backends integrated with MongoDB Atlas, GloboWatch automates camera operations to reduce operator workload, ensuring a reliable and user-friendly experience.

## Pre-Installation Requirements
### Hardware
- 4GB RAM (8GB recommended)
- 2GHz dual-core CPU
- 1GB free disk space

### Software
- Node.js (v14 or higher)
- npm (v6 or higher) or yarn
- Python 3.8 or higher
- pip (Python package manager)
- Browser with Web Speech API support (e.g., Google Chrome)
- MongoDB Atlas account for backend data storage

### Checklist for Administrators
- [ ] Verify Node.js installation: `node --version`
- [ ] Verify npm installation: `npm --version`
- [ ] Verify Python installation: `python --version`
- [ ] Verify pip installation: `pip --version`
- [ ] Ensure a MongoDB Atlas account is active with a valid connection string
- [ ] Confirm microphone access for voice recognition
- [ ] Ensure internet connectivity for dependency installation and MongoDB Atlas

## Installation Instructions
1. **Clone the Repository**:
   ```bash
   git clone https://github.com/your-username/GloboResidencia.git
   cd GloboResidencia
   ```
2. **Set Up the Frontend**:
   - Navigate to the frontend directory:
     ```bash
     cd globowatch-react
     ```
   - Install dependencies:
     ```bash
     npm install
     npm install xlsx
     ```
   - Create a `.env` file in `globowatch-react` with the following:
     ```plaintext
     REACT_APP_API_URL=http://localhost:5000
     REACT_APP_ANALYTICS_URL=http://localhost:5001
     ```
3. **Set Up the Backends**:
   - Navigate to the first backend directory:
     ```bash
     cd ../BackEndAnalises
     ```
   - Install dependencies:
     ```bash
     pip install -r dependencias.txt
     ```
   - Navigate to the second backend directory:
     ```bash
     cd ../BackEndAPIgeral
     ```
   - Install dependencies:
     ```bash
     pip install -r dependencias.txt
     ```
   - Create a `.env` file in `BackEndAPIgeral` with the following:
     ```plaintext
     MONGODB_URI=your_mongodb_atlas_connection_string
     ```
4. **Start the Application**:
   - In separate terminal windows, start the backends:
     ```bash
     cd BackEndAnalises
     python main.py
     ```
     ```bash
     cd BackEndAPIgeral
     python backend.py
     ```
   - Start the frontend:
     ```bash
     cd globowatch-react
     npm start
     ```
   - Open `http://localhost:3000` in a supported browser.

## Configuration Settings
- **Frontend (`globowatch-react/.env`)**:
  - `REACT_APP_API_URL`: URL of the main backend API (default: `http://localhost:5000`)
  - `REACT_APP_ANALYTICS_URL`: URL of the analytics backend (default: `http://localhost:5001`)
- **Backend (`BackEndAPIgeral/.env`)**:
  - `MONGODB_URI`: MongoDB Atlas connection string (e.g., `mongodb+srv://user:pass@cluster0.mongodb.net/db`)
- **Expected Output**:
  - Frontend loads at `http://localhost:3000` with a login page.
  - Backends respond to API requests (e.g., `http://localhost:5001/status`).

## Post-Installation Checklist
- [ ] Confirm the frontend loads at `http://localhost:3000` and displays the login page (use credentials: admin/admin).
- [ ] Test voice commands (e.g., “Boa Viagem”) to switch cameras.
- [ ] Verify traffic data displays in the dashboard.
- [ ] Check backend connectivity by accessing `http://localhost:5001/status`.
- [ ] Ensure MongoDB Atlas connection is active (no connection errors in backend logs).

## Troubleshooting
- **Error**: "Module not found" in frontend
  - **Solution**: Run `npm install` in `globowatch-react`.
- **Error**: "MongoDB connection failed"
  - **Solution**: Verify `MONGODB_URI` in `BackEndAPIgeral/.env` and ensure MongoDB Atlas is accessible.
- **Error**: "Voice recognition failed"
  - **Solution**: Confirm microphone permissions and use Google Chrome.
- **Error**: "pip install fails"
  - **Solution**: Update pip (`pip install --upgrade pip`) and check `dependencias.txt` for valid packages.
- **Error**: "Port already in use"
  - **Solution**: Stop other processes on ports 3000, 5000, or 5001, or change ports in `.env` files.

## Further Reading
- [React Documentation](https://reactjs.org/)
- [Web Speech API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Speech_API)
- [MongoDB Atlas](https://www.mongodb.com/cloud/atlas)
- [Flask Documentation](https://flask.palletsprojects.com/)
- [Node.js Documentation](https://nodejs.org/en/docs/)