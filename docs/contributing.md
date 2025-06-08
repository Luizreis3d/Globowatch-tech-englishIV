# Contributing to GloboWatch

## Introduction
Thank you for your interest in contributing to GloboWatch! This application automates camera switching through voice commands and provides real-time traffic data for Recife, using a React frontend and Python backends with MongoDB Atlas. Your contributions can enhance functionality, improve usability, or fix issues, making traffic monitoring more efficient and reliable.

## Prerequisites
To contribute, you should be familiar with:
- **Technologies**: React, Node.js, Python, Flask, MongoDB Atlas, Web Speech API, REST APIs.
- **Tools**: Git, GitHub, npm/yarn, pip, Docker (optional).
- **Setup**: Follow the [Installation Guide](installation.md) to configure the development environment.
- **Knowledge**: JavaScript/TypeScript (React), Python, Git workflows, API testing (e.g., Postman or curl).

## How to Contribute
1. **Fork the Repository**:
   - Navigate to the repository: `https://github.com/your-username/GloboResidencia`.
   - Click "Fork" to create a copy in your GitHub account.
2. **Clone Your Fork**:
   ```bash
   git clone https://github.com/your-username/GloboResidencia.git
   cd GloboResidencia
   ```
3. **Create a New Branch**:
   - Use a descriptive name for your feature or fix:
     ```bash
     git checkout -b feature/your-feature-name
     ```
4. **Make Changes**:
   - Follow the coding guidelines below.
   - Test changes locally (e.g., run `npm start` for frontend, `python backend.py` for backends).
5. **Commit Your Changes**:
   - Write clear, concise commit messages:
     ```bash
     git commit -m "Add feature: describe your change"
     ```
6. **Push to Your Fork**:
   ```bash
   git push origin feature/your-feature-name
   ```
7. **Open a Pull Request**:
   - Go to the original repository on GitHub.
   - Click "New Pull Request" and select your branch.
   - Provide a detailed description of your changes, referencing any related issues.

## Coding Guidelines
- **Frontend (React)**:
  - Use 2-space indentation.
  - Follow React functional components and hooks.
  - Name files in `camelCase` (e.g., `cameraSwitch.js`).
  - Add comments for complex logic.
- **Backend (Python)**:
  - Follow PEP 8 style guidelines.
  - Use 4-space indentation.
  - Name files in `snake_case` (e.g., `camera_controller.py`).
  - Include docstrings for functions and modules.
- **Commits**:
  - Use descriptive messages (e.g., "Fix bug in /status endpoint response").
  - Keep commits focused and atomic.
- **Testing**:
  - Test API endpoints locally (e.g., `curl http://localhost:5001/status`).
  - Ensure voice commands work in Chrome (Web Speech API).
  - Verify MongoDB Atlas connectivity.

## Reporting Issues
- Open an issue on GitHub: `https://github.com/your-username/GloboResidencia/issues`.
- Include:
  - A clear title (e.g., "Error in /dashboard/dados endpoint").
  - Steps to reproduce the issue.
  - Expected and actual behavior.
  - Screenshots or logs, if applicable.

## Contact
For questions or support, reach out via:
- **GitHub Issues**: Preferred for technical discussions.
- **Email**: Contact the team at `globo.watch.team@example.com` (placeholder; update as needed).

## Acknowledgments
We appreciate your contributions to making GloboWatch a more robust and efficient tool for traffic monitoring in Recife!