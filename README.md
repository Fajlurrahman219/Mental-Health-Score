
# Mental Health Score Prediction

A Machine Learning web application that predicts a mental health score based on student lifestyle, social media usage, academic details, sleep, physical activity, and stress level.

## Live Demo

- **Live Website:** https://mental-health-score-1-djoz.onrender.com/
- **Backend API:** https://mental-health-score-api-2026.onrender.com
- **API Documentation:** https://mental-health-score-api-2026.onrender.com/docs
- **GitHub Repository:** https://github.com/Fajlurrahman219/Mental-Health-Score

## Project Overview

The Mental Health Score Prediction project uses a trained machine learning model to estimate a score from user-provided lifestyle and demographic information.

Users enter their details through a web form. The frontend sends the data to a FastAPI backend, which processes the input and returns the model's prediction.

**Note:** This project is for educational and informational purposes only. It is not a medical diagnostic tool and should not replace professional mental health advice.

## Features

- Interactive web-based form
- Student lifestyle and academic information input
- Social media usage analysis
- Form validation
- Machine learning-based score prediction
- FastAPI REST API integration
- Interactive API documentation
- Responsive frontend
- Cloud deployment using Render

## Tech Stack

### Frontend
- HTML5
- CSS3
- JavaScript

### Backend
- Python
- FastAPI
- Pydantic
- Uvicorn

### Machine Learning
- Pandas
- Scikit-learn
- Joblib
- Trained machine learning model

### Deployment
- Render
- GitHub

## Project Structure

```text
Mental-Health-Score/
├── main.py
├── Mental_Health_Model.pkl
├── requirements.txt
├── index.html
├── style.css
├── script.js
├── Student Social Media And Mental Health Impact.csv
├── ML_Project.ipynb
└── README.md
```

## How It Works

1. The user opens the web application.
2. The user enters the required personal, academic, and lifestyle information.
3. JavaScript validates the form data.
4. The frontend sends a JSON request to the FastAPI `/predict` endpoint.
5. The backend validates the request and passes the required features to the trained model.
6. The model generates a predicted mental health score.
7. The frontend displays the prediction to the user.

## Input Features

The prediction API accepts these fields:

| Field | Description |
|---|---|
| `age` | User's age |
| `gender` | Gender |
| `country` | Country |
| `academic_level` | Current academic level |
| `most_used_platform` | Most-used social media platform |
| `purpose_of_use` | Main purpose of social media use |
| `avg_daily_usage_hours` | Average daily social media usage |
| `daily_unlocks` | Number of daily phone unlocks |
| `study_hours` | Daily study hours |
| `physical_activity_hours` | Daily physical activity hours |
| `sleep_hours_per_night` | Average nightly sleep |
| `stress_level` | Reported stress level |

## Example API Request

```json
{
  "age": 21,
  "gender": "Male",
  "country": "India",
  "academic_level": "Undergraduate",
  "most_used_platform": "Instagram",
  "purpose_of_use": "Education",
  "avg_daily_usage_hours": 4.5,
  "daily_unlocks": 60,
  "study_hours": 5,
  "physical_activity_hours": 1,
  "sleep_hours_per_night": 7,
  "stress_level": "Medium"
}
```

## Example API Response

```json
{
  "predicted_mental_health_score": 6.78
}
```

The response value is illustrative. Actual predictions depend on the submitted data and trained model.

## Run Locally

### 1. Clone the repository

```powershell
git clone https://github.com/Fajlurrahman219/Mental-Health-Score.git
cd Mental-Health-Score
```

### 2. Create a virtual environment

```powershell
py -m venv .venv
```

### 3. Activate the environment

```powershell
.\.venv\Scripts\Activate.ps1
```

If PowerShell blocks activation, run:

```powershell
Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass
.\.venv\Scripts\Activate.ps1
```

### 4. Install dependencies

```powershell
python -m pip install --upgrade pip
pip install -r requirements.txt
```

### 5. Start the FastAPI backend

Ensure `main.py` and `Mental_Health_Model.pkl` are present in the project root.

```powershell
uvicorn main:app --reload
```

Open the following URLs:

- API: http://127.0.0.1:8000/
- API documentation: http://127.0.0.1:8000/docs

### 6. Open the frontend

Open `index.html` in your browser or use the VS Code Live Server extension.

For local testing, configure the API URL in `script.js`:

```javascript
const API_BASE = "http://127.0.0.1:8000";
```

For the deployed frontend, use the actual deployed backend URL:

```javascript
const API_BASE = "https://mental-health-score-api-2026.onrender.com";
```

Make sure the configured URL matches the backend that is currently running.

## API Endpoint

**Method:** `POST`

**Endpoint:** `/predict`

**Content-Type:** `application/json`

The API accepts the input features and returns a JSON response containing the predicted score.

You can test the backend using the [FastAPI Swagger Documentation](https://mental-health-score-api-2026.onrender.com/docs).

## Troubleshooting

- **Failed to fetch:** Verify the backend URL, backend status, network connection, and CORS configuration.
- **422 Unprocessable Entity:** Check that request field names, types, and allowed values match the backend schema.
- **500 Internal Server Error:** Check the Render backend logs and verify that the model file loads correctly.
- **Slow first request:** A hosted service may need time to wake up after being idle.

## Limitations

- Predictions are estimates generated by a machine learning model.
- The result is not a clinical diagnosis.
- Model performance depends on the dataset and training process.
- Dataset bias or missing information may affect predictions.
- Avoid entering sensitive personal information.

If you are experiencing mental health difficulties, consider speaking with a qualified mental health professional.

## Author

**GitHub:** [Fajlurrahman219](https://github.com/Fajlurrahman219)

## License

No open-source license has been specified for this project yet.
