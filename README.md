# 🚀 Go Web App — Customized & Deployed with ArgoCD & Kubernetes

This project is a customized fork of [iam-veeramalla/go-web-app](https://github.com/iam-veeramalla/go-web-app), modified and deployed as a complete CI/CD pipeline using Docker, Helm, Kubernetes, and ArgoCD.

---

## 🧱 Based On

> 🔗 Forked from: [iam-veeramalla/go-web-app](https://github.com/iam-veeramalla/go-web-app)

The original project is a lightweight Go HTTP web server. This fork adds:
- Custom HTML pages
- Docker image build & push
- Helm chart packaging
- Kubernetes deployment
- GitOps pipeline with ArgoCD

---

## 🛠 Tech Stack

| Tool        | Purpose                         |
|-------------|----------------------------------|
| **Go**      | Backend web server              |
| **Docker**  | Containerization                |
| **Helm**    | Kubernetes packaging             |
| **K8s**     | Orchestration (Minikube local) |
| **ArgoCD**  | GitOps-style CD pipeline        |
| **GitHub Actions** | Linting and CI (optional) |

---

## 🗂 Project Structure
```yaml
.
├── main.go # Go Web Server
├── static/ # HTML pages
├── Dockerfile # Container definition
├── go-web-app-chart/ # Helm chart
│ └── templates/
│ └── values.yaml
├── k8s/manifest/ # Raw Kubernetes YAMLs 
└── README.md
```

---

## 🐳 Docker Build & Push

```bash
docker build -t byisrar/golang:v2 .
docker push byisrar/golang:v2
```
## ☸️ Helm Installation (Kubernetes)
```
helm install go-web-app ./go-web-app-chart
```
## Upgrade when needed:
```
helm upgrade go-web-app ./go-web-app-chart
```
## 🔁 Deploy with ArgoCD

- Push repo to GitHub (make public/private as needed)

- In ArgoCD UI:

  - Create App

  - Git URL → this repo

  - Path → go-web-app-chart/

  - Sync manually or auto

- Done! CD enabled 🔁

## 🌐 Accessing the App

Enable Ingress addon:
```
minikube addons enable ingress
```
Get Minikube IP:
```
minikube ip
```
Update /etc/hosts:
```
<minikube-ip>  go-lang.local
```
Access in browser:
```
http://go-lang.local/home
http://go-lang.local/about
```

## ✨ Sample Routes in Go
```yaml
http.HandleFunc("/home", homePage)
http.HandleFunc("/courses", coursePage)
http.HandleFunc("/about", aboutPage)
http.HandleFunc("/contact", contactPage)
```
## 🔐 Image Info (values.yaml)
```yaml
image:
  repository: byisrar/golang
  tag: v2
```

## 📸 Screenshots
![image](https://github.com/user-attachments/assets/8590f9e0-a25a-4b53-9ca7-2c1124c194d5)
![image](https://github.com/user-attachments/assets/38f598d9-f499-40b2-a1e1-78f038012b42)

## 🙋‍♂️ Author
Customized and deployed by @Israr8

## 📄 License
MIT License — Forked from iam-veeramalla/go-web-app






















