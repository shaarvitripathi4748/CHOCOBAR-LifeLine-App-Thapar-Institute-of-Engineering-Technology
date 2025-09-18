# CHOCOBAR-LifeLine-App-Thapar-Institute-of-Engineering-Technology
LifeLine App
AI-powered healthcare & accessibility companion app
Submissions:                                         (Note: Participants will add their video link here after recording.)
Table of Contents

The Problem
Our Solution - LifeLine

On-Device Continuous Monitoring
On-Device AI Symptom Detection & Response
Blind Assistance


Technical Architecture
Project Scope & Future Work
Setup and Installation (Hypothetical)
Usage (Hypothetical)
Team
License

The Problem
Every day, millions of people worldwide navigate life with chronic medical conditions—epilepsy, cardiac disorders, anxiety disorders, and Parkinson's disease. These conditions don't just affect the patients; they create ripples of concern throughout entire families.
The crisis is multi-faceted:

Memory Gaps During Episodes: When a medical episode strikes, patients often experience memory loss or confusion, unable to accurately recall what exactly happened. This critical information gap hampers accurate diagnosis and treatment optimization to an extent.
Helpless Bystanders: Imagine witnessing someone having a seizure or cardiac event. Most people freeze, not knowing whether to call for help, how to position the person, or what immediate actions could save a life. These precious seconds of indecision can mean the difference between recovery and tragedy.
Family Anxiety: Families live in perpetual worry—"What if they have an attack when alone? What if nobody around knows their condition or medication needs?" This constant stress affects mental health and quality of life for entire households.
Accessibility Challenges: Additionally, over 285 million visually impaired individuals worldwide struggle with daily tasks that sighted people take for granted—finding personal belongings, navigating spaces, or identifying objects in their environment.

The current reality is stark: There exists no comprehensive, intelligent solution that combines real-time health monitoring, emergency response guidance, and accessibility features—all while preserving user privacy and operating independently of constant internet connectivity.
Our Solution - LifeLine
LifeLine is a revolutionary AI-powered mobile application that transforms any smartphone into a personal healthcare guardian and accessibility assistant. By leveraging cutting-edge on-device AI and the powerful sensors already built into modern smartphones, LifeLine provides continuous, intelligent support without compromising privacy or requiring constant connectivity.
1. On-Device Continuous Monitoring
LifeLine runs efficiently in the background, turning your smartphone into a sophisticated medical monitoring device:

Accelerometer/Gyroscope Integration: Continuously analyzes movement patterns to detect falls, unusual tremors, convulsions, or seizure-like motor activity. Our AI distinguishes between normal daily activities and potential medical emergencies with remarkable accuracy.
Ambient Sound Analysis: The microphone listens for acoustic signatures of distress—gasping, choking, irregular breathing patterns, or verbal cries for help—while respecting privacy by processing all audio locally.
Visual Monitoring (Optional): When activated, the camera can observe physical signs like facial expressions or body positioning, adding another layer of detection capability.

2. On-Device AI Symptom Detection & Response
When LifeLine detects a potential medical event, it springs into action with intelligent, personalized responses:

Instant AI Analysis: Our lightweight, on-device machine learning model—trained on extensive medical datasets—analyzes sensor data in real-time, identifying early warning signs and classifying the type of episode occurring.
Voice-First Aid Guidance: The app immediately activates a calm, clear voice guidance system that:

Provides reassurance to the patient: "You're having an episode. Help is on the way. Try to breathe slowly."
Instructs nearby bystanders step-by-step: "Please help them lie down on their side. Loosen any tight clothing around their neck. Do not put anything in their mouth."


Personalized Medical Instructions: Based on pre-loaded patient profiles, LifeLine provides specific guidance:

"This person has epilepsy. Please administer 1 tablet of Clonazepam from the red medical pouch in their bag's front pocket."
"They have a cardiac condition. Help them take their nitroglycerin tablet under their tongue."


Automatic Episode Documentation: The app begins recording audio and sensor data, creating a detailed log of the episode for medical professionals to review later, invaluable for treatment optimization.

3. Blind Assistance
LifeLine extends its AI capabilities to serve the visually impaired community:

Intelligent Object Finding: Users can ask natural language queries like "Where are my reading glasses?" or "Find my black watch." The app uses computer vision to scan the environment and provides voice-guided directions.
Scene Description: The AI describes the user's surroundings in detail, helping them navigate unfamiliar spaces safely and confidently.
Real-time Navigation Assistance: Provides continuous voice feedback about obstacles, doorways, and environmental features.

Technical Architecture
LifeLine employs a sophisticated yet elegant architecture that balances on-device processing for privacy and speed with cloud capabilities for complex AI tasks:
mermaidgraph TB
    subgraph "Mobile Device (Unity App)"
        A[Sensor Data Collection] --> B[On-Device ML Models]
        B --> C[Local Decision Engine]
        C --> D[Voice Guidance System]
        C --> E[Emergency Actions]
    end
    
    subgraph "Cloud Server (FastAPI)"
        F[REST API Gateway] --> G[PyTorch Models]
        F --> H[Hugging Face LLMs]
        F --> I[Medical Knowledge Base]
    end
    
    subgraph "Data Flow"
        A --> J[Privacy Filter]
        J --> F
        G --> K[Predictions & Analysis]
        H --> K
        K --> C
    end
