# DevOps CI/CD Kubernetes Demo

This project demonstrates an end-to-end DevOps pipeline.

## Tools Used
- Docker
- Kubernetes
- Jenkins
- AWS (optional deployment)

## Architecture

Developer → GitHub → Jenkins Pipeline → Docker Build → Docker Hub → Kubernetes Deployment

## Application

Simple Flask application deployed in Kubernetes cluster.

## Steps to Run

1. Build Docker image
2. Push to Docker Hub
3. Deploy to Kubernetes using kubectl
4. Access application via NodePort
