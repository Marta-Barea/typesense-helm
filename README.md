# 🌐 Typesense Helm Chart

## 📌 Overview

This Helm chart deploys [Typesense](https://typesense.org/), an open-source, fast, and typo-tolerant search engine, onto a Kubernetes cluster.

- 🌐 [Official Website](https://typesense.org/)
- 💡 [GitHub Repository](https://github.com/typesense/typesense)

---

## 🛠 Prerequisites

- Helm v3.x
- Kubernetes v1.16+
- Persistent Volume (PV) provisioner support in the underlying infrastructure

---

## 🚀 Installation

To add the Typesense repository and install the chart with the release name `my-release`, run:

```bash
$ helm repo add springboard https://marta-barea.github.io/typesense-helm/
$ helm install my-release typesense/typesense -n [namespace]
```

---

## ⚙️ Configuration

### 🐳 Docker Image

- **Repository**: `docker.io/typesense/typesense`
- **Tag**: `0.25.0`
- **Pull Policy**: `IfNotPresent`

### 🎛 Resources

- **CPU and Memory**: No limits or requests specified by default.

### 💽 Persistence

- **Enabled**: Yes
- **Path**: `/data`
- **Access Mode**: `ReadWriteOnce`
- **Size**: `25Gi`

---

## 🗄 StatefulSet Configuration

- **Replicas**: 3
- **Application Port**: 8108

#### 🩺 Health Checks

- **Liveness Probe**: Starts after 60 seconds, times out after 5 seconds.
- **Readiness Probe**: Starts after 10 seconds, times out after 3 seconds.

---

## 📡 Service Configuration

- **Service Type**: Configurable (`ClusterIP` by default)
- **Service Port**: Configurable (80 by default)

---

## 🙏 Contribute

If you find this project helpful, please consider starring it on GitHub!

