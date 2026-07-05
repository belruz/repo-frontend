# Frontend - Innovatech Chile

Frontend desarrollado en React + Vite, desplegado en AWS EC2 mediante contenedor Docker y pipeline CI/CD con GitHub Actions.

## Descripción del Proyecto
Este repositorio forma parte de la plataforma central de Innovatech Chile, un sistema distribuido diseñado para la gestión eficiente de ventas y logística. El proyecto completo se compone de tres repositorios principales:
- **Frontend**: Interfaz de usuario para la interacción con el sistema (este repositorio).
- **Backend Ventas**: Microservicio encargado del registro y control de ventas.
- **Backend Despachos**: Microservicio encargado de la coordinación y seguimiento de envíos.

Esta arquitectura permite una alta escalabilidad, mantenimiento simplificado y despliegues independientes en la infraestructura de AWS.

## Tecnologías
- React 18
- Vite
- Tailwind CSS
- Docker (multi-stage build)
- GitHub Actions (CI/CD)


## Pipeline CI/CD
El pipeline se activa con push en la rama `deploy`:
1. Construye imagen Docker multi-stage
2. Publica imagen en ECR
3. Despliega en EKS via kubectl 

