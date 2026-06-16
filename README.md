# Horizonte Blockchain — Sitio Web

Sitio institucional de Horizonte Blockchain: comunidad, educación, eventos, alianzas y servicios Web3 para Latinoamérica.

Sitio estático (HTML/CSS/JS puro, sin frameworks ni build). Costo de hosting: **$0/mes**.

## Estructura de esta carpeta

```
sitio-web/                 ← Esta es la carpeta raíz del repositorio GitHub
├── index.html             ← Página completa (todo el sitio en un solo archivo)
├── robots.txt              ← Indica a buscadores qué indexar
├── sitemap.xml              ← Mapa del sitio para SEO
├── _headers                  ← Reglas de cache y seguridad (las lee Cloudflare Pages automáticamente)
├── favicon.ico, favicon-32x32.png, apple-touch-icon.png   ← Íconos del sitio
├── README.md                  ← Esta guía
└── assets/img/                  ← Logo, fotos del equipo y comunidad (optimizadas para web)
```

Todo lo que necesitas para producción está aquí dentro. No subas la carpeta del proyecto completa — **sube solo esta carpeta `sitio-web`**.

## Paso 1 — Crear el repositorio en GitHub

1. Entra a [github.com/new](https://github.com/new).
2. Nombre sugerido: `horizonte-blockchain-web`.
3. Visibilidad: puede ser público (no hay claves secretas en este código — el Access Key de Web3Forms es público por diseño, ver Paso 4).
4. No marques "Add README" (ya tienes uno).
5. Crea el repo.

Desde tu computadora, dentro de esta carpeta `sitio-web`:

```bash
git init
git add .
git commit -m "Sitio Horizonte Blockchain v1"
git branch -M main
git remote add origin https://github.com/TU-USUARIO/horizonte-blockchain-web.git
git push -u origin main
```

## Paso 2 — Conectar Cloudflare Pages

1. Crea una cuenta gratis en [pages.cloudflare.com](https://pages.cloudflare.com).
2. "Create a project" → "Connect to Git" → selecciona el repo `horizonte-blockchain-web`.
3. Configuración de build:
   - **Framework preset:** None
   - **Build command:** (déjalo vacío)
   - **Build output directory:** `/`
4. Deploy. En 1-2 minutos tendrás una URL tipo `horizonte-blockchain-web.pages.dev` ya funcionando.

## Paso 3 — Conectar tu dominio horizonteblockchain.org

1. En el proyecto de Cloudflare Pages → pestaña "Custom domains" → "Set up a custom domain".
2. Escribe `horizonteblockchain.org` (y opcionalmente `www.horizonteblockchain.org`).
3. Si tu dominio ya usa Cloudflare como DNS, el registro se crea automático. Si no, Cloudflare te dará un registro CNAME para crear en tu proveedor de dominio actual.
4. El certificado SSL se emite automáticamente y gratis.

## Paso 4 — Activar el formulario de contacto (Web3Forms, gratis)

El formulario de leads ya está integrado en el código (sección `#contacto`), solo falta tu clave personal:

1. Entra a [web3forms.com](https://web3forms.com) y genera tu Access Key gratis con tu correo (no requiere tarjeta).
2. Abre `index.html`, busca la línea:
   ```html
   <input type="hidden" name="access_key" value="TU_ACCESS_KEY_WEB3FORMS">
   ```
3. Reemplaza `TU_ACCESS_KEY_WEB3FORMS` con la clave que te envió Web3Forms por correo.
4. Vuelve a subir el cambio (`git add . && git commit -m "Activar formulario" && git push`) — Cloudflare Pages redeploya solo, automáticamente, en cada push.

Plan gratuito de Web3Forms: 250 envíos/mes — más que suficiente para empezar.

## Paso 5 — Completar enlaces de redes sociales (pendiente)

En el código actual, los enlaces de **Telegram, LinkedIn e Instagram** todavía apuntan a `#` (no hay URL real cargada) — solo WhatsApp está activo. Para activarlos:

1. Abre `index.html` y busca `href="#"` cerca de los textos "Telegram", "LinkedIn" e "Instagram" (sección Comunidad y pie de página).
2. Reemplaza cada `#` por la URL real de cada canal.
3. Si quieres, también agrega esas URLs al bloque `sameAs` del schema JSON-LD al inicio del `<head>` — esto ayuda a que Google y los motores de IA (ChatGPT, Gemini, Perplexity) reconozcan estos canales como oficiales de la organización.

## Checklist antes de anunciar el lanzamiento

- [ ] Access Key de Web3Forms configurada y probada (envía un mensaje de prueba desde el formulario)
- [ ] Enlaces de Telegram, LinkedIn e Instagram actualizados
- [ ] Dominio horizonteblockchain.org apuntando a Cloudflare Pages
- [ ] Sitio revisado en móvil y desktop

## Costo total mensual

| Servicio | Plan | Costo |
|---|---|---|
| Hosting (Cloudflare Pages) | Free | $0 |
| CDN + SSL | Incluido | $0 |
| Formulario de leads (Web3Forms) | Free, 250 envíos/mes | $0 |
| Dominio horizonteblockchain.org | Ya lo tienes | (renovación anual aparte) |

**Total: $0/mes** en infraestructura.
