# render-keepalive

Cron que mantiene despiertos los backends en Render (plan Free): un GitHub Action hace
`curl` cada 15 min (lun–vie 6–17h) para evitar cold-starts en las demos.

## Qué cubre
- `spacecraftsystem.onrender.com`
- `bankinback.onrender.com`
- `spacecraft-taller-backend.onrender.com`

No cubre ContentHub ni frontends. Timeouts de 90s + 2 reintentos; disparo manual con
`workflow_dispatch`.

## Agregar un servicio
Solo sumar su URL a la lista en `keep-alive.yml` (duplicado en `.github/workflows/`).
Sin código, sin dev server, sin build ni deploy.
