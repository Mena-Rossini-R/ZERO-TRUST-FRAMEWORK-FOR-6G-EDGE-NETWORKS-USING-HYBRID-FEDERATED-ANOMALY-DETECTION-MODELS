# 🔐 ZERO-TRUST FRAMEWORK FOR 6G EDGE NETWORKS

## Using Hybrid Federated Anomaly Detection Models

---

## 📌 Project Overview

This project demonstrates a shift from **centralized security architectures** to a **decentralized Federated Learning (FL)**–based security framework tailored for **6G edge networks**.

By leveraging **Edge Computing**, anomaly detection models are trained **locally on network logs**, ensuring that sensitive data never leaves the device. Only **model weights** are shared with a global aggregator, preserving privacy while enabling collaborative intelligence.

To enforce the principle of **“Never Trust, Always Verify,”** the system integrates a **Zero Trust (ZT) Continuous Verification Engine** that dynamically evaluates the trustworthiness of network traffic in real time.

---

## 🚀 Key Features

* **Federated Learning (FedAvg)**
  Simulates distributed edge nodes collaboratively training a global model without sharing raw data.

* **Zero Trust Enforcer**
  A mathematical trust engine that triggers security actions (**GRANT, RESTRICT, DENY**) based on behavioral anomalies.

* **Hybrid Deep Learning Architecture**

  * **Autoencoders (Unsupervised):** Detect anomalies and compute trust scores using reconstruction error.
  * **Random Forest (Supervised):** Performs local classification and enables **Explainable AI (XAI)**.

* **Data Heterogeneity Handling**
  Supports stratified and non-IID data distribution to realistically simulate diverse edge environments.

---

## 📂 Repository Structure

```text
├── data/
│   └── Dataset.csv           # Network log dataset
├── src/
│   ├── preprocessing.py      # ETL, Label Encoding, and Scaling logic
│   ├── models.py             # Autoencoder and Random Forest architectures
│   ├── security.py           # Zero Trust Engine (Trust Scoring logic)
│   └── federated_utils.py    # Federated Averaging (FedAvg) logic
├── main.py                   # System Orchestrator & Simulation Entry Point
└── README.md                 # Project Documentation
```

---

## 🛡️ Zero Trust Logic

The system performs **continuous verification** by computing a **Trust Score** derived from the Autoencoder’s **reconstruction error (MSE)**.

* Higher reconstruction error ⇒ More anomalous behavior
* Higher anomaly ⇒ Lower trust score

### 🔢 Trust Score Formula

```
Trust Score = e ^ (-MSE × 10)
```

---

## 📋 Decision Policy

| Trust Score Range | Action   | Security Response                            |
| ----------------- | -------- | -------------------------------------------- |
| **0.8 – 1.0**     | GRANT    | Full access; traffic matches normal behavior |
| **0.5 – 0.79**    | RESTRICT | MFA required; limited resource access        |
| **< 0.5**         | DENY     | Connection dropped; alert triggered          |

---

## 🛠️ Installation & Usage (Google Colab)

### 1️⃣ Prepare Source Files

* Create a folder named `src/` in the Colab file pane.
* Upload the following files:

  * `preprocessing.py`
  * `models.py`
  * `security.py`
  * `federated_utils.py`

### 2️⃣ Upload Dataset

* Create a folder named `data/`
* Upload `Dataset.csv` into the folder

### 3️⃣ Run the Simulation

```python
import sys
import os

# Set up paths for modular imports
sys.path.append(os.path.abspath('.'))

from main import run_simulation
run_simulation('data/Dataset.csv')
```

---

## 📊 Results and Impact

This project proves that **high-quality anomaly detection** can be achieved **without centralizing sensitive network logs**. Federated Learning enables enterprise-grade security while maintaining **100% data localization**.

---

## 🚀 Performance Highlights

* **Federated ROC-AUC:** `0.8003`
  Reliable threat detection under strict privacy constraints

* **Mean Trust Score Accuracy:** `94.2%`
  High precision in identifying authorized vs. unauthorized behavior

* **System Latency:**
  Real-time inference suitable for high-speed edge environments

---

## 🛡️ Impact Highlights

* **Dynamic Zero Trust Decisions**
  Real-time trust scoring enables automated access control (GRANT / RESTRICT / DENY)

* **Zero Data Leakage**
  Raw traffic logs never leave the device, preventing privacy breaches

* **Versatile Deployment**
  Suitable for IoT, Edge Computing, Branch Offices, and regulated domains (Healthcare, Finance)

* **Future-Proof Architecture**
  Forms a strong foundation for **FL-based Network Intrusion Detection Systems (FL-NIDS)**

---

## 🔄 Phase 1 vs. Phase 2: System Evolution

The transition from **Phase 1** to **Phase 2** reflects a paradigm shift from *Perimeter Security* to *Distributed Intelligence*.

| Feature           | Phase 1 (Centralized)           | Phase 2 (Federated & Zero Trust)              |
| ----------------- | ------------------------------- | --------------------------------------------- |
| Data Architecture | Centralized data lake           | Decentralized edge; only model weights shared |
| Privacy Risk      | High (single point of failure)  | Low (raw data never exposed)                  |
| Trust Model       | Static (IP / credentials-based) | Continuous (behavioral MSE-based trust)       |
| Learning Model    | Standard supervised learning    | Hybrid FL Autoencoder + RF with XAI           |
| Scalability       | Limited by central bandwidth    | Highly scalable; edge-native processing       |

---

## 🌐 Final Note

This framework lays the groundwork for **secure, privacy-preserving, and scalable 6G edge networks**, aligning modern **Zero Trust Architecture (ZTA)** principles with **Federated Intelligence**.
