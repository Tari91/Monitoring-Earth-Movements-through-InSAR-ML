**InSAR Ground Deformation Monitoring with Machine Learning**
Using Synthetic Data for Simulation
📌 Overview
This project demonstrates ground deformation monitoring using Interferometric Synthetic Aperture Radar (InSAR) data and Machine Learning (ML). It includes:
✅ Synthetic InSAR data generation (simulating subsidence, noise, atmospheric effects)
✅ Feature engineering (spatial, temporal, and neighborhood features)
✅ ML-based deformation prediction (Random Forest regression)
✅ Anomaly detection (Isolation Forest for unusual movements)
✅ Excel export (.xls or .xlsx reports for analysis)

📂 Project Structure
insar_ml_monitoring/  
│── 📄 README.md                  # This file  
│── 📄 insar_monitoring.py        # Main Python script  
│── 📊 insar_results.xls          # Sample output (Excel)  
│── 📈 plots/                     # Saved visualizations (optional)  
🚀 Quick Start
1. Install Dependencies
bash
pip install numpy pandas scikit-learn scikit-image matplotlib xlwt openpyxl xlsxwriter
2. Run the Script
bash
python insar_monitoring.py
(This will generate synthetic data, train the model, and export results to insar_results.xls)

3. Outputs Generated
insar_results.xls (or .xlsx) with:

Raw InSAR phase & deformation data

Model predictions

Detected anomalies

Plots (if enabled) showing:

Subsidence patterns over time

Anomaly detection results

🔍 Code Workflow
1. Synthetic InSAR Data Generation
Simulates ground deformation (subsidence bowl)

Adds realistic noise & atmospheric effects

Output: DataFrame with [x, y, time, phase, true_deformation]

2. Feature Engineering
Spatial features: Distance from center, angle

Temporal features: Time, time-squared

Neighborhood stats: Mean & std of phase in nearby pixels

3. Machine Learning Model
Random Forest Regressor predicts deformation from phase data

Metrics: Mean Squared Error (MSE), feature importance

4. Anomaly Detection
Isolation Forest flags unusual deformation patterns

Visualized on a scatter plot

5. Excel Export
Exports raw data, predictions, and anomalies

Supports .xls (Excel 97-2003) or .xlsx (modern Excel)

📊 Sample Outputs
1. Synthetic InSAR Phase vs. True Deformation
Phase vs Deformation Plot

2. Anomaly Detection
Anomaly Detection

(Plots are saved if save_plots=True in code)

🛠 Customization
Adjust synthetic data parameters:

python
insar_df = generate_synthetic_insar_data(size=10000, time_steps=8, noise_level=0.2)
Try different ML models:

python
from sklearn.svm import SVR
model = SVR(kernel='rbf')
Export to .xlsx (recommended for large datasets):

python
df.to_excel("results.xlsx", engine='openpyxl')
📜 License
MIT License - Free for academic and commercial use.

📬 Contact
Tarinabo williamtarinabo@gmail.com
