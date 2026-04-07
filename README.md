# GexCom — Sitio de Documentacion

Sitio estatico generado automaticamente con MkDocs Material.

**Ultima actualizacion**: 2026-04-07

## Descripcion

Documentacion tecnica de **GexCom** — Sistema de Gestion de Comunicaciones Judiciales del Centro de Servicios Judiciales de Bello, Antioquia.

Generado desde el repositorio principal con `scripts/sync_docs.ps1`.

## Secciones

- **Inicio** — Metricas y descripcion del proyecto
- **Guia de Usuario** — Introduccion, flujo de trabajo, API REST
- **Arquitectura** — Diagramas Mermaid: capas, estados, flujo, DB, dispatch, contexto
- **Desarrollo** — Convenciones, testing, logging, workflow CDAID
- **Seguridad** — JWT+RBAC, audit trail+PII, secretos
- **Calidad** — Estado del proyecto, metricas SDD, auditoria AUDIT-04

## Deploy con Docker

```bash
# Construir imagen
docker build -t gexcom-docs .

# Servir en puerto 8080
docker run -p 8080:80 gexcom-docs
# → http://localhost:8080
```

## Actualizar la documentacion

Desde el repositorio principal de GexCom:

```powershell
# Pipeline completo: ensamblar + build + deploy files
.\scripts\sync_docs.ps1

# Solo vista previa local
make docs-serve
```

## Stack

- **MkDocs Material** — Tema con dark/light mode, busqueda en ES, tabs sticky
- **Mermaid.js** — Diagramas renderizados en el navegador (self-hosted)
- **Nginx Alpine** — Servidor estatico con gzip, cache headers y security headers

> Generado por `scripts/sync_docs.ps1` desde el repositorio principal de GexCom.
