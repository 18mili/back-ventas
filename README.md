# 💰 Backend Ventas — Innovatech Chile

API REST para gestión de ventas con **Java Spring Boot + MySQL**.

## 🏗️ Contenedorización

| Etapa | Imagen | Propósito |
|-------|--------|-----------|
| `builder` | `maven:3.9-eclipse-temurin-17-alpine` | Compila y genera el `.jar` |
| `production` | `eclipse-temurin:17-jre-alpine` | Ejecuta el `.jar` |

## 🚀 Cómo ejecutar

```bash
git clone https://github.com/TU_USUARIO/back-ventas.git
cd back-ventas
cp .env.example .env   # editar con tus valores
docker compose up --build -d
curl http://localhost:8081/actuator/health
```

## 💾 Persistencia

Named volume `mysql_ventas_data` → los datos de MySQL sobreviven reinicios del contenedor.

## 🔄 Pipeline CI/CD — Secrets requeridos

| Secret | Descripción |
|--------|-------------|
| `DOCKERHUB_USERNAME` | Usuario Docker Hub |
| `DOCKERHUB_TOKEN` | Token Docker Hub |
| `EC2_BACKEND_HOST` | IP EC2 backend |
| `EC2_USER` | Usuario SSH |
| `EC2_SSH_KEY` | Clave privada SSH |

## 📁 Estructura

```
backend-ventas/
├── .github/workflows/deploy.yml
├── src/
├── .env.example
├── Dockerfile
├── docker-compose.yml
└── README.md
```