Technology Stack
Frontend (Client Application):

Unity Engine (C#): Provides cross-platform mobile development with native performance
Sensor Integration: Direct access to accelerometer, gyroscope, microphone, and camera
TensorFlow Lite/ONNX Runtime: On-device inference for real-time prediction
OpenCV for Unity: Powers computer vision features for blind assistance

Backend (Server & API):

Python FastAPI: High-performance, async-capable REST API framework
PyTorch: State-of-the-art deep learning framework for model training and inference
Hugging Face Transformers: Integration of powerful language models for natural language understanding
SQLite: Lightweight database for prototype data management

AI/ML Pipeline:

Custom-trained models for seizure detection, fall detection, and cardiac event recognition
Transfer learning from medical imaging datasets
Natural language processing for voice command interpretation
Computer vision models optimized for mobile deployment

Project Scope & Future Work
Current Phase (Phase 2 Submission)
This submission presents a comprehensive proof-of-concept demonstrating:

Detailed technical architecture and system design
UI/UX mockups and user flow diagrams
Feasibility analysis of sensor-based detection
Integration strategies for AI models
Privacy-preserving architecture design

Planned Implementation Roadmap
Phase 3 - MVP Development (Months 1-3):

Implement core sensor data collection module
Deploy baseline ML models for seizure and fall detection
Develop voice guidance system
Create basic emergency response features

Phase 4 - Advanced Features (Months 4-6):

Expand condition coverage (anxiety attacks, diabetic emergencies, stroke detection)
Implement blind assistance module
Optimize models for battery efficiency
Develop family notification system

Future Enhancements:

Multi-language support with regional first-aid protocols
Federated learning for privacy-preserving model improvements
Integration with emergency services APIs
Medication reminder and tracking system
Predictive analytics for episode forecasting

Setup and Installation (Hypothetical)
Follow these steps to set up the LifeLine development environment:
Prerequisites

Python 3.9 or higher
Unity 2022.3 LTS
Git
4GB+ RAM recommended

Backend Setup
bash# Clone the repository
git clone https://github.com/shaarvitripathi4748/CHOCOBAR-LifeLine-App-Thapar-Institute-of-Engineering-Technology
cd lifeline-app

# Create virtual environment
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt
requirements.txt:
txtfastapi==0.104.1
uvicorn==0.24.0
torch==2.1.0
torchvision==0.16.0
transformers==4.35.0
opencv-python==4.8.1
numpy==1.24.3
scikit-learn==1.3.2
pydantic==2.4.2
python-multipart==0.0.6
SQLAlchemy==2.0.23
Start the server
bash# Run the FastAPI server
uvicorn app.main:app --reload --host 0.0.0.0 --port 8000

# In a separate terminal, run the ML service
python ml_service/model_server.py
Mobile App Setup

Open Unity Hub and import the LifeLineUnity project
Configure your build settings for Android/iOS
Update the API endpoint in Assets/Scripts/Config.cs
Build and deploy to your device

Usage (Hypothetical)
Initial Setup

Download and Install: Get LifeLine from your app store
Create Profile: Enter your medical information, conditions, and medications
Grant Permissions: Allow access to sensors, microphone, and camera
Configure Emergency Contacts: Add family members and healthcare providers

Daily Use

Background Monitoring: Simply carry your phone, LifeLine watches over you
Voice Commands: "LifeLine, find my medication" or "LifeLine, I'm feeling dizzy"
Emergency Response: Automatic detection and guidance during medical events
Health Logs: Review episode history and share with your doctor

For Caregivers

Receive real-time alerts when episodes occur
Access detailed episode reports
View medication adherence statistics
Communicate with emergency responders

Team
Team CHOCOBAR
Thapar Institute of Engineering & Technology
We are a passionate team of engineering students committed to leveraging AI for social good. Our diverse backgrounds in machine learning, mobile development, and healthcare technology converge in LifeLine—our vision for a safer, more accessible world.

Team Members: United by innovation, driven by impact
Institution: Proudly representing TIET Patiala in Samsung PRISM GenAI Hackathon 2025
Mission: Making healthcare assistance accessible to everyone, everywhere

License
This repository and its contents, including the idea and design of LifeLine, were created for the purpose of submission to the Samsung PRISM GenAI Hackathon 2025. All intellectual property rights are retained by the authors, Team CHOCOBAR.

<div align="center">
  <b>LifeLine - Because every second counts, and every life matters.</b>
  <br><br>
  Made with ❤️ by Team CHOCOBAR for Samsung PRISM GenAI Hackathon 2025
</div>
