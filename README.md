# Diario de un despido

Sitio estático de una sola página. Sin build, sin dependencias.

## Archivos

- `index.html` — todo el sitio: estilos, contenido y el snippet de Mixpanel.
- `.nojekyll` — evita que GitHub Pages procese la carpeta con Jekyll.

## Publicar en GitHub Pages

1. Crea un repositorio nuevo y sube el contenido de esta carpeta a la raíz (no la carpeta entera, los archivos sueltos).
2. En el repo: **Settings → Pages**.
3. En *Source* elige **Deploy from a branch**, rama `main`, carpeta `/ (root)`. Guarda.
4. En 1-2 minutos tendrás la URL en esa misma pantalla. Esa es la que va en la bio de Instagram.

Para actualizar, edita `index.html` y haz push a `main`. Pages republica solo.

## Analítica

Mixpanel está cargado en el `<head>` con el token `4b372793f5dfbed79b94b7d029e430bf` y el host europeo (`api-eu.mixpanel.com`).

Configuración activa:
- `autocapture: true` — registra pageviews y clics automáticamente.
- `record_sessions_percent: 100` — graba la sesión de todas las visitas.

Para ver el tráfico de Instagram por separado, usa UTMs en el enlace de la bio. Mixpanel las lee solo:

```
https://TU-USUARIO.github.io/TU-REPO/?utm_source=instagram&utm_medium=bio
https://TU-USUARIO.github.io/TU-REPO/?utm_source=instagram&utm_medium=stories
```

Así distingues en el panel qué formato te trae más gente.

## Pendiente antes de publicar

- Aviso de cookies / privacidad. Con grabación de sesión al 100% y autocapture estás tratando datos personales, y el RGPD pide informar y recoger consentimiento antes de activar el tracking. Lo más simple: una página `privacidad.html` y un banner que solo llame a `mixpanel.init()` si el visitante acepta.
