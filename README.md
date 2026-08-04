# Solutions AI — Sitio web corporativo

Landing page corporativa de **Solutions AI**, construida en un **único archivo `index.html`**
que incluye todo el HTML, el CSS y el JavaScript. No requiere build, ni dependencias, ni servidor:
basta con abrir el archivo en el navegador. La carpeta `brand/` guarda el logo suelto para usarlo
fuera del sitio; la página no la necesita para funcionar.

## Cómo verlo

- Doble clic en `index.html`, o
- servirlo en local: `npx serve .` y abrir `http://localhost:3000`

## Qué incluye

| Sección | Contenido |
|---|---|
| Hero | Propuesta de valor, CTA, panel de métricas animado y tarjeta flotante |
| Confianza | Sectores con los que se trabaja + carrusel infinito de tecnologías |
| Servicios | 6 áreas de servicio con iconos y etiquetas |
| Por qué nosotros | Retícula *bento* con los diferenciadores del equipo |
| Proceso | Método de trabajo en 4 etapas |
| Métricas | Contadores animados al entrar en pantalla |
| Casos de éxito | 3 casos con KPIs |
| Testimonios | 3 citas de clientes |
| Planes | 3 modelos de colaboración |
| FAQ | Acordeón accesible |
| Contacto | Formulario con validación + datos de contacto |
| Footer | Enlaces, redes sociales y avisos legales |

## Características técnicas

- **Paleta azul / blanco / negro** definida con variables CSS (`--blue-*`, `--ink`, `--white`),
  con acentos secundarios en cian y violeta (`--cyan-*`, `--violet-*`) para los degradados de marca.
- **Degradados de marca reutilizables** (`--grad-brand`, `--grad-text`): botones, iconos, KPIs y
  fragmentos de titular resaltados con la clase `.grad-text`.
- **Modo claro y oscuro** con conmutador en la barra superior; recuerda la preferencia en `localStorage`
  y respeta `prefers-color-scheme` la primera vez.
- **Totalmente responsive** (escritorio, tablet y móvil) con menú hamburguesa.
- **Animaciones al hacer scroll** vía `IntersectionObserver`, contadores animados y barra de progreso de lectura.
- **Detalles de interacción**: fondo *aurora* animado en el hero, halo que sigue al cursor en las
  tarjetas de servicio, destello en los botones principales, carrusel de tecnologías que se pausa
  al pasar el ratón y enlace del menú resaltado según la sección visible.
- **Accesibilidad**: `aria-label` / `aria-expanded` en controles, foco visible, navegación por teclado
  y respeto de `prefers-reduced-motion`.
- **Sin JavaScript el contenido sigue siendo visible** (las animaciones se activan solo con la clase `js`).
- Iconos SVG en línea y favicon embebido: cero peticiones externas salvo las fuentes de Google Fonts
  (si no cargan, se usan fuentes del sistema).

## Marca

El isotipo es una **S trazada como circuito**, con dos nodos en los extremos: se lee a la vez como
la inicial de Solutions y como una referencia tecnológica. Va sobre un cuadrado redondeado con el
degradado de marca (`#1552A8 → #2E7BFF → #22D3EE`).

| Archivo | Uso |
|---|---|
| `brand/logo.svg` | Versión principal, con degradado. Presentaciones, redes, documentos. |
| `brand/logo-mono.svg` | Una sola tinta (azul corporativo). Impresión, sellos, fondos complejos. |

Dentro de `index.html` el isotipo va **en línea** en tres sitios: la barra de navegación, el pie y el
`favicon` (data URI en el `<link rel="icon">`). Si cambias el logo, actualiza los tres. Los dos SVG
en línea usan IDs de degradado distintos (`logoGrad` y `logoGradFooter`) porque un mismo ID
repetido en la página haría que el segundo no pintara.

## Personalización rápida

1. **Colores**: edita las variables en el bloque `:root` (al inicio del `<style>`).
2. **Textos, precios y datos de contacto**: están directamente en el HTML, en la sección correspondiente.
3. **Formulario**: hoy muestra una confirmación simulada. Para conectarlo a un backend o servicio de
   formularios, sustituye el bloque `setTimeout(...)` del `form.addEventListener('submit', ...)`
   por tu llamada `fetch()`.

## Despliegue

Al ser un sitio estático de un solo archivo, funciona tal cual en GitHub Pages, Netlify, Vercel,
Cloudflare Pages o cualquier hosting tradicional.
