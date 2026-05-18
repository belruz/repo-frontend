# Frontend - Innovatech Chile

Frontend desarrollado en React + Vite, desplegado en AWS EC2 mediante contenedor Docker y pipeline CI/CD con GitHub Actions.

## Tecnologías
- React 18
- Vite
- Tailwind CSS
- Docker (multi-stage build)
- GitHub Actions (CI/CD)

## Arquitectura
- EC2 pública (subnet-publica 10.0.1.0/24)
- IP pública: 34.194.185.50
- Puerto: 80

El contenedor incluye Nginx como servidor estatico y proxy para rutas `/api` hacia los backends privados.

## Pipeline CI/CD
El pipeline se activa con push en la rama `deploy`:
1. Construye imagen Docker multi-stage
2. Publica imagen en Docker Hub
3. Despliega en EC2 via AWS SSM usando `docker-compose`

## Docker Compose
- `docker-compose.yml` levanta el servicio `frontend` en el puerto 80.
- El archivo `nginx.conf` realiza proxy a:
	- `/api/ventas` -> Backend Ventas (puerto 8080) en la subred privada
	- `/api/despachos` -> Backend Despachos (puerto 8081) en la subred privada

