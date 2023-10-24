# GitHub Actions Workflows 🤖

Este repositorio contiene dos workflows de GitHub Actions: `Feature Branch Workflow` y `Release Branch Workflow`.

## Feature Branch Workflow

El workflow de la rama de características se activa en las siguientes condiciones:

- Cuando se hace push a las ramas que coinciden con el patrón `feature/*`.
- Se ejecuta automáticamente cada lunes a las 15:45 y a las 20:00 (BOT-GMT-4,UTC-4).
- También puede ser ejecutado manualmente.

Este workflow contiene tres trabajos:

1. **Test**: Este trabajo se encarga de la instalación de dependencias.
2. **Build**: Este trabajo se encarga de la construcción de la aplicación.
3. **Deploy**: Este trabajo se encarga del despliegue a producción. Se ejecuta sólo si el evento es un push y el tipo de referencia es una rama.

## Release Branch Workflow

El workflow de la rama de lanzamiento se activa cuando se hace push a las ramas que coinciden con el patrón `release/*`.

Este workflow contiene un solo trabajo:

1. **Deploy**: Este trabajo se encarga del despliegue a producción. Se ejecuta sólo si el evento es un push y el tipo de referencia es una rama.

## Cumplimiento de los requisitos

Los workflows cumplen con los siguientes requisitos:

- Contienen al menos tres trabajos: test, build y deploy.
- Contienen al menos dos pasos por cada trabajo.
- Se ejecutan manualmente, cada lunes a las 15:45 y a las 20:00 (BOT-GMT-4,UTC-4), y en las ramas que coinciden con los patrones `feature/*` y `release/*`.