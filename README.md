# Forest Fire Weather Index (FWI) Prediction

A Flask web application that predicts the **Fire Weather Index (FWI)** using a Ridge Regression model trained on the **Algerian Forest Fires dataset**. 

---

## About

The **Fire Weather Index (FWI)** is a numeric rating of fire intensity, commonly used in forest fire risk assessment. This project uses a trained **Ridge Regression** model to predict FWI based on meteorological and fire-related inputs, served through a simple Flask web interface.

---

## Project Structure

```
your_app/
├── app.py                 # Flask application
├── templates/
│   ├── index.html         # Landing page
│   └── home.html          # Prediction form + result page
├── static/
│   └── style.css           # Stylesheet for the form
├── models/
│   ├── ridge.pkl           # Trained Ridge Regression model
│   └── scaler.pkl          # Fitted StandardScaler
└── README.md
```

---

## Features Used

| Feature | Description | Typical Range |
|---|---|---|
| `Temperature` | Temperature in °C | 22 – 42 |
| `RH` | Relative Humidity (%) | 21 – 90 |
| `Ws` | Wind Speed (km/h) | 6 – 29 |
| `Rain` | Rainfall (mm) | 0 – 16.8 |
| `FFMC` | Fine Fuel Moisture Code | 28 – 92 |
| `DMC` | Duff Moisture Code | 1 – 65 |
| `ISI` | Initial Spread Index | 0 – 18 |
| `classes` | Fire occurrence (0 = No Fire, 1 = Fire) | 0 / 1 |
| `Region` | Region (0 = Bejaia, 1 = Sidi-Bel Abbes) | 0 / 1 |

---

## Tech Stack

- **Backend:** Flask (Python)
- **ML Model:** Ridge Regression (scikit-learn)
- **Preprocessing:** StandardScaler
- **Frontend:** HTML, CSS
- **Data:** Algerian Forest Fires Dataset

---

## Installation

1. **Clone the repository**
   ```bash
   git clone <your-repo-url>
   cd your_app
   ```

2. **Create a virtual environment (recommended)**
   ```bash
   python -m venv venv
   source venv/bin/activate   # On Windows: venv\Scripts\activate
   ```

3. **Install dependencies**
   ```bash
   pip install flask scikit-learn pandas numpy
   ```

4. **Ensure model files exist**
   Make sure `models/ridge.pkl` and `models/scaler.pkl` are present in the `models/` folder.

---

## Usage

1. **Run the Flask app**
   ```bash
   python app.py
   ```

2. **Open in browser**
   ```
   http://127.0.0.1:8080/
   ```

3. **Navigate to the prediction page**
   ```
   http://127.0.0.1:8080/predictdata
   ```

4. **Fill in the form** with weather and fire-risk parameters, then click **Predict** to see the estimated FWI value.

---

## Sample Input

| Field | Sample Value |
|---|---|
| Temperature | 32 |
| RH | 45 |
| Ws | 15 |
| Rain | 0 |
| FFMC | 84.5 |
| DMC | 24.3 |
| ISI | 8.2 |
| classes | 1 |
| Region | 0 |

---

## Model Details

- **Algorithm:** Ridge Regression
- **Preprocessing:** Features are scaled using `StandardScaler` before being passed to the model.
- **Output:** A continuous numeric FWI score — higher values indicate greater fire risk.

---

## License

This project is open source and available under the [MIT License](LICENSE).
