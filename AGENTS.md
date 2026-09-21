# render-keepalive — AGENTS.md

> Proyecto independiente (repo solo para alojar un cron). Abrir opencode con cwd en
> `render-keepalive/`, nunca en `Projects/`. Sin código, sin dev server, sin build.

## Qué es
- Un GitHub Action (`keep-alive.yml`, duplicado en `.github/workflows/`) que hace `curl`
  cada 15 min (lun–vie 6–17h) contra los backends en Render plan Free para evitar cold-starts.
- Cubre 3 backends: `spacecraftsystem.onrender.com`, `bankinback.onrender.com`,
  `spacecraft-taller-backend.onrender.com`. NO cubre ContentHub ni frontends.
- Timeouts 90s + 2 reintentos. Disparo manual: `workflow_dispatch`.

## No hacer
- No agregar lógica: para sumar un servicio (ej. ContentHub) solo agregar su URL a la lista.
- No borrar el duplicado de `.github/workflows/` sin verificar cuál usa GitHub.
