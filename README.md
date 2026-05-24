# AUY1104-SharedApache

Apache HTTP Server desplegado en k3s via CI/CD con GitHub Actions y Docker Hub.

## Servicio

Expuesto en `http://<IP_PUBLICA>:30100`

## Secrets requeridos en GitHub

| Nombre | Descripción |
|--------|-------------|
| `DOCKER_USERNAME` | Usuario Docker Hub |
| `DOCKER_PASSWORD` | Token Docker Hub |
| `EA2_SSH_PRIVATE_KEY` | Llave SSH privada para conectar a la VM k3s |

## Variables requeridas en GitHub

| Nombre | Descripción |
|--------|-------------|
| `K3S_SERVER_PUBLIC_IP` | IP pública de la VM con k3s |

## Despliegue manual

```bash
# Aplicar manifiestos directamente
kubectl apply -f k8s/
```

## Rollback

```bash
kubectl rollout undo deployment/apache-server
```
