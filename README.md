# ACN Server Monitoring System (IoT) - README

This repository contains two parts: the Python backend (`acn_backend_iot`) and the Vite + React frontend (`acn_frontend_iot`). This README explains how to run both locally and how to commit the README to your GitHub repository.

## Prerequisites
- **Python**: 3.8 or newer
- **Node.js**: 16+ (includes `npm`)
- **Git**: for committing and pushing

## Backend - `acn_backend_iot`
1. Open a terminal and change directory:

```powershell
cd acn_backend_iot
```

2. Create and activate a virtual environment (recommended):

Windows (PowerShell):
```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
```

3. Install dependencies
- If there is a `requirements.txt`, run:

```powershell
pip install -r requirements.txt
```

- If no `requirements.txt` exists, install the packages your project needs. If you are missing a dependency at runtime, install it (for example `pip install pyserial`) and then consider creating `requirements.txt` with `pip freeze > requirements.txt`.

4. Run the backend components
- Start the main backend server:

```powershell
python main.py
```

- If your setup requires joystick input, run the reader in a separate terminal:

```powershell
python joystick_reader.py
```

Notes:
- Run `main.py` first if it serves an API that the frontend will call. Run `joystick_reader.py` in another terminal if it provides input to the backend.

## Frontend - `acn_frontend_iot`
1. Change directory to the frontend:

```powershell
cd ..\acn_frontend_iot
```

2. Install dependencies:

```powershell
npm install
```

3. Run the dev server:

```powershell
npm run dev
```

4. Build for production:

```powershell
npm run build
npm run preview
```

The frontend uses Vite; `npm run dev` starts a local dev server (see the terminal output for the URL, usually `http://localhost:5173`).

If this project also packages an Electron application, you can build the desktop binary (when an `electron:build` script is present) by running:

```powershell
npm run electron:build
```

## Commit and push the README to GitHub
From the repository root:

```powershell
git add README.md
git commit -m "chore: add README with run instructions"
git push origin <branch-name>
```

Replace `<branch-name>` with your working branch (e.g., `main` or `master`).

## Troubleshooting
- If the frontend cannot reach the backend, verify backend is running and check CORS or the API base URL.
- If Python modules are missing, install them in the venv and update `requirements.txt`.

## Contact / Next steps
- If you want, I can also: create a `requirements.txt` from the running environment, add a `.env.example`, or create GitHub Actions to run lint/build on push.

---
Generated on: December 11, 2025
