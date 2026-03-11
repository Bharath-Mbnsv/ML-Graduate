# 🎓 ML-Graduate — University Admission Predictor

A Machine Learning-powered tool that helps prospective graduate students make smarter, data-driven decisions when applying to Master's programs — predicting admission chances and classifying universities as **ambitious**, **moderate**, or **safe** picks based on a student's academic profile.

---

## 🎯 Overview

Choosing which universities to apply to is one of the most stressful decisions for graduate school applicants. Existing consultancies and predictors often rely on limited past data and subjective judgment. This project takes a data-driven approach — training multiple ML models on real admission data to objectively evaluate a student's profile and recommend universities accordingly.

Students can input their academic credentials and instantly receive:
- Predicted admission probability for target universities
- Classification of each university as ambitious, moderate, or safe
- A comparison of past admits with similar profiles

---

## ✨ Features

- Accepts multiple student profile inputs for prediction
- Trains and evaluates **three ML models** — results compared to select the best
- Classifies university choices as **Ambitious / Moderate / Safe**
- Displays historical admits with similar academic profiles for reference
- Saved model (`svc_model.pickel`) for fast, reusable inference
- Clean Jupyter Notebook for transparent, reproducible analysis

---

## 📥 Input Features

| Feature                     | Description                                      |
|-----------------------------|--------------------------------------------------|
| 📝 GRE Score                | Graduate Record Examination score                |
| 🌐 TOEFL Score              | Test of English as a Foreign Language score      |
| 🎓 B.Tech Percentage        | Undergraduate academic performance               |
| 📅 Term Applying For        | Fall / Spring intake                             |
| 📄 Research Papers          | Total technical papers published                 |

---

## 🤖 Models Used

| Model               | Type                    | Use Case                              |
|---------------------|-------------------------|---------------------------------------|
| Linear Regression   | Regression              | Predict continuous admission score    |
| Support Vector Machine (SVM) | Classification | Classify admission likelihood        |
| Random Forest       | Ensemble Classification | Robust prediction across varied profiles |

All three models are trained, evaluated, and compared using error metrics to select the best performer for final predictions.

---

## 📊 Model Evaluation

Models are compared using standard error and performance metrics:

- **Mean Absolute Error (MAE)**
- **Mean Squared Error (MSE)**
- **R² Score** (for regression)
- **Accuracy, Precision, Recall** (for classifiers)

The best-performing model is used to generate the final university predictions.

---

## 🗂️ Project Structure

```
├── Dataset.csv             # Admission records with student profiles and outcomes
├── education.ipynb         # Main Jupyter Notebook — EDA, training, evaluation
├── education.ipynb copy    # Backup / experimental notebook
├── svc_model.pickel        # Serialized trained SVM model for reuse
└── README.md
```

---

## ⚙️ Installation & Setup

### Prerequisites

- Python 3.7+
- Jupyter Notebook

### Clone the Repository

```bash
git clone https://github.com/Bharath-Mbnsv/ML-Graduate.git
cd ML-Graduate
```

### Install Dependencies

```bash
pip install pandas numpy scikit-learn matplotlib seaborn jupyter
```

### Launch the Notebook

```bash
jupyter notebook education.ipynb
```

---

## 🔄 Workflow

```
Raw Data (Dataset.csv)
        │
        ▼
Data Preprocessing & EDA
        │
        ▼
Feature Engineering
        │
        ▼
┌───────┬──────────┬──────────────┐
│  LR   │   SVM    │ Random Forest│
└───┬───┴────┬─────┴──────┬───────┘
    │        │             │
    └────────┴─────────────┘
              │
        Model Comparison
        (MAE, MSE, R², Accuracy)
              │
        Best Model Selected
              │
        University Prediction
        (Ambitious / Moderate / Safe)
```

---

## 🏁 Output

Given a student's profile, the system outputs:

```
University: XYZ University
Admission Probability: 78%
Classification: Moderate ✅

Similar Past Admits:
  GRE: 320 | TOEFL: 108 | B.Tech: 82% | Status: Admitted
  GRE: 318 | TOEFL: 105 | B.Tech: 80% | Status: Admitted
```

---

## 🔮 Future Improvements

- Add more features — LOR strength, SOP quality score, work experience
- Expand dataset with more diverse universities and geographic regions
- Build an interactive web app using **Flask** or **Streamlit**
- Integrate a **recommendation engine** to suggest best-fit universities automatically
- Use **deep learning** models for improved prediction accuracy on larger datasets

---

## 🤝 Contributing

Contributions are welcome! To get started:

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/your-feature`)
3. Commit your changes (`git commit -m 'Add your feature'`)
4. Push to the branch (`git push origin feature/your-feature`)
5. Open a Pull Request
