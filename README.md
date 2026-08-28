# Student Marks Prediction System

An end-to-end machine learning web application that predicts a student's math score based on demographic and academic factors.

---

## How it Works

The app takes 7 inputs from the user — gender, ethnicity, parental education, lunch type, test prep course, reading score, and writing score — and predicts the math score using a trained regression model.

8 models were trained and evaluated (Random Forest, XGBoost, CatBoost, Gradient Boosting, AdaBoost, Decision Tree, KNN, Linear Regression). The best performing model is automatically selected and saved.

---

## Project Structure

```
├── src/
│   ├── components/
│   │   ├── data_ingestion.py       # Loads and splits dataset
│   │   ├── data_transformation.py  # Preprocessing pipeline
│   │   └── model_trainer.py        # Trains and selects best model
│   ├── pipeline/
│   │   ├── predict_pipeline.py     # Loads model and runs inference
│   │   └── train_pipeline.py
│   ├── exception.py
│   ├── logger.py
│   └── utils.py
├── artifacts/                      # Saved model and preprocessor
├── notebook/                       # EDA and model training notebooks
├── templates/                      # Flask HTML templates
├── application.py                  # Flask app entry point
├── render.yaml                     # Render deployment config
└── requirements.txt
```

---

## Run Locally

**1. Clone the repo**
```bash
git clone https://github.com/<your-username>/<your-repo-name>.git
cd <your-repo-name>
```

**2. Create and activate a virtual environment**
```bash
python -m venv venv

# Windows
venv\Scripts\activate

# Mac/Linux
source venv/bin/activate
```

**3. Install dependencies**
```bash
pip install -r requirements.txt
```

**4. Run the app**
```bash
python application.py
```

**5. Open in browser**
```
http://localhost:5000
```

---

## Deploy on Render

**1.** Push your project to a GitHub repository (make sure `artifacts/` with `.pkl` files is included)

**2.** Go to [render.com](https://render.com) and sign up / log in

**3.** Click **New → Web Service**

**4.** Connect your GitHub account and select your repository

**5.** Render will auto-detect `render.yaml` — verify these settings:
- Build Command: `pip install -r requirements.txt`
- Start Command: `gunicorn application:application`

**6.** Click **Deploy** — your app will be live at a `*.onrender.com` URL in a few minutes

---

## Tech Stack

- Python, Flask, Gunicorn
- Scikit-learn, XGBoost, CatBoost
- Pandas, NumPy
- HTML, CSS (custom UI)
- Render (deployment)
