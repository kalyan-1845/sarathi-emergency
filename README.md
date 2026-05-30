# 🚑 Sarathi — Smart Emergency Navigation System

[![Published Research](https://img.shields.io/badge/Research-IJARSCT%20Journal-0ea5e9?style=for-the-badge&logo=googlescholar)]()
[![Routing Core](https://img.shields.io/badge/Algorithm-Custom%20Dijkstra%20Graph-7c3aed?style=for-the-badge&logo=neo4j)]()
[![Mobile App](https://img.shields.io/badge/Mobile-Flutter%20%7C%20Dart-02569B?style=for-the-badge&logo=flutter)]()
[![Backend](https://img.shields.io/badge/Backend-FastAPI%20%7C%20WebSockets-009688?style=for-the-badge&logo=fastapi)]()

Sarathi is an automated, low-latency emergency vehicle dispatch and navigation system. Designed to minimize first-responder transit times, the system features a topological pathfinding routing engine (Dijkstra algorithm) and real-time WebSocket telemetry to synchronize GPS coordinates between dispatched vehicles and hospital control centers.

> [!NOTE]
> **Published Research**: This project is backed by our published research paper: *"Sarathi: Smart Emergency Navigation System"* | DOI: [10.48175/IJARSCT-32733](https://doi.org/10.48175/IJARSCT-32733).

---

## 🏗️ Telemetry & Routing Architecture

Sarathi coordinates GPS coordinate triangulation and optimal route dispatching in real-time:

```mermaid
graph TD
    Ambulance([Ambulance GPS Module]) -->|Websocket Stream| Backend[Python FastAPI Server]
    Backend --> Router[Dijkstra Pathfinding Engine]
    Router -->|Triangulated Coordinates| Map[Spatial Topology Router]
    Map -->|Optimal Emergency Route| Control[Hospital Dispatch Dashboard]
    Map -->|Live Route Updates| ClientApp[Flutter/Dart Mobile UI]
```

### Technical Specs:
*   **Routing Core**: Custom Dijkstra graph traversal algorithm mapped to actual city coordinates to optimize emergency routing.
*   **Synchronization**: High-performance, low-latency WebSocket connection in FastAPI syncs active vehicle states instantly.
*   **Mobile Interface**: Native client compiled in Flutter (Dart) handles active GPS feed tracking and route rendering.

---

## ⚡ Key Features

*   **Topological Mapping**: Coordinates graph networks using custom distance-matrix weights to bypass heavy traffic.
*   **Triangulation Engine**: Computes coordinate feeds dynamically for live dispatch visualization.
*   **Interactive Dispatcher Dashboard**: Real-time admin control panel monitoring active alerts and available routes.
*   **Low-Latency WebSockets**: Maintains continuous bi-directional tracking under 80ms delay.

---

## 🛠️ Local Installation & Setup

### Prerequisites
*   **Node.js / npm** (for web dashboard)
*   **Python**: v3.10 or higher (for backend)
*   **Flutter SDK**: [Download Flutter](https://docs.flutter.dev/get-started/install) (for mobile app)

### Installation Steps

1.  **Clone the Repository**:
    ```bash
    git clone https://github.com/kalyan-1845/sarathi-emergency.git
    cd sarathi-emergency
    ```

2.  **Start Python Backend (FastAPI)**:
    ```bash
    cd backend
    python -m venv venv
    source venv/bin/activate  # On Windows: venv\Scripts\activate
    pip install -r requirements.txt
    uvicorn main:app --host 0.0.0.0 --port 8000
    ```

3.  **Run Mobile App (Flutter)**:
    ```bash
    cd ../mobile
    flutter pub get
    flutter run
    ```

---

## 📄 Research Reference

If you use or reference our routing architecture, please cite our paper:
*   **Title**: *Sarathi: Smart Emergency Navigation System*
*   **Journal**: International Journal of Advanced Research in Science, Communication and Technology (IJARSCT)
*   **Paper URL**: [Sarathi Official Paper PDF](https://github.com/kalyan-1845/Sarathi-Official-researcher/blob/main/Sarathi-Official-Paper.pdf)