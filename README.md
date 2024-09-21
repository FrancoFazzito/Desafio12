## Material Adicional de Soporte

Este repositorio incluye material adicional de soporte para la solución implementada. Se proporcionan diagramas que ilustran la arquitectura de la solución, facilitando la comprensión del flujo de trabajo de despliegue automatizado con ArgoCD y GitOps.

### Diagrama de Arquitectura

```mermaid
graph TD;
    A[Repositorio Git] -->|Manifiestos Kubernetes| B[ArgoCD Server];
    B --> C[Aplicación NodeJS];
    B --> D[MongoDB];
    C --> E[NestJS App];
    D --> F[Base de Datos];
    B --> G[Clúster de Kubernetes];
    E --> F;
