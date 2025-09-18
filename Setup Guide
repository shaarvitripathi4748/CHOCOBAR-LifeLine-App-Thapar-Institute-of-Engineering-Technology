# LifeLine - Development Environment Setup Guide

This guide outlines the process to set up the development environment for the LifeLine backend AI server and the Unity client. This is a **hypothetical setup** for the Phase 2 proof-of-concept architecture.

## Prerequisites

Before you begin, ensure you have the following installed on your system:

*   **Python 3.9+** (for the backend server)
*   **pip** (Python package manager)
*   **Unity Hub & Unity Editor 2022.3 LTS** (for the mobile client)
*   **Git** (for version control)
*   **4GB+ RAM** (recommended)

## Part 1: Backend AI Server Setup

The backend is a Python-based FastAPI server that handles heavy AI processing requests from the mobile client.

### 1. Clone the Repository
```bash
git clone https://github.com/SHAARVITRIPATHI4748/CHOCOBAR-LifeLine-App-Thapar-Institute-of-Engineering-Technology.git

cd CHOCOBAR-LifeLine-App-Thapar-Institute-of-Engineering-Technology

2. Create and Activate a Virtual Environment

It is recommended to isolate your Python dependencies.

# Create the environment
python -m venv venv

# Activate it
# On macOS/Linux:
source venv/bin/activate
# On Windows:
.\venv\Scripts\activate

3. Install Python Dependencies

Install all required packages from the requirements.txt file.

pip install -r requirements.txt

4. Configure Environment Variables

Create a .env file in the root directory to store sensitive configuration like API keys. 

Note: This file should be added to .gitignore to keep secrets out of version control.

# .env
HUGGING_FACE_API_KEY=your_hugging_face_key_here
DATABASE_URL=sqlite:///./lifeline.db

5. Run the Development Server

Start the FastAPI server. The --reload flag enables auto-reload on code changes.

uvicorn app.main:app --reload --host 0.0.0.0 --port 8000

The server will start. You can interact with the automatic API documentation at 
http://localhost:8000/docs.

6. Run the ML Model Service

In a separate terminal, activate the virtual environment and run any additional model serving scripts.

python ml_service/model_server.py

Part 2: Unity Mobile Client Setup

The client is a separate Unity project that handles the user interface and sensor data collection.

1. Open the Project

Open Unity Hub.

Click "Open" and navigate to the /LifeLineUnity folder within the cloned repository.

The Unity Editor will open with the project.

2. Configure Build Settings

Go to File > Build Settings.

Choose your target platform (Android or iOS).

Ensure all necessary scenes are added to the build.

3. Configure API Endpoint

In the Unity Project window, navigate to Assets/Scripts/.

Open the Config.cs script.

Update the apiBaseUrl variable to point to your running FastAPI server (e.g., http://localhost:8000 or your network IP for device testing).

4. Build and Deploy

Connect your mobile device or start an emulator.

Click "Build And Run" in the Build Settings window.

The application will be installed and launched on your device.

Testing the Workflow

Start the Backend: Ensure your FastAPI server is running on http://localhost:8000.

Start the Client: Open the built LifeLine app on your mobile device.

Simulate Data: The Unity app will collect mock sensor data and send HTTP requests (e.g., POST /api/analyze-sensor-data) to the backend.

View Results: The server will process the data with its AI models and return a JSON response, which the app will use to trigger alerts or voice guidance.

Note: This setup guide describes the intended development process for a full implementation, as described in the project's architecture.

