# Linnda Search Landing

Landing page estática para vender `Linnda Search` (Google Ads), construida a partir del archivo `index-v5.html`.

## Estructura

- `index.html`: landing completa (SEO, estilos y scripts incluidos).

## Ejecutar en local

Opcion 1:

```bash
cd linnda-search-landing
python3 -m http.server 8080
```

Abrir: `http://localhost:8080`

Opcion 2:

Usar la extension Live Server de VS Code/Cursor.

## Deploy rapido

Como es un sitio estatico de un solo archivo, puedes desplegarlo en:

- Vercel
- Netlify
- GitHub Pages
- Cloudflare Pages

Publica el contenido de esta carpeta, con `index.html` en la raiz.

## Notas

- El HTML contiene metadatos Open Graph, FAQ Schema y Service Schema.
- Si vas a usar dominio propio, actualiza en `index.html` las URLs canonicas y de OG:
  - `https://search.linnda.co/`
  - `https://search.linnda.co/og-image.png`
