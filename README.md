# Linnda Search — Landing Page

Landing page de lanzamiento del producto **Linnda Search** — audit de Google Ads con IA para brands de LatAm.

![GEO Score](https://geo-optimizer-web.onrender.com/badge?url=https://search.linnda.co)
![Vercel Deploy](https://img.shields.io/badge/deployed-vercel-000000?logo=vercel)
![Status](https://img.shields.io/badge/status-live-00d4ff)

**Live:** [search.linnda.co](https://search.linnda.co) · [vercel preview](https://linnda-search-landing.vercel.app)

---

## Stack

- HTML5/CSS3/Vanilla JS (single-file deployment)
- Design system alineado con Linnda portal (Next.js + Tailwind + glassmorphism)
- Hosted en Vercel con custom domain
- Form backend: n8n webhook (ver CONFIG block)

---

## Estructura del proyecto

```
linnda-search-landing/
├── index.html                    # Landing principal
├── public/
│   ├── robots.txt               # Permite 27 bots de AI explícitamente
│   ├── sitemap.xml              # URLs canónicas
│   ├── llms.txt                 # Summary AI-readable (RFC: llmstxt.org)
│   ├── llms-full.txt            # Knowledge base completo AI-readable
│   ├── .well-known/
│   │   └── ai.txt              # AI usage policy (análogo a security.txt)
│   └── ai/
│       ├── summary.json        # Entity summary estructurado
│       ├── faq.json            # FAQs en formato JSON
│       └── service.json        # Schema.org Service con offers
├── .github/workflows/
│   └── geo-audit.yml           # CI: auditoría GEO en cada push
└── README.md
```

---

## Configuración

Las variables configurables viven al inicio del `<script>` en `index.html`, bloque `CONFIG`:

| Variable | Default | Descripción |
|---|---|---|
| `WEBHOOK_URL` | `null` | Endpoint n8n para enviar leads del form |
| `LOOM_URL` | `null` | Demo de 2 min (fallback: WhatsApp) |
| `CALENDLY_URL` | `calendar.app.google/ADqwyJuTePGxqZGJ6` | Calendario de Jose Clavijo |
| `FOUNDING_DEADLINE` | `2026-04-30T23:59:00-05:00` | Cierre del Founding 10 |
| `FOUNDING_TAKEN` | `3` | Cupos tomados (actualizar manualmente) |
| `FOUNDING_TOTAL` | `10` | Cupos máximos |

---

## AI Search Optimization (GEO)

Esta landing está optimizada para **Generative Engine Optimization** — aparecer en respuestas de ChatGPT, Claude, Perplexity, Gemini y otras IAs cuando alguien pregunta por herramientas de audit de Google Ads en LatAm.

### Endpoints de AI discovery

- [/llms.txt](https://search.linnda.co/llms.txt) — summary markdown para LLMs
- [/llms-full.txt](https://search.linnda.co/llms-full.txt) — knowledge base completo
- [/.well-known/ai.txt](https://search.linnda.co/.well-known/ai.txt) — policy de uso con AI crawlers
- [/ai/summary.json](https://search.linnda.co/ai/summary.json) — entity summary JSON
- [/ai/faq.json](https://search.linnda.co/ai/faq.json) — FAQs JSON
- [/ai/service.json](https://search.linnda.co/ai/service.json) — service + offers JSON

### Schemas JSON-LD implementados

- `Organization` (Linnda)
- `Service` (Linnda Search con 3 offers)
- `FAQPage` (7 preguntas)
- `HowTo` (3 pasos del audit)
- `AggregateOffer` (pricing)
- `Article` (caso Matena)

### Monitoreo automático

El workflow `.github/workflows/geo-audit.yml` ejecuta [geo-optimizer-skill](https://github.com/Auriti-Labs/geo-optimizer-skill) en cada push y semanalmente (lunes 4am Bogotá), subiendo resultados al tab Security de GitHub.

---

## Deployment

```bash
# Clonar
git clone https://github.com/TU_USER/linnda-search-landing.git
cd linnda-search-landing

# Deploy en Vercel (auto-deploy en cada push a main)
vercel --prod
```

Custom domain: `search.linnda.co` apuntando via CNAME a `cname.vercel-dns.com`.

---

## Contacto

- Email: jose@linnda.co
- WhatsApp: [+57 319 705 6803](https://wa.me/573197056803)
- Calendar: [calendar.app.google/ADqwyJuTePGxqZGJ6](https://calendar.app.google/ADqwyJuTePGxqZGJ6)
- Parent: [www.linnda.co](https://www.linnda.co)
