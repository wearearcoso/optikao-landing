# Optikao Landing — Contexto del Proyecto

> Este archivo es la fuente de verdad compartida entre todos los agentes que trabajan en este proyecto.
> Lo leen: Hermes (VPS), OpenCode (Mac local), Claude Code (Mac local).
> **Actualízalo siempre que hagas cambios importantes.**

## ¿Qué es este proyecto?
Landing page para **Optikao**, óptica ubicada en Barranquilla, Colombia.
Gestionado por **Arcoso LLC** (agencia SEO/web de Sergio Aldana).

## URLs
- **Producción**: https://optikao.pages.dev (Cloudflare Pages)
- **Repo GitHub**: https://github.com/wearearcoso/optikao-landing
- **Deploy**: automático — cada push a `main` → Cloudflare Pages lo publica

## Stack
- HTML puro (sin framework, sin build step)
- Google Fonts: **Syne 800** (headings) + **Inter** (body)
- CSS Variables (sin Tailwind, sin SCSS)
- Deploy: Cloudflare Pages via Wrangler / GitHub integration

## Estructura de archivos
```
optikao/
├── public/
│   └── index.html      ← ÚNICO archivo de la landing
├── CLAUDE.md           ← este archivo (contexto compartido)
└── AGENTS.md           ← historial de sprints
```

## Paleta de colores
```css
--navy:       #0D1B2A   /* fondo principal oscuro */
--teal:       #1A8F7F   /* color primario de marca */
--teal-light: #20B2A0   /* hover / acentos */
--cream:      #F5F3EF   /* fondo claro / secciones alternas */
--white:      #FFFFFF
--gray:       #6B7280
--gray-light: #F3F4F6
```

## Secciones de la landing (en orden)
1. **Nav fijo** — logo + CTA button
2. **Hero** — dark navy, radial teal glow, badge + h1 + dos CTAs
3. **Services grid** — 6 tarjetas: examen visual, monturas, lentes de contacto, lentes de sol, pantallas digitales, oftalmología pediátrica
4. **Stats bar** — dark navy: 500+ pacientes, 5★, 200+ monturas, 24h
5. **¿Por qué Optikao?** — 3 tarjetas: asesoría personalizada, entrega 24h, garantía
6. **CTA section** — gradiente teal + botón WhatsApp
7. **Footer** — info básica

## ⚠️ Datos pendientes (el cliente debe proveer)
- [ ] Número real de WhatsApp (actualmente: `573000000000`)
- [ ] Dirección física + horarios (footer)
- [ ] Fotos reales para galería / hero
- [ ] Estadísticas reales (¿son exactos los 500+ pacientes, 200+ monturas?)
- [ ] Email de contacto

## Convenciones de trabajo
- **Rama principal**: `main` (no `master`)
- **Commits en inglés**: `feat:`, `fix:`, `chore:`
- **Un solo archivo HTML** — no fragmentar en múltiples archivos a menos que el cliente lo pida explícitamente
- **Responsive mobile-first** — probar en 375px, 768px, 1280px
- **No frameworks externos** — mantener el bundle en cero (solo Google Fonts vía CDN)

## Cómo publicar cambios
```bash
# Desde el VPS (Hermes lo hace):
cd /opt/data/work/optikao
git add -A
git commit -m "feat: descripción del cambio"
git push origin main
# → Cloudflare Pages detecta el push y publica automáticamente

# Desde tu Mac (tú o OpenCode):
cd ~/ruta/a/optikao
git add -A
git commit -m "feat: descripción del cambio"
git push origin main
```

## Orquestación multi-agente

Este proyecto participa en el sistema multi-agente Arcoso (Hermes + OpenCode + Claude Desktop).
**Antes de trabajar:**
1. `git pull` del repo `~/arcoso/orquestacion-arcoso` (o `/opt/data/repo/orquestacion-arcoso` en VPS)
2. Leer `CONTEXT.json` — verificar locks y quién está activo
3. Si hay lock en este proyecto, NO tocarlo
4. Leer `KEEL.md` para contexto global del sistema

## Infraestructura
- **Cloudflare Pages project**: `optikao`
- **Account ID CF**: en `CLOUDFLARE_ACCOUNT_ID` (`.secrets.env`)
- **Token CF**: `CLOUDFLARE_API_TOKEN_OPTIKAO` (`.secrets.env` del VPS)
- **Repo owner**: `wearearcoso` (GitHub)
