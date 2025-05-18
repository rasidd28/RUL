# 🔧 Remaining Useful Life (RUL) Prediction using LSTM

This project focuses on predicting the **Remaining Useful Life (RUL)** of jet engines using **Long Short-Term Memory (LSTM)** networks. The dataset used is the **NASA C-MAPSS** FD001 dataset, a popular benchmark for predictive maintenance tasks.

---

## 📁 Dataset

- **Source**: [NASA C-MAPSS Dataset](https://data.nasa.gov/dataset/cmapss-jet-engine-simulated-data)
- **Subset Used**: `FD001`
- **Train Trajectories**: 100 engines
- **Test Trajectories**: 100 engines
- **Operating Conditions**: 1
- **Fault Modes**: 1 

Each engine runs until failure. The objective is to predict how many cycles remain before each engine fails.

---

## 📊 Exploratory Data Analysis (EDA)

A thorough EDA was performed to better understand the data characteristics and relationships between variables.

### ✅ Key Tasks:
- **Dataset Inspection**: Checked for missing values, datatypes, and value distributions.
- **Sensor Histograms**: Plotted and saved histograms for each sensor to understand distributions.
- **Time-Series Analysis**: Plotted time-series data of operational settings and all sensors for selected engine units.
- **Correlation Analysis**: Computed and visualized correlation matrix using a heatmap.

📁 Files/Outputs generated:
- `EDA_summary_statistics.csv`
- `EDA_missing_values.csv`
- `EDA_sensor_distributions.png`
- `Unit_<n>_All_Plots.png`
- `Unit_<n>_Correlation_Heatmap.png`

---

## 🧠 Model: LSTM (Long Short-Term Memory)

### ✅ Architecture:
- **Input**: Time-series data of selected sensors per unit
- **Layers**:
  - LSTM Layer(s)
  - Dense Layer for regression output
- **Loss Function**: Mean Squared Error (MSE)
- **Optimizer**: Adam

### 🔧 Preprocessing:
- Normalized sensor data
- Windowed the data using sliding windows
- Target: Remaining cycles from each timestep

---

## 📈 Results

- **Evaluation Metric**: RMSE (Root Mean Squared Error)
- The model effectively predicted the RUL trend with reasonable accuracy.
- Further improvements can be achieved using:
  - Sensor selection based on correlation/variance
  - Adding more units from other C-MAPSS datasets (FD002–FD004)
  - Using attention mechanisms or bidirectional LSTM layers

---

## 🚀 Future Work

- Hyperparameter tuning for better generalization
- Cross-dataset validation (e.g., FD002, FD003)
- Integration with real-time simulation dashboards

---

## 🧾 Requirements

Install the following libraries before running the code:

```bash
pip install numpy pandas matplotlib seaborn scikit-learn tensorflow
