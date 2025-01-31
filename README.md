# Multi-Modal Deep Learning for Solar Flare Prediction  
## Integrating GOES, SDO/HMI, AIA, and DSCOVR Data  

## 🚀 Plan to Build the Model  

### 1️⃣ Data Collection (Using SunPy & HelioPy)  
We will collect:  
- ✅ **GOES X-ray flux** (flare intensity).  
- ✅ **SDO/HMI magnetograms** (magnetic field changes).  
- ✅ **SDO/AIA UV/EUV images** (solar region brightness).  
- ✅ **DSCOVR solar wind data** (external influence).  

**Libraries:** `sunpy`, `heliopy`, `astropy`, `requests`  

---

### 2️⃣ Preprocessing  

#### 🔹 Time-Series Data (GOES, DSCOVR)  
- ✅ Normalize values using **MinMaxScaler**.  
- ✅ Convert into **sequences** for LSTM.  

#### 🔹 Solar Images (SDO/HMI, AIA)  
- ✅ Convert **FITS files** to NumPy arrays.  
- ✅ Resize images for CNN input.  
- ✅ Apply **CLAHE** (if needed) to enhance features.  

---

### 3️⃣ Model Architecture (CNN + LSTM)  

#### 🔹 CNN for Solar Images (HMI/AIA)  
- ✅ Extract **spatial features** (sunspot size, brightness).  

#### 🔹 LSTM for Time-Series Data (GOES/DSCOVR)  
- ✅ Learn **historical patterns** in X-ray flux & solar wind.  

#### 🔹 Fusion Layer + Dense Layers  
- ✅ Combine **CNN + LSTM outputs** → Fully Connected Layers → Predict flare probability.  

---

### 4️⃣ Model Training & Evaluation  
- ✅ Use **IM-BALANCED dataset handling** (SMOTE, class weighting).  
- ✅ Evaluate using **Precision-Recall, F1-score** (flare events are rare).  
- ✅ Compare **CNN+LSTM vs. Baseline (only GOES LSTM)**.  

---

### 5️⃣ Real-Time Predictions & Visualization  
- ✅ Deploy as **Flask/FastAPI API**.  
- ✅ Show **real-time SunPy plots & alerts**.  
- ✅ Visualize **feature importance using SHAP**.  
