# 🌫️ Neighborhood Air – Hyperlocal Air Quality Forecasting Platform

> A scalable web platform that predicts **neighborhood-level air pollution** using satellite observations, ground sensors, and weather data — helping people plan daily activities at safer times instead of relying on inaccurate citywide AQI averages.

---

## ⚠️ Important

All Machine Learning and data processing work is in the **`Machine_learning`** branch.

```bash
git checkout Machine_learning
```

| Notebook | Purpose |
|---|---|
| `tempo_complete_download.ipynb` | Downloads NASA TEMPO satellite data |
| `data_preprocessing.ipynb` | Cleans and merges environmental datasets |
| `air_quality_model.ipynb` | ML forecasting models and evaluation |

---

## 🧩 Problem

Existing AQI apps depend on **few monitoring stations**, which means:

- Pollution can differ **street-to-street**
- City AQI is often **misleading**
- Users **cannot plan** next-day activities
- **No explanation** is provided for pollution spikes

> **Example:** A city AQI of 120 does not mean your specific area has the same air quality.

---

## ✅ Our Solution

We create **hyperlocal pollution forecasts** by fusing multiple environmental data sources.

### Data Sources
- 🛰️ NASA TEMPO satellite observations
- 📡 Ground monitoring stations (EPA / OpenAQ)
- 🌤️ Weather data (NOAA)

### Instead of:
> *"Air quality is poor"*

### We show:
> *"NO₂ spike expected 4–6 PM due to traffic emissions and low wind speed"*

---

## ✨ Features

### 🌍 Hyperlocal Forecasting
Downscales large satellite grids (~10 km) to **street-level predictions** using machine learning.

### 🧠 Explainable Predictions
Shows *why* pollution increases — traffic corridors, weather conditions, industrial activity.

### 🗺️ Interactive Map
Map-based visualization showing local risk levels at a glance.

### 🔔 Personalized Alerts
Pin your **home, office, school, or park** and receive alerts when pollution crosses your thresholds.

### 📅 Daily Planning
Helps you decide the best time to:
- Exercise outdoors
- Commute safely
- Plan outdoor photography or travel

---

## 🏗️ System Architecture

```
Satellite (TEMPO)
       ↓
Ground Sensors (EPA/OpenAQ)
       ↓
Weather Data (NOAA)
       ↓
Data Preprocessing
       ↓
Feature Engineering
       ↓
Machine Learning Forecast
       ↓
Time-Series Database
       ↓
FastAPI Backend
       ↓
Web Dashboard + Alerts
```

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| **Backend** | FastAPI (Python async API), Docker |
| **Database (MVP)** | SQLite |
| **Database (Production)** | TimescaleDB (PostgreSQL) + PostGIS |
| **Data Processing** | xarray + dask, Geopandas, Zarr |
| **Machine Learning** | scikit-learn (Random Forest, Gradient Boosting); Future: PyTorch |
| **Frontend** | Next.js (React), Mapbox, Leaflet |
| **Infrastructure** | Docker, Kubernetes, S3-compatible storage, Prometheus + Grafana |

---

## 🚀 Getting Started

### Prerequisites
- Python 3.10+
- Node.js 18+
- Docker (recommended)
- Git

### 1. Clone the Repository

```bash
git clone https://github.com/<your-username>/<repo-name>.git
cd <repo-name>
```

### 2. Backend Setup

```bash
# Create and activate virtual environment
python -m venv venv

# Windows
venv\Scripts\activate

# Linux / Mac
source venv/bin/activate

# Install dependencies
pip install -r requirements.txt

# Run backend
uvicorn app.main:app --reload
```

API docs available at: `http://localhost:8000/docs`

### 3. Frontend Setup

```bash
cd frontend
npm install
npm run dev
```

Open: `http://localhost:3000`

### 4. Docker (Recommended)

```bash
docker-compose build
docker-compose up
```

---

## 🧪 Machine Learning Workflow

After switching to the `Machine_learning` branch, run notebooks in this order:

1. `tempo_complete_download.ipynb`
2. `data_preprocessing.ipynb`
3. `air_quality_model.ipynb`

**Outputs:** cleaned dataset · trained models · evaluation metrics · prediction results

---

## 📁 Project Structure

```
.
├── app/                # FastAPI backend
├── frontend/           # Next.js frontend
├── data/               # Datasets
├── notebooks/          # Experiments & ML notebooks
├── docker-compose.yml
├── requirements.txt
└── README.md
```

---

## 🗺️ Roadmap

- [ ] SMS & push notifications
- [ ] Exposure tracking dashboard
- [ ] Mobile PWA app
- [ ] Public API (Data-as-a-Service)
- [ ] Institutional dashboard (schools / societies)
- [ ] Advanced ML models (LSTM / GNN)

---

## 🤝 Contributing

1. Fork the repository
2. Create a new branch (`git checkout -b feature/your-feature`)
3. Commit your changes
4. Open a Pull Request

---

## 📄 License

Choose one and add here:
- MIT License
- Apache 2.0
- Proprietary

---

## 📬 Contact

For collaboration, research, or partnership inquiries — **open an Issue** in the repository.
