# 🏢 Inmobiliaria Pro

Sistema de gestión de alquileres. App web estática que corre 100% en el navegador, sin servidor ni base de datos externa.

## Funcionalidades

- **Propiedades** — Cargá cada alquiler con nombre, dirección e inquilino
- **Pagos recurrentes** — Configurá el día de vencimiento mensual, marcalos como cobrados y el sistema avanza al mes siguiente automáticamente
- **Notas con fecha** — Vencimientos de contrato y notas libres con alerta de vencimiento
- **Agenda** — Vista global ordenada por urgencia
- **Autenticación** — Acceso con contraseña protegida por SHA-256

## Seguridad

La contraseña nunca se guarda en texto plano. Se almacena como hash SHA-256 en el `localStorage` del navegador usando la [Web Crypto API](https://developer.mozilla.org/en-US/docs/Web/API/SubtleCrypto/digest). Los datos de la app también viven en `localStorage`, por lo que son locales a cada navegador.

> **Importante:** Esta app es ideal para uso personal o de equipo pequeño. Al ser una app estática sin backend, quien tenga acceso al navegador podría inspeccionar el `localStorage`. No usarla para datos altamente sensibles sin una capa adicional de seguridad.

## Uso

### Opción A — Local
Abrí `alquileres.html` directamente en tu navegador.

### Opción B — GitHub Pages
1. Hacé fork de este repositorio
2. En **Settings → Pages**, elegí `main` branch y carpeta `/root`
3. Accedé a `https://<tu-usuario>.github.io/<nombre-repo>/alquileres.html`

## Primera vez

Al abrir la app por primera vez se te pedirá que crees una contraseña. Esa contraseña queda guardada en tu navegador — no hay forma de recuperarla si la olvidás (deberías limpiar el `localStorage` y empezar de nuevo).

## Tecnologías

- HTML + CSS + JavaScript vanilla (sin frameworks ni dependencias)
- Web Crypto API para hashing
- `localStorage` para persistencia de datos
- `sessionStorage` para manejo de sesión
