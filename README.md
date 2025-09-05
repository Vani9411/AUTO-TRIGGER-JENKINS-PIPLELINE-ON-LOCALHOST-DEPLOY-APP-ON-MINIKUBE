# AUTO-TRIGGER-JENKINS-PIPLELINE-ON-LOCALHOST-DEPLOY-APP-ON-MINIKUBE

🚀 Auto Trigger Jenkins Pipeline on Windows Localhost & Deploy App on Minikube

📌 Project Overview

This project demonstrates how to build a fully automated Continuous Integration and Continuous Deployment (CI/CD) pipeline using Jenkins on a Windows localhost environment. The pipeline automatically triggers whenever new code is pushed to a GitHub repository and takes care of the entire process from building the application to deploying it into a Kubernetes cluster running on Minikube.

It provides a hands-on simulation of real-world DevOps practices, where automation reduces manual intervention, increases deployment speed, and ensures consistency across environments.


---

🛠 Tools & Technologies Used

⚙️ Jenkins – Automation server used to create and manage the CI/CD pipeline

🧑‍💻 Git & GitHub – For version control and source code hosting

🐳 Docker – To build containerized applications

📦 DockerHub – To store and share Docker images remotely

☸️ Minikube – Lightweight Kubernetes cluster for local testing

💻 kubectl – CLI to interact with Kubernetes clusters

🖥️ Windows 10/11 – Localhost platform to run Jenkins and Minikube



---

⚙️ Project Workflow (Step-by-Step)

🔹 1. Install and Configure Tools

📥 Install Git for version control.
🐳 Install Docker Desktop and enable Kubernetes support if required.
⚙️ Install Jenkins on Windows and start it as a service.
☸️ Install Minikube and kubectl for Kubernetes deployment.
🔑 Configure GitHub and DockerHub accounts.


---

🔹 2. Setup Jenkins on Windows

🌐 Launch Jenkins on http://localhost:8080.

📦 Install necessary plugins:

🔹 Git Plugin

🔹 Pipeline Plugin

🔹 Docker Pipeline Plugin

🔹 Kubernetes CLI Plugin


🔑 Configure Jenkins credentials for GitHub and DockerHub.
✅ Verify Jenkins has access to Docker and kubectl commands.


---

🔹 3. Connect Jenkins with GitHub

🔗 Go to GitHub repository settings → Add a Webhook pointing to Jenkins:

http://<localhost-ip>:8080/github-webhook/

🔔 Select “Push Events” so Jenkins is triggered automatically when code is pushed.
🚀 This ensures continuous integration is achieved.


---

🔹 4. Pipeline Stages Explanation

The pipeline consists of multiple stages:

1️⃣ Checkout Code – Jenkins fetches the latest source code from GitHub.
2️⃣ Build Application – The application is compiled and packaged.
3️⃣ Containerization – A Docker image is created for the application.
4️⃣ Push to DockerHub – The Docker image is uploaded to DockerHub.
5️⃣ Deploy to Minikube – Kubernetes manifests are applied using kubectl.
6️⃣ Verification – Jenkins confirms that the app is running successfully.


---

🔹 5. Deploy Application on Minikube

▶️ Start Minikube cluster locally.
📄 Apply Kubernetes Deployment and Service manifests.
🔎 Check pods and services to confirm application is running.
🌐 Access the app via Minikube service URL.


---

🔹 6. Project Structure

📂 A standard project setup includes:

.
├── Jenkinsfile       # Defines the pipeline workflow
├── Dockerfile        # Defines how the Docker image is built
├── deployment.yaml   # Kubernetes deployment configuration
├── service.yaml      # Kubernetes service configuration
└── src/              # Application source code


---

🏗️ Project Architecture

🧑‍💻 Developer
               │
        (Push Code to GitHub)
               │
               ▼
         🌐 GitHub Repo
               │
       (Webhook Trigger)
               │
               ▼
          ⚙️ Jenkins CI/CD
     ┌─────────────────────────────┐
     │ 1. Checkout Code            │
     │ 2. Build Application        │
     │ 3. Create Docker Image      │
     │ 4. Push Image to DockerHub  │
     │ 5. Deploy on Minikube       │
     └─────────────────────────────┘
               │
               ▼
        🐳 DockerHub Registry
               │
               ▼
        ☸️ Minikube Cluster
     ┌─────────────────────────────┐
     │ Kubernetes Deployment +     │
     │ Service running the app     │
     └─────────────────────────────┘
               │
               ▼
          🌍 End User Access


---

🔹 7. Monitoring and Verification

📊 Use Jenkins dashboard to monitor pipeline execution.
🐳 Verify DockerHub to confirm image push.
☸️ Run:

kubectl get pods
kubectl get svc

to check application status.
🌍 Access the application URL from Minikube to confirm deployment.


---

🧹 Cleanup Process

When testing is complete:
❌ Delete Kubernetes deployments and services.
🛑 Stop the Minikube cluster.
🧽 Remove local Docker images if not needed.

👉 This prevents unnecessary resource usage and keeps the environment clean.


---

🏁 Conclusion

This project demonstrates how to implement a complete DevOps lifecycle on Windows, starting from a code push on GitHub to automated deployment on Kubernetes.

By integrating ⚙️ Jenkins, 🧑‍💻 GitHub, 🐳 Docker, 📦 DockerHub, and ☸️ Minikube, the pipeline ensures smooth, automated, and reliable deployments. This setup is ideal for learning and practicing DevOps concepts as it simulates how CI/CD pipelines function in real-world organizations.

