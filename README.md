# Algorithmic_Trading_Strategy_Agent# 📈 Algorithmic Trading Strategy Agent (LSTM + DSP)

### **Overview**
This project implements a professional-grade automated trading agent designed for high-volatility financial markets. By integrating **Digital Signal Processing (DSP)** with **Deep Learning**, the system filters stochastic market noise to identify high-probability price action signals.

---

### **🏛️ Architecture & Motivation**
The architecture of this bot is inspired by my experience in **Medical Sensor Technology at Centronix (Hyderabad)**. I observed that biological sensor data and financial market data share a common challenge: a low **Signal-to-Noise Ratio (SNR)**.

#### **The Pipeline:**
1. **Denoising (Kalman Filter):** Raw price data is treated as a noisy observation of a hidden state. A recursive Kalman Filter is applied to estimate the "True Trend," effectively reducing market "jitter" without the latency found in traditional Moving Averages.
2. **Sequential Modeling (LSTM):** A stacked **Long Short-Term Memory** network processes the denoised signal. This architecture is chosen specifically to mitigate the **Vanishing Gradient** problem, allowing the model to remember long-term market regimes.
3. **MLOps Structure:** Built using a modular factory pattern, separating Data Ingestion, DSP Components, and Model Training for production scalability.



---

### **🚀 Tech Stack**
* **Languages:** Python 3.x
* **DSP & Math:** `pykalman`, `NumPy`, `SciPy`
* **Deep Learning:** `TensorFlow` / `Keras` (LSTM)
* **Data & Deployment:** `yfinance`, `Pandas`, `Streamlit`

---

### **📁 Project Structure**
```text
├── artifacts/               # Trained models and scalers
├── data/                    # Historical market datasets (CSV)
├── src/
│   └── TradingBot/
│       ├── components/      # Modular logic (Ingestion, DSP, LSTM)
│       ├── pipeline/        # Training and Prediction workflows
│       └── utils/           # Common helper functions
├── app.py                   # Streamlit Frontend for visualization
└── main.py                  # Pipeline controller