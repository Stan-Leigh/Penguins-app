# Palmer Penguin Classification App

A simple machine learning web application built with **Streamlit** that predicts the species of a Palmer penguin based on physical measurements and categorical attributes such as island and sex.

The app allows users to either manually input penguin measurements through sidebar controls or upload a CSV file containing penguin features. It then preprocesses the input, applies a saved classification model, and displays both the predicted species and prediction probabilities.

The deployed web app is live [here](https://stan-leigh-penguins-app.streamlit.app/)

---

## Overview

The **Palmer Penguin Classification App** predicts one of three penguin species:

- Adelie
- Chinstrap
- Gentoo

The app is based on the Palmer Penguins dataset, originally made available through the `palmerpenguins` library in R by Allison Horst.

This project demonstrates how a trained machine learning model can be deployed in a lightweight interactive web interface, making it easy for users to test predictions without writing code.

---

## Features

- Interactive Streamlit web interface
- Manual input using sidebar widgets
- CSV file upload for batch-style prediction input
- Uses penguin physical measurements as model features
- One-hot encodes categorical variables before prediction
- Loads a saved machine learning model from a `.pkl` file
- Predicts Palmer penguin species
- Displays prediction probabilities for all classes
- Shows the processed input features used by the model

---

## Demo Flow

The user can interact with the app in two ways.

### 1. Manual Input

If no CSV file is uploaded, the app allows the user to enter values manually from the sidebar:

- Island
- Sex
- Bill length
- Bill depth
- Flipper length
- Body mass

The app then converts the selected values into a dataframe and uses them for prediction.

### 2. CSV Upload

The user can upload a CSV file containing the required input columns. The app reads the file with Pandas and processes it before passing it into the trained model.

---

## Dataset

The app uses the Palmer Penguins dataset.

The local dataset file expected by the app is:

```text
penguins_cleaned.csv
```

The dataset is used in the app to support the encoding process. The app loads the cleaned penguin dataset, removes the `species` column, and combines it with the user input before applying one-hot encoding.

Expected dataset columns include:

```text
species
island
bill_length_mm
bill_depth_mm
flipper_length_mm
body_mass_g
sex
```

---

### File Descriptions

| File | Description |
|---|---|
| `penguins_app.py` | Main Streamlit application script |
| `penguins_cleaned.csv` | Cleaned Palmer Penguins dataset |
| `penguins_clf.pkl` | Saved trained classification model |
| `requirements.txt` | Python dependencies |
| `README.md` | Project documentation |

---

## Installation

Clone the repository:

```bash
git clone https://github.com/YOUR_USERNAME/YOUR_REPOSITORY_NAME.git
cd YOUR_REPOSITORY_NAME
```

Create a virtual environment:

```bash
python -m venv venv
```

Activate the environment:

On macOS/Linux:

```bash
source venv/bin/activate
```

On Windows:

```bash
venv\Scripts\activate
```

Install dependencies:

```bash
pip install -r requirements.txt
```

---

## Recommended Requirements

Use package versions that are compatible with your saved model.

Example:

```text
streamlit==1.37.1
pandas==2.2.2
numpy==1.26.4
scikit-learn==1.5.1
```

If you retrain the model using newer package versions, update `requirements.txt` to match the versions used during training.

---

## Running the App Locally

Run:

```bash
streamlit run penguins_app.py
```

Then open the local URL shown in the terminal, usually:

```text
http://localhost:8501
```

---

## Limitations

- The model is only as accurate as the training data and preprocessing pipeline.
- The app expects the cleaned dataset and saved model file to be available locally.
- The app uses a simple preprocessing flow instead of a full scikit-learn pipeline.
- Uploaded CSV files must contain the expected feature columns.
- The current implementation is designed for demonstration and learning purposes.

---

## Technologies Used

- Python
- Streamlit
- Pandas
- NumPy
- scikit-learn
- Pickle

---

## Portfolio Summary

This project demonstrates:

- Building an interactive ML app
- Preparing user input for model prediction
- Loading and using a saved machine learning model
- Deploying a lightweight data science application
- Creating a user-friendly interface for non-technical users

---

## License

This project is for educational and portfolio purposes. The Palmer Penguins dataset is credited to the `palmerpenguins` project by Allison Horst.
