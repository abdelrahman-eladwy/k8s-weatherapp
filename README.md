🌦️ Weather App with Kubernetes (k8s-weatherapp)

A scalable, cloud-native weather application built with Flask (Python) backend, React frontend, Redis for caching, and deployed on Kubernetes.

Demo (Consider adding a screenshot or GIF here!)
📌 Features

    Real-time weather data from OpenWeatherMap API.

    Caching with Redis to reduce API calls and improve performance.

    React frontend for a responsive UI.

    Kubernetes-managed for scalability and resilience.

    Helm charts for easy deployment.

🏗️ Architecture
Copy

├── backend/           # Flask app (Weather API)  
├── frontend/          # React app (UI)  
├── k8s/               # Kubernetes manifests  
├── helm/              # Helm charts for deployment  
├── docker-compose.yml # Local development  
└── README.md  

⚙️ Prerequisites

    Tools:

        kubectl (Kubernetes CLI)

        minikube (or a Kubernetes cluster)

        docker

        helm (for Helm deployments)

    API Key:

        Sign up for a free OpenWeatherMap API key.

🚀 Deployment
Option 1: Kubernetes (Minikube)

    Start Minikube:
    sh
    Copy

    minikube start  

    Deploy Redis:
    sh
    Copy

    kubectl apply -f k8s/redis-deployment.yaml  
    kubectl apply -f k8s/redis-service.yaml  

    Deploy Backend & Frontend:
    sh
    Copy

    kubectl apply -f k8s/backend-deployment.yaml  
    kubectl apply -f k8s/frontend-deployment.yaml  

    Access the App:
    sh
    Copy

    minikube service frontend-service --url  

Option 2: Helm
sh
Copy

helm install weather-app helm/weather-app  

Option 3: Docker Compose (Local Dev)
sh
Copy

docker-compose up --build  

Access: http://localhost:3000 (Frontend) | http://localhost:5000 (Backend)
🔧 Configuration

Set environment variables in k8s/configmap.yaml or .env (for local dev):
ini
Copy

OPENWEATHER_API_KEY=your_api_key  
REDIS_URL=redis://redis-service:6379  

📂 Repository Structure
Directory	Purpose
backend/	Flask API (fetches weather data)
frontend/	React UI (displays weather)
k8s/	Kubernetes manifests
helm/	Helm charts for deployments
🤝 Contributing

    Fork the repo.

    Create a branch (git checkout -b feature/your-feature).

    Commit changes (git commit -m "Add feature").

    Push (git push origin feature/your-feature).

    Open a PR.

📜 License

MIT
Notes:

    Customize: Replace placeholder text (e.g., your_api_key) with actual values.

    Screenshot: Add a demo image/GIF for better visuals.

    Helm: If Helm charts are incomplete, mention it or guide users to customize values.yaml.
