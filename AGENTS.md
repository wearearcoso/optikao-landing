# AGENTS.md — Historial de Sprints / Handoffs

> Cada agente (Hermes, OpenCode, Claude Code) debe registrar aquí lo que hizo
> y el estado en que deja el proyecto. Es el log de handoffs entre agentes.

---

## Sprint 1 — Jul 27, 2026
**Agente**: Hermes (VPS Hostinger)
**Estado**: ✅ Completado

### Hecho
- Diseño y construcción completa de la landing en HTML puro (`public/index.html`)
- Secciones: nav fijo, hero, services grid (6 cards), stats bar, why-us (3 cards), CTA + WhatsApp, footer
- Paleta de colores definida: navy/teal/cream
- Google Fonts: Syne 800 + Inter
- Deploy en Cloudflare Pages: https://optikao.pages.dev
- Creación de repo GitHub: https://github.com/wearearcoso/optikao-landing
- Configuración de CLAUDE.md (contexto compartido) + AGENTS.md (este archivo)

### Estado del repositorio
- Branch: `main`
- Archivos: `public/index.html`, `CLAUDE.md`, `AGENTS.md`
- Deploy: Cloudflare Pages conectado via Wrangler (pendiente conectar via GitHub para auto-deploy)

### Pendiente para el próximo agente / sprint
- [ ] Conectar Cloudflare Pages al repo GitHub para auto-deploy (actualmente deploy manual con Wrangler)
- [ ] Reemplazar número WhatsApp placeholder `573000000000` con el real del cliente
- [ ] Agregar dirección física + horarios en el footer
- [ ] El cliente debe enviar fotos reales para la landing
- [ ] Validar stats (500+ pacientes, 200+ monturas, etc.)

---

## Cómo registrar tu trabajo
Cuando termines de trabajar en el proyecto, agrega una entrada así:

```
## Sprint N — Fecha
**Agente**: [Hermes / OpenCode / Claude Code]
**Estado**: ✅ Completado | 🔄 En progreso | ❌ Bloqueado

### Hecho
- ...

### Pendiente
- [ ] ...
```
