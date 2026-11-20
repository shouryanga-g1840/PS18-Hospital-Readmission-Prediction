# PS18 Hospital Readmission Prediction API

Basic FastAPI deployment of the PS18 30-day hospital readmission prediction model.

## Run locally

```bash
python -m venv .venv
# Activate the environment, then:
pip install -r requirements.txt
uvicorn main:app --reload
```

Open:
- API health check: http://127.0.0.1:8000/
- Interactive API documentation: http://127.0.0.1:8000/docs
- Model information: http://127.0.0.1:8000/model-info

## Deploy to Render

Create a new **Web Service** from this GitHub repository. Render can detect `render.yaml`
as a Blueprint, or use these settings manually:

- Build command: `pip install -r requirements.txt`
- Start command: `uvicorn main:app --host 0.0.0.0 --port $PORT`

The model file `readmission_model.joblib` must remain in the repository root alongside `main.py`.

## Prediction

Send a JSON POST request to `/predict`. The request schema is shown in `/docs`.

## Important

This repository exposes an API and its Swagger documentation; it does not include a separate
graphical patient dashboard. Predictions are experimental decision-support outputs and must
not be used as a substitute for professional clinical judgment. Do not submit real patient
identifiers or sensitive patient information to a public demo.
