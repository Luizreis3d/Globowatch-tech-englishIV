## Introduction

GloboWatch is an innovative application designed to streamline traffic monitoring in Recife by automating camera switching through voice commands and providing real-time traffic data. Built with a React frontend and two Python backends integrated with MongoDB Atlas, it reduces operator workload, enhances safety with a redundant system, and aligns with Grupo Globo’s visual identity for a user-friendly desktop experience.

## Team
- **Brendo Garcia**: Backend development, testing and repository management
- **Leandro Marques**: Database development, testing and repository management
- **Luiz Reis**: Documentation and presentation preparation
- **Frontend development by others from the original team**

*Note*: Our team consists of three members due to project constraints. Tasks were efficiently divided to meet all requirements, with each member taking on multiple roles.

## Problem and Solution
**Problem**: Manual camera switching in traffic monitoring systems overloads operators, who juggle multiple tasks simultaneously, leading to inefficiencies and potential errors.

**Solution**: GloboWatch automates camera switching using voice commands via the Web Speech API, significantly reducing operator workload. It also provides real-time traffic data from MongoDB Atlas, enhancing situational awareness and decision-making.

## Features
- **Voice-Activated Camera Switching**: Switch cameras using voice commands (e.g., “Boa Viagem”) for hands-free operation.
- **Real-Time Traffic Data**: Display traffic conditions for Recife, sourced from MongoDB Atlas.
- **Redundant System**: Ensures reliability and safety through backup mechanisms.
- **User Login**: Secure access with credentials (e.g., admin/admin).
- **Camera Scheduling**: Schedule camera switches with Excel import (.xlsx) and LocalStorage persistence.
- **Dashboard**: Centralized interface with camera controls, event logs, and traffic notifications.
- **Camera Stream Preview**: View and maximize camera feeds for detailed monitoring.

## Prerequisites
- Node.js (v14 or higher)
- npm or yarn
- Python 3.8 or higher
- pip (Python package manager)
- Browser with Web Speech API support (e.g., Chrome)
- MongoDB Atlas account for backend data storage

## Getting Started
1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/GloboResidencia.git
   cd GloboResidencia
   ```
2. Set up the frontend:
   ```bash
   cd globowatch-react
   npm install
   npm install xlsx
   npm start
   ```
3. Set up the backends:
   ```bash
   cd ../BackEndAnalises
   pip install -r dependencias.txt
   python main.py
   cd ../BackEndAPIgeral
   pip install -r dependencias.txt
   python backend.py
   ```
4. Open `http://localhost:3000` in your browser and log in with credentials (e.g., admin/admin).

## Documentation
- [Installation Guide](./docs/installation.md)
- [API Reference](./docs/api-reference.md)
- [Contribution Guide](./docs/contributing.md)

## License
This project is licensed under the MIT License.
