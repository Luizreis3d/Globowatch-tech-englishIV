# GloboWatch API Reference

## Introduction
The GloboWatch API provides endpoints to control camera monitoring and retrieve real-time traffic data for Recife. Integrated with a React frontend and backed by two Python services using MongoDB Atlas, the API enables automated camera switching and traffic analysis, reducing operator workload and enhancing situational awareness.

## Authentication
No authentication is required for the current endpoints. Future versions may introduce API keys or OAuth for secure access.

## Endpoints

### 1. Start Camera Monitoring
- **Method**: POST
- **URL**: `http://localhost:5001/start`
- **Description**: Initiates monitoring for a specified camera, enabling real-time data collection.
- **Body**:
  ```json
  {
    "camera": "CAMERA4"
  }
  ```
- **Response**:
  - **Status Code**: 200 OK
  - **Body**:
    ```json
    {
      "status": "success",
      "message": "Monitoring started for CAMERA4"
    }
    ```
- **Example**:
  ```bash
  curl -X POST http://localhost:5001/start -H "Content-Type: application/json" -d '{"camera": "CAMERA4"}'
  ```

### 2. Stop Camera Monitoring
- **Method**: POST
- **URL**: `http://localhost:5001/stop`
- **Description**: Stops monitoring for a specified camera, halting data collection.
- **Body**:
  ```json
  {
    "camera": "CAMERA4"
  }
  ```
- **Response**:
  - **Status Code**: 200 OK
  - **Body**:
    ```json
    {
      "status": "success",
      "message": "Monitoring stopped for CAMERA4"
    }
    ```
- **Example**:
  ```bash
  curl -X POST http://localhost:5001/stop -H "Content-Type: application/json" -d '{"camera": "CAMERA4"}'
  ```

### 3. Get Camera Status
- **Method**: GET
- **URL**: `http://localhost:5001/status`
- **Description**: Retrieves the monitoring status of all cameras, indicating whether each is active or inactive.
- **Parameters**: None
- **Response**:
  - **Status Code**: 200 OK
  - **Body**:
    ```json
    {
      "status": "success",
      "cameras": [
        { "camera": "CAMERA1", "monitoring": true },
        { "camera": "CAMERA4", "monitoring": false }
      ]
    }
    ```
- **Example**:
  ```bash
  curl http://localhost:5001/status
  ```

### 4. Get Traffic Data
- **Method**: GET
- **URL**: `http://localhost:5000/dashboard/dados?rua=TODAS&horas=6`
- **Description**: Retrieves traffic data for all cameras or a specific camera, filtered by the last N hours.
- **Parameters**:
  - `rua` (query, string, required): Street name (e.g., "Boa Viagem") or "TODAS" for all cameras.
  - `horas` (query, integer, required): Number of hours to filter data (e.g., 6).
- **Response**:
  - **Status Code**: 200 OK
  - **Body**:
    ```json
    {
      "status": "success",
      "data": [
        {
          "camera": "CAMERA4",
          "location": "Boa Viagem",
          "trafficLevel": "High",
          "timestamp": "2025-06-08T13:45:00-03:00"
        }
      ]
    }
  ```
- **Example**:
  ```bash
  curl "http://localhost:5000/dashboard/dados?rua=TODAS&horas=6"
  ```

## Error Codes
- **400 Bad Request**: Invalid or missing parameters (e.g., invalid camera name or `horas` not an integer).
  - Example:
    ```json
    { "status": "error", "message": "Invalid camera name" }
    ```
- **404 Not Found**: Camera or data not found for the specified parameters.
  - Example:
    ```json
    { "status": "error", "message": "No data found for the specified camera" }
    ```
- **500 Internal Server Error**: Unexpected server issue (e.g., database connection failure).
  - Example:
    ```json
    { "status": "error", "message": "Internal server error" }
    ```