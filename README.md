# Kubernetes Tasks Repository  

This repository contains my Kubernetes learning tasks and exercises. Each task covers fundamental Kubernetes concepts and best practices.  

## Task 1: Pods, ReplicaSets, and Deployments  

In this task, I have worked on:  
- **Creating Pods**: Basic unit of deployment in Kubernetes.  
- **ReplicaSets**: Ensuring the desired number of pod replicas run at all times.  
- **Deployments**: Managing updates and rollbacks for applications.
## Task 2: Advanced Kubernetes Objects

### 1. DaemonSet  
### 2. Service - NodePort  
### 3. Service - ClusterIP  
### 4. Static Pods  

## Task 3: Statful-set kubernates
# MySQL StatefulSet with Headless Service in Kubernetes

This project demonstrates how to deploy a **MySQL database** using a **StatefulSet** and a **Headless Service** in Kubernetes.

## 🧠 What is a StatefulSet?

A **StatefulSet** is used for managing stateful applications. It provides:
- Stable, unique network identifiers
- Stable, persistent storage
- Ordered, graceful deployment and scaling

## 🌐 What is a Headless Service?

A **Headless Service** (with `clusterIP: None`) enables direct DNS-based access to individual pods in a StatefulSet. This is essential for databases and clustered services.

---

## 📁 File Structure

- `statefulset-mysql.yaml`: Contains StatefulSet and Headless Service configurations
- `configmap.yaml` *(optional)*: If initialization scripts or config values are needed
- `secret.yaml`: Stores sensitive information like database passwords

---
## Task 4: ConfigMap and SecretKey

# 📦 Kubernetes ConfigMap & Secret Setup

This repository demonstrates how to configure your Kubernetes deployment using:
- **ConfigMaps** for non-sensitive configuration (e.g., logging level, DB URL)
- **Secrets** for sensitive data (e.g., passwords)

---

## 🧾 What You’ll Find

- `configmap.yaml`: Defines general application settings
- `secret.yaml`: Secures sensitive values like database passwords
- `deployment.yaml`: Shows how to use both ConfigMap and Secret as environment variables

---

## ⚙️ Step-by-Step Usage

### 1️⃣ Create the ConfigMap

```yaml
# configmap.yaml
apiVersion: v1
kind: ConfigMap
metadata:
  name: app-config
data:
  DATABASE_URL: jdbc:mysql://mysql-db-0.mysql-headless.default.svc.cluster.local:3306/mydb
  LOG_LEVEL: INFO
  MAX_CONNECTIONS: "100"

```
