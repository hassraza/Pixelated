# Pixelated Digital Image Studio

Pixelated Digital Image Studio is a full-stack image editing project built for a final submission report. It combines a **FastAPI backend** for image processing with a **single-page frontend** for uploading, editing, comparing, and exporting images.

The project focuses on a clean workflow:
1. Upload an image.
2. Apply one or more transformations.
3. Compare the original and edited result.
4. Export the final image in a common format.

---

## Project Overview

The application provides a browser-based editing workspace with common image manipulation tools such as grayscale, blur, sharpen, brightness, contrast, saturation, invert, sepia, rotate, flip, edge detection, emboss, pixelate, resize, and crop.

The frontend is implemented as a static HTML application in `frontend/index.html`, while the backend exposes image-processing endpoints through FastAPI in `backend/main.py`.

---

## Objectives

- Build a usable image editing interface in the browser.
- Provide a backend API that performs reliable image transformations.
- Support common import/export formats.
- Keep the design lightweight and easy to run locally for review or submission.

---

## Technology Stack

- **Backend:** FastAPI, Uvicorn, Pillow
- **Frontend:** HTML, Tailwind CSS via CDN, vanilla JavaScript
- **Browser support:** Modern desktop browsers
- **Development language:** Python 3.12

---

## Features

### Frontend
- Drag-and-drop or click-to-upload image import.
- Editor workspace with tool rail, canvas area, and control panel.
- Live API status indicator.
- Undo and reset actions.
- Before/after comparison slider.
- Export options for PNG, JPEG, and WEBP.
- Zoom controls for closer inspection.
- Operation history for reviewing applied steps.

### Backend
- Health check and operations listing endpoints.
- Image processing endpoints under `/api/process/*`.
- Base64 encoded image responses for easy frontend display.
- Cross-origin support for local frontend development.

---

## Project Structure

```text
pixelated/
├── backend/
│   ├── main.py
│   └── requirements.txt
├── frontend/
│   └── index.html
├── README.md
└── vercel.json
```

---

## Backend API Summary

### Utility endpoints
- `GET /api/` - service status
- `GET /api/health` - health check
- `GET /api/operations` - list supported operations

### Image processing endpoints
- `POST /api/process/grayscale`
- `POST /api/process/blur`
- `POST /api/process/sharpen`
- `POST /api/process/brightness`
- `POST /api/process/contrast`
- `POST /api/process/saturation`
- `POST /api/process/invert`
- `POST /api/process/sepia`
- `POST /api/process/rotate`
- `POST /api/process/flip`
- `POST /api/process/edge-detect`
- `POST /api/process/emboss`
- `POST /api/process/pixelate`
- `POST /api/process/resize`
- `POST /api/process/crop`

All processing endpoints accept an uploaded image file and return the edited result as Base64-encoded PNG data.

---

## Setup and Run

### 1. Install backend dependencies

```bash
cd backend
pip install -r requirements.txt
```

### 2. Start the backend server

```bash
uvicorn main:app --host 0.0.0.0 --port 8000
```

The API will be available at:

- `http://localhost:8000/api/health`
- `http://localhost:8000/docs`

### 3. Run the frontend

Option 1: open `frontend/index.html` directly in a browser.

Option 2: serve the folder locally:

```bash
cd frontend
python -m http.server 3000
```

Then open:

- `http://localhost:3000`

---

## Verification

The backend was verified locally after setup with a successful health check:

- `GET /api/health` returned `{"status":"healthy"}`

This confirms the API starts correctly and is ready for the frontend.

---

## Submission Notes

This project is suitable for a final submission because it demonstrates:

- a working client-server architecture,
- a complete set of practical image editing features,
- a clean and responsive browser UI,
- and a documented local setup process for reviewers.

