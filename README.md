🎨 Pixelated Digital Image Studio

Pixelated Digital Image Studio is a full-stack image editing application built as a final submission project. It combines a FastAPI backend for image processing with a single-page frontend for interactive editing, comparison, and export.

🌐 Live Demo:
👉 https://pixelated-two.vercel.app/

📌 Project Overview

This application provides a browser-based image editing workspace with a smooth and intuitive workflow:

Upload an image
Apply one or more transformations
Compare original vs edited result
Export the final image

The frontend is implemented as a static HTML application, while the backend exposes powerful image-processing APIs.

🎯 Objectives
Build a user-friendly browser-based image editor
Develop a reliable backend API for image transformations
Support common image formats for import/export
Keep the system lightweight and easy to run locally
🛠️ Technology Stack
Layer	Technology
Backend	FastAPI, Uvicorn, Pillow
Frontend	HTML, Tailwind CSS (CDN), Vanilla JavaScript
Language	Python 3.12
Browser Support	Modern desktop browsers
✨ Features
🖥️ Frontend
Drag-and-drop or click-to-upload image import
Interactive editor workspace (tool rail, canvas, control panel)
Live API status indicator
Undo and reset functionality
Before/after comparison slider
Zoom controls for detailed inspection
Export options: PNG, JPEG, WEBP
Operation history tracking
⚙️ Backend
Health check and service status endpoints
Image processing API endpoints
Base64-encoded image responses
CORS support for frontend-backend integration
🧩 Project Structure
pixelated/
├── backend/
│   ├── main.py
│   └── requirements.txt
├── frontend/
│   └── index.html
├── README.md
└── vercel.json
🔌 Backend API
Utility Endpoints
GET /api/ → Service status
GET /api/health → Health check
GET /api/operations → List supported operations
Image Processing Endpoints
POST /api/process/grayscale
POST /api/process/blur
POST /api/process/sharpen
POST /api/process/brightness
POST /api/process/contrast
POST /api/process/saturation
POST /api/process/invert
POST /api/process/sepia
POST /api/process/rotate
POST /api/process/flip
POST /api/process/edge-detect
POST /api/process/emboss
POST /api/process/pixelate
POST /api/process/resize
POST /api/process/crop

📌 All endpoints:

Accept an uploaded image file
Return edited image as Base64-encoded PNG
🚀 Setup & Run
1️⃣ Install Backend Dependencies
cd backend
pip install -r requirements.txt
2️⃣ Start Backend Server
uvicorn main:app --host 0.0.0.0 --port 8000

📍 API available at:

http://localhost:8000/api/health
http://localhost:8000/docs
3️⃣ Run Frontend
Option 1: Direct Open
Open frontend/index.html in your browser
Option 2: Local Server
cd frontend
python -m http.server 3000

Then visit:

http://localhost:3000
✅ Verification

The backend was successfully tested locally:

GET /api/health
{"status": "healthy"}

✔ Confirms API is running correctly and ready for frontend integration
