# 🛡️ Fraud Detection System using Machine Learning & Deep Learning

This Django-based web application detects fraudulent activities in uploaded datasets using machine learning and deep learning models, including:

* SVM (Support Vector Machine)
* Naive Bayes
* AutoEncoder (Proposed Model)
* LSTM (Extension Model)

---

## 🚀 Features

* 📁 Upload and process CSV datasets
* 🧠 Train models on provided data
* 📊 Compare model performance using accuracy, precision, recall, and F1-score
* 🖼️ Visualize metrics with bar charts
* 🔐 Secure login system with email-based OTP verification
* 🔎 Predict labels on new test data

---

## 📂 Folder Structure

```
WebAttackDetection/
│
├── WebApp/                  # Django App
│   ├── templates/           # HTML templates
│   ├── static/              # Uploaded CSV files
│   ├── views.py             # Backend logic (ML/DL models)
│   ├── urls.py              # URL routing
│   └── models.py
│
├── WebAttackDetection/      # Django Project
│   ├── settings.py
│   ├── urls.py
│
├── manage.py
└── README.md
```

---

## 🧰 Requirements

Install dependencies using pip:

```bash
pip install -r requirements.txt
```
---

## 🛠️ Setup Instructions

1. **Clone the repository**

```bash
git clone https://github.com/your-repo/fraud-detection.git
cd fraud-detection
```

2. **Create a virtual environment**

```bash
python -m venv venv
source venv/bin/activate   # On Windows: venv\Scripts\activate
```

3. **Install dependencies**

```bash
pip install -r requirements.txt
```

4. **Set up the MySQL database**

```sql
CREATE DATABASE WebAttackDB;

-- Table for user registration
CREATE TABLE register (
  username VARCHAR(50) PRIMARY KEY,
  password VARCHAR(50),
  contact VARCHAR(15),
  email VARCHAR(100),
  address TEXT
);
```

5. **Update SMTP credentials**

Edit the `sendOTP` function in `views.py`:

```python
email_address = 'your_email@gmail.com'
email_password = 'your_app_password'
```

Use [Google App Passwords](https://support.google.com/accounts/answer/185833) if using Gmail.

6. **Run the Django server**

```bash
python manage.py runserver
```

7. **Access the application**

Open your browser and go to:
`http://127.0.0.1:8000/`

---

## 🧪 Functionalities

| Feature               | Description                          |
| --------------------- | ------------------------------------ |
| **User Signup/Login** | With OTP verification to email       |
| **Dataset Upload**    | Accepts `.csv` file and processes it |
| **Run Models**        | SVM, Naive Bayes, AutoEncoder, LSTM  |
| **Predict New Data**  | Upload new file for prediction       |
| **Visualizations**    | Compare algorithms using graphs      |


---

## 📌 Notes

* The dataset must be in CSV format.
* First column (protocol) and third column (service) are label encoded.
* All features are one-hot encoded before training.
* LSTM input is reshaped to 3D.
* `autoencoder` is trained to reconstruct input and detect anomalies based on reconstruction error.

---

## 🧠 Algorithms

### ✅ SVM & Naive Bayes

Standard supervised learning classifiers trained on preprocessed features.

### 💡 Proposed: AutoEncoder

* Unsupervised anomaly detection
* Compresses and reconstructs data
* High reconstruction error indicates anomaly

### 🔮 Extension: LSTM

* Deep learning sequential model
* Applied over encoded features


Would you like the `requirements.txt` or `.sql` dump file generated too?
