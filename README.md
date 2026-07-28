# Solutions AI — Sitio web corporativo

Landing page corporativa de **Solutions AI**, construida en un **único archivo `index.html`**
que incluye todo el HTML, el CSS y el JavaScript. No requiere build, ni dependencias, ni servidor:
basta con abrir el archivo en el navegador.

## Cómo verlo

- Doble clic en `index.html`, o
- servirlo en local: `npx serve .` y abrir `http://localhost:3000`

## Qué incluye

| Sección | Contenido |
|---|---|
| Hero | Propuesta de valor, CTA y panel de métricas animado |
| Confianza | Sectores con los que se trabaja |
| Servicios | 6 áreas de servicio con iconos y etiquetas |
| Proceso | Método de trabajo en 4 etapas |
| Métricas | Contadores animados al entrar en pantalla |
| Casos de éxito | 3 casos con KPIs |
| Testimonios | 3 citas de clientes |
| Planes | 3 modelos de colaboración |
| FAQ | Acordeón accesible |
| Contacto | Formulario con validación + datos de contacto |
| Footer | Enlaces, redes sociales y avisos legales |

## Características técnicas

- **Paleta azul / blanco / negro** definida con variables CSS (`--blue-*`, `--ink`, `--white`).
- **Modo claro y oscuro** con conmutador en la barra superior; recuerda la preferencia en `localStorage`
  y respeta `prefers-color-scheme` la primera vez.
- **Totalmente responsive** (escritorio, tablet y móvil) con menú hamburguesa.
- **Animaciones al hacer scroll** vía `IntersectionObserver`, contadores animados y barra de progreso de lectura.
- **Accesibilidad**: `aria-label` / `aria-expanded` en controles, foco visible, navegación por teclado
  y respeto de `prefers-reduced-motion`.
- **Sin JavaScript el contenido sigue siendo visible** (las animaciones se activan solo con la clase `js`).
- Iconos SVG en línea y favicon embebido: cero peticiones externas salvo las fuentes de Google Fonts
  (si no cargan, se usan fuentes del sistema).

## Personalización rápida

1. **Colores**: edita las variables en el bloque `:root` (al inicio del `<style>`).
2. **Textos, precios y datos de contacto**: están directamente en el HTML, en la sección correspondiente.
3. **Formulario**: hoy muestra una confirmación simulada. Para conectarlo a un backend o servicio de
   formularios, sustituye el bloque `setTimeout(...)` del `form.addEventListener('submit', ...)`
   por tu llamada `fetch()`.

## Despliegue

Al ser un sitio estático de un solo archivo, funciona tal cual en GitHub Pages, Netlify, Vercel,
Cloudflare Pages o cualquier hosting tradicional.
