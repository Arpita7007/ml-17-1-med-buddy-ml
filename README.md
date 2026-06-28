# ⚕️ MedBuddy.ML — Heart Disease Risk Predictor

A full-stack machine learning web application that predicts heart disease risk from clinical patient data. Built with a FastAPI backend, Streamlit frontend, and an XGBoost/Scikit-learn model trained on the Cleveland Heart Disease dataset.

🔴 **Live Demo:** [medbuddy-fronend.onrender.com](https://medbuddy-fronend.onrender.com)  
📡 **API Docs:** [ml-17-1-med-buddy-ml-1.onrender.com/docs](https://ml-17-1-med-buddy-ml-1.onrender.com/docs)

---

## 🧠 What It Does

Enter 13 clinical features (age, cholesterol, heart rate, etc.) and the model returns:
- **Prediction** — Heart Disease Detected / Not Detected
- **Probability** — Confidence score of the prediction

---

## 🏗️ Project Structure

```
ml-17-1-med-buddy-ml/
├── backend/
│   ├── __init__.py
│   ├── main.py          # FastAPI app & prediction endpoint
│   ├── predictor.py     # Model loading & inference logic
│   └── training.py      # Model training script
├── dataset/
│   └── heart.csv        # Cleveland Heart Disease dataset
├── frontend/
│   └── app.py           # Streamlit UI
├── model_dir/
│   └── heart_disease_prediction_model.joblib
├── notebook_files/
│   └── _17_1_med_buddy_ml_notebook.ipynb
├── Procfile
├── requirements.txt
└── env_template.txt
```

---

## 🤖 ML Details

| Component | Detail |
|---|---|
| Dataset | Cleveland Heart Disease (UCI) |
| Target | Binary — 0: No Disease, 1: Disease |
| Features | 13 clinical attributes |
| Libraries | Scikit-learn, XGBoost, Pandas, NumPy |
| Model | Saved as `.joblib` for fast inference |

### Input Features

| Feature | Description |
|---|---|
| `age` | Age in years |
| `sex` | Sex (1 = Male, 0 = Female) |
| `cp` | Chest pain type (0–3) |
| `trestbps` | Resting blood pressure (mm Hg) |
| `chol` | Serum cholesterol (mg/dl) |
| `fbs` | Fasting blood sugar > 120 mg/dl (1 = True) |
| `restecg` | Resting ECG results (0–2) |
| `thalach` | Maximum heart rate achieved |
| `exang` | Exercise induced angina (1 = Yes) |
| `oldpeak` | ST depression induced by exercise |
| `slope` | Slope of peak exercise ST segment |
| `ca` | Number of major vessels (0–4) |
| `thal` | Thalassemia type (0–3) |

---

## 🔌 API Reference

**Base URL:** `https://ml-17-1-med-buddy-ml-1.onrender.com`

### `GET /health`
Health check endpoint.
```json
{ "status": "ok" }
```

### `POST /predict-heart-disease`
Returns prediction and probability.

**Request body:**
```json
{
  "age": 52, "sex": 1, "cp": 0,
  "trestbps": 125, "chol": 212, "fbs": 0,
  "restecg": 1, "thalach": 168, "exang": 0,
  "oldpeak": 1.0, "slope": 2, "ca": 0, "thal": 2
}
```

**Response:**
```json
{
  "prediction": 0,
  "probability": 0.14,
  "diagnosis": "No Heart Disease Detected"
}
```

---

## 🚀 Tech Stack

| Layer | Technology |
|---|---|
| ML | Scikit-learn, XGBoost, Pandas, NumPy |
| Backend | FastAPI, Uvicorn, Joblib |
| Frontend | Streamlit |
| Deployment | Render (backend + frontend) |
| Environment | Python 3.11, python-dotenv |

---

## ⚙️ Run Locally

### 1. Clone the repo
```bash
git clone https://github.com/Arpita7007/ml-17-1-med-buddy-ml.git
cd ml-17-1-med-buddy-ml
```

### 2. Create a virtual environment
```bash
python -m venv .venv
.venv\Scripts\activate   # Windows
source .venv/bin/activate  # Mac/Linux
```

### 3. Install dependencies
```bash
pip install -r requirements.txt
```

### 4. Set up environment variables
```bash
cp env_template.txt .env
# Edit .env and set PROJECT_ROOT to your local project path
```

### 5. Run the backend
```bash
uvicorn backend.main:app --reload
```

### 6. Run the frontend (new terminal)
```bash
streamlit run frontend/app.py
```

---

## 🌐 Deployment

| Service | Platform | URL |
|---|---|---|
| FastAPI Backend | Render | `https://ml-17-1-med-buddy-ml-1.onrender.com` |
| Streamlit Frontend | Render | `https://medbuddy-fronend.onrender.com` |

> ⚠️ Free tier on Render spins down after inactivity. First request may take ~30 seconds to wake up.

---

## 👩‍💻 Author

**Arpita** — B.Tech Data Science & Big Data  
[GitHub](https://github.com/Arpita7007)
