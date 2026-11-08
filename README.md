# PulseSim — Monte Carlo Based System Reliability & Performance Prediction

**An ML-powered system reliability simulator that uses Monte Carlo simulations and Random Forest models to estimate application performance, latency, and failure risk under different traffic conditions.**

## Overview

PulseSim is a software engineering and machine learning project designed to simulate how backend systems behave under different workloads.

Modern applications experience changing traffic, server overload, and unexpected failures. PulseSim addresses this problem by generating thousands of simulated system scenarios using the **Monte Carlo method** and applying Machine Learning to predict performance and reliability.

The platform allows users to configure system parameters, execute simulations, analyze performance metrics, and visualize potential reliability risks through an interactive dashboard.

## Problem Statement

Backend systems must remain reliable even when traffic increases or infrastructure components fail.

Traditional testing may not cover every possible combination of traffic spikes, server failures, and resource utilization.

PulseSim uses probabilistic simulation to explore different possible operating conditions and estimate the risk of performance degradation.

## Key Features

- **Monte Carlo Simulation:** Generates thousands of randomized system scenarios.
- **Traffic Spike Simulation:** Models sudden increases in incoming requests.
- **Server Failure Simulation:** Evaluates the impact of server unavailability.
- **Latency Analysis:** Estimates response times under different workloads.
- **SLO Violation Estimation:** Calculates the probability of exceeding a configured latency target.
- **Machine Learning Prediction:** Uses Random Forest models to predict system performance.
- **Interactive Dashboard:** Displays simulation results and performance metrics.
- **Performance Visualization:** Presents latency, utilization, and reliability statistics through charts.

## How It Works

1. The user configures the system parameters through the dashboard.
2. The frontend sends the configuration to the backend API.
3. The Monte Carlo engine generates multiple randomized scenarios.
4. Each scenario is evaluated for traffic conditions, server availability, and performance.
5. The simulation calculates latency and reliability metrics.
6. Random Forest models analyze the generated data and make predictions.
7. The backend returns the results to the frontend.
8. The dashboard visualizes the final performance analysis.

## Monte Carlo Method

Monte Carlo simulation is a statistical technique that uses repeated random sampling to estimate the probability of different outcomes.

PulseSim uses this method to simulate different combinations of:

- Incoming request volume
- Traffic spike probability
- Server failure probability
- Available server capacity
- Workload intensity

For example, if 2,000 out of 10,000 simulated scenarios exceed the configured latency threshold:

\[
P(\text{SLO Violation})=\frac{2000}{10000}\times100=20\%
\]

The estimated SLO violation probability is 20%.

## Machine Learning Approach

PulseSim incorporates Random Forest algorithms for predictive analysis.

**Random Forest Classifier**
- Predicts whether a system configuration is likely to violate its latency objective.
- Uses simulation-generated data for training.

**Random Forest Regressor**
- Predicts performance metrics such as P95 latency.
- Helps estimate system response under different configurations.

The models use synthetic simulation data in this academic prototype. Their predictions should not be interpreted as production guarantees.

## Performance Metrics

| Metric | Description |
|---|---|
| Average Latency | Average response time |
| P95 Latency | Response time below which 95% of requests complete |
| Server Utilization | Percentage of available server capacity being used |
| SLO Violation Risk | Percentage of scenarios exceeding the latency objective |
| Failure Probability | Estimated probability of server failure |

## Technology Stack

| Technology | Purpose |
|---|---|
| Python | Simulation and backend logic |
| FastAPI | Backend REST API |
| React | Interactive frontend |
| NumPy | Random sampling and numerical calculations |
| Pandas | Data processing |
| Scikit-learn | Machine Learning models |
| Recharts | Data visualization |

## Project Architecture

```text
PulseSim/
│
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   ├── pages/
│   │   └── App.jsx
│   ├── package.json
│   └── index.html
│
├── backend/
│   ├── app/
│   │   ├── main.py
│   │   ├── simulation.py
│   │   ├── model.py
│   │   └── routes/
│   ├── requirements.txt
│   └── .venv/
│
└── README.md
```

*Note: The structure above describes the intended organization. Adjust filenames to match the actual repository.*

## Installation and Setup

### Prerequisites

- Python 3.11 or later (a compatible Python version is recommended)
- Node.js and npm
- Visual Studio Code

### 1. Clone the Repository

```bash
git clone <YOUR_GITHUB_REPOSITORY_URL>
cd PulseSim
```

### 2. Backend Setup

```bash
cd backend
python -m venv .venv
```

Activate the virtual environment on Windows:

```powershell
.\.venv\Scripts\Activate.ps1
```

Install dependencies:

```bash
python -m pip install -r requirements.txt
```

Start the backend:

```bash
python -m uvicorn app.main:app --reload
```

Backend API:

```text
http://127.0.0.1:8000
```

API documentation:

```text
http://127.0.0.1:8000/docs
```

### 3. Frontend Setup

Open a separate terminal:

```bash
cd frontend
npm install
npm run dev
```

Frontend development server:

```text
http://localhost:5173
```

## Applications

- Backend infrastructure capacity planning
- Application reliability analysis
- Workload and traffic simulation
- Performance engineering experiments
- Predictive system monitoring research
- Software reliability education

## Future Enhancements

- Real-time monitoring using application telemetry
- Integration with Prometheus and Grafana
- Redis-based caching and workload simulation
- Distributed server failure simulation
- Automated capacity recommendations
- Advanced predictive models
- Containerized deployment using Docker

## Limitations

PulseSim is an academic prototype that uses simulated workloads and probabilistic assumptions. Its results depend on the assumptions and training data used. It does not currently represent actual production infrastructure measurements or guarantee real-world application performance.

## Learning Outcomes

This project demonstrates the practical application of:

- Monte Carlo simulation
- Probability and statistical modelling
- Machine Learning classification and regression
- REST API development
- Full-stack application architecture
- Performance and reliability engineering
- Data visualization

## Author

**Yashika Nanda**

B.Tech — Electronics and Communication Engineering

## License

This project is intended for academic and educational purposes. Add an appropriate open-source license before distributing it publicly.
