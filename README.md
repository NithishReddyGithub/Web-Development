# Dockerfile – Build & Push to Azure Container Registry (ACR)

This task covers creating a **Dockerfile** for a sample application, building the image locally, and pushing it to **Azure Container Registry (ACR)**.

---

## Files

- [Dockerfile](.Dockerfile)  
- [docker-build-logs.txt](.build.lo)  
- [acr-push-logs.txt](LINK_TO_PUSH_LOGS)  

---

## Steps

### 1. Build Docker Image
```bash
docker build -t <acr_name>.azurecr.io/my-sample-app:latest . | tee docker-build-logs.txt
```

---

## 2. Login to ACR
```bash
az acr login --name <acr_name>
```

---

## 3. Push Image to ACR

```bash
docker push <acr_name>.azurecr.io/my-sample-app:latest | tee acr-push-logs.txt
```

---

## Verification

### Azure CLI
```bash
az acr repository list --name <acr_name> --output table
```

---

## Azure Portal Verification

Navigate to **Container Registry → Repositories** and confirm that the image is available.

📷 - ![Image in Azure Container Registry](.acr-image.png)
