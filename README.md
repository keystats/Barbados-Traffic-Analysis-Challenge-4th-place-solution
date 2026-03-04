# 🚦 Barbados Traffic Flow Predictor 
### *Winning "Best Factors Affecting Traffic" in the Zindi Challenge*

[![Zindi Competition](https://img.shields.io/badge/Zindi-Barbados_Traffic_Analysis_Challenge-1ebba3)](https://zindi.africa/competitions/barbados-traffic-analysis-challenge) <!-- Placeholder link, replace with actual -->
[![Team](https://img.shields.io/badge/Team-Traffic_Solvers-blueviolet)](#)
[![Award](https://img.shields.io/badge/Award-Best_Factors_Affecting_Traffic-gold)](#)

[![Python](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/)
[![CatBoost](https://img.shields.io/badge/CatBoost-🐈-orange)](https://catboost.ai/)
[![XGBoost](https://img.shields.io/badge/XGBoost-⚡-green)](https://xgboost.readthedocs.io/)
[![OpenCV](https://img.shields.io/badge/OpenCV-👁️-red)](https://opencv.org/)

---

## 🌟 The Mission
On the beautiful island of Barbados, traffic congestion affects every citizen. The Ministry of Transport and Works challenged data scientists to predict traffic flow at the **Norman Niles Roundabout** and, most importantly, **identify the *root causes*** of congestion.

Our team, **Traffic Solvers ([NYMFREE](https://zindi.africa/users/nymfree) & [KEYSTATS](https://zindi.africa/users/keystats))**, took on this challenge. We didn't just build a model; we built a **discovery engine**.

> **Result:** 🥈 **4th Place** on the Private Leaderboard (Score: **0.7146**) & 🏆 **Winner of "Best Factors Affecting Traffic"** Award!

---

## 🗺️ Our 7-Step Journey: From Pixels to Policy

We broke down the complex problem into seven powerful notebooks, each a chapter in our story.

### **Notebook 1: 🧹 The Foundation (Data Cleaning)**
*   **Goal:** Turn fragmented video clips into a smooth, continuous timeline.
*   **Why:** You can't predict the future if your past is broken! We identified and filtered for continuous sequences, creating a pristine dataset of **9,014 high-quality observations**.

### **Notebook 2: 🎥 The Eyes (Video Feature Extraction)**
*   **Goal:** Extract vehicle movement from 130+ GB of video.
*   **How:** We used **parallel processing** (16 notebooks running at once!) and computer vision (OpenCV) to extract:
    *   `Vehicle_Count` | `Avg_Speed_kmh` | `Speed_Range_kmh`
    *   This turned raw footage into structured traffic data.

### **Notebook 3: ☀️ The Atmosphere (Environmental Context)**
*   **Goal:** Understand how the environment affects traffic.
*   **Innovation:** We analyzed video **brightness** to capture:
    *   Day vs. Night patterns
    *   Tropical weather (rain, fog)
    *   This feature became a **top 5 congestion driver (11.1% importance)**!

### **Notebook 4: 🧩 The Unifier (Feature Integration)**
*   **Goal:** Merge all our hard-won features into one master dataset.
*   **Result:** A unified matrix ready for machine learning magic.

### **Notebook 5: 🔄 The Transformer (Data Reshaping)**
*   **Goal:** Format data perfectly for the competition.
*   **Action:** Separated entry/exit flows and standardized everything, creating final train/test files.

### **Notebook 6: 🧪 The Lab (Advanced Traffic Science)**
*   **Goal:** Create sophisticated indicators based on traffic flow theory.
*   **Our Creations:**
    *   `Traffic Progression` | `Shockwave Index` | `State Gate` | `Dwell Time`
*   **Critical Lesson:** These features were **brilliant for *explaining* congestion** (which won us the award!), but we discovered something crucial in the next step...

### **Notebook 7: 🏆 The Winner (The Temporal Model)**
*   **Goal:** Build our highest-performing prediction model.
*   **The Pivotal Discovery:** ⏰ **Time patterns dominate traffic prediction!** Our complex traffic science features were great for understanding, but for pure prediction, time-based features were king.
*   **Our Winning Formula:**
    *   **XGBoost** (600 trees) + **CatBoost** (3000 iterations)
    *   **Key Features:** `hour_x_location`, `hour_squared`, `hour_sin/cos`
    *   **Blended Ensemble (50/50)** for the final, robust prediction.
*   **Final Score:** **0.7146** on the Private Leaderboard.

---

## 🔑 Key Insights: What's Really Causing Traffic in Barbados?

Our analysis, which earned us the **"Best Factors"** award, revealed the true culprits:

| Rank | Feature | Importance | The Root Cause |
| :--- | :--- | :--- | :--- |
| **1** | `hour_x_location` | 9.6% | **Specific roads get clogged at specific times.** (e.g., Norman Niles #3 vs. #1). |
| **2** | `hour_squared` | 14.2% | **Rush hours create exponential congestion.** It's not linear! |
| **3** | `Avg_Brightness` | 11.1% | **Mother Nature plays a role.** Weather and light/dark cycles matter. |
| **4** | `Dwell_adj` | 11.5% | **Vehicles are spending too long *inside* the roundabout.** This is a key efficiency metric. |
| **5** | `Traffic Signaling` | 10.6% | **Control systems have a huge impact.** Getting signaling right is critical. |

---

## 📢 Our Recommendations to the Barbados Ministry

Based on our data, here’s how to make a real difference:

*   **🚦 Dynamic Signal Timing:** Adjust traffic lights based on our `hour_x_location` findings. Don't use a one-size-fits-all schedule!
*   **🌦️ Weather-Ready Roads:** Have plans for when brightness drops (rain, dusk). Drivers behave differently.
*   **🎯 Targeted Interventions:** Focus on the specific approaches (`location_squared`) that show the most stress.
*   **🗣️ Public Awareness:** Tell citizens *when* and *where* congestion is worst, so they can plan.

---

## 🛠️ Tech Stack & Tools

*   **Languages:** `Python`
*   **Libraries:** `CatBoost`, `XGBoost`, `OpenCV`, `Pandas`, `NumPy`, `Scikit-learn`
*   **Core Concepts:** Computer Vision, Time-Series Analysis, Ensemble Modeling, Feature Engineering, Traffic Flow Theory

---

## 👥 The Team

*   **[KEYSTATS](https://zindi.africa/users/keystats)**  
*   **[NYMFREE](https://zindi.africa/users/nymfree)** 

---

## ✨ Final Thought

This project was more than a competition. It was a **blueprint for smarter traffic management**. We proved that by combining data science with a genuine desire to understand a problem, you can create insights that improve people's daily lives.

**From raw video to real-world impact.** ❤️

---
⭐ **If you find this work interesting, drop a star!** Feel free to explore the notebooks and reach out with questions.
