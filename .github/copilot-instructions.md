# Copilot Instructions for Mergington High School Activities API

## Project Overview
- This is a simple FastAPI web application for managing extracurricular activities at Mergington High School.
- The backend (`src/app.py`) exposes REST endpoints for listing activities and signing up students.
- The frontend is a static site (`src/static/index.html`, `app.js`, `styles.css`) that interacts with the API.
- All data is stored in-memory (no database). Activities and participants reset on server restart.

## Key Components
- **Backend:**
  - `src/app.py`: FastAPI app, defines endpoints:
    - `GET /activities`: List all activities and participants
    - `POST /activities/{activity_name}/signup?email=...`: Sign up a student
    - `GET /`: Redirects to static HTML frontend
  - Activities are stored in a Python dict, keyed by activity name.
- **Frontend:**
  - `src/static/index.html`: Main UI, loads activities and provides signup form
  - `src/static/app.js`: Fetches activities, handles signup via API
  - `src/static/styles.css`: Basic styling

## Developer Workflows
- **Install dependencies:**
  - `pip install -r requirements.txt` (or see `src/README.md` for minimal install)
- **Run the app:**
  - `cd src && python app.py` (runs on http://localhost:8000)
  - Or use Uvicorn: `uvicorn app:app --reload`
- **Access the app:**
  - Frontend: http://localhost:8000/static/index.html
  - API docs: http://localhost:8000/docs

## Project Conventions
- No persistent storage: all data is lost on restart.
- Activity names are unique identifiers.
- Email is required for signup; no authentication is enforced.
- Static files are served from `/static` route.
- No test suite or CI/CD is present by default.

## Examples
- To add a new activity, edit the `activities` dict in `src/app.py`.
- To change the UI, edit files in `src/static/`.

## References
- See `src/README.md` for API and usage details.
- See `requirements.txt` for dependencies.

---
If you add new workflows or conventions, update this file to help future AI agents and developers.
