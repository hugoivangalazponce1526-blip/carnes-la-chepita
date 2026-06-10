# CLAUDE.md — Carnes La Chepita

Context file for Claude Code. Brief and precise — read before starting any session.

## Project overview

Landing page orientada a conversión para **Carnes La Chepita**, carnicería familiar desde 1990 en Curicó y Molina/Lontue (Región del Maule, Chile). El negocio ya tiene delivery propio y 8.600+ seguidores en Instagram pero **no tiene página web** — ese es el problema que resuelve este proyecto. Objetivo: capturar tráfico orgánico local de Google y convertirlo en pedidos por WhatsApp.

Stack igual al proyecto HG Growth Lab: un único `index.html` con HTML, CSS y JS vanilla. Tailwind vía CDN. Sin bundler, sin framework, sin `node_modules`.

## Running locally

```bash
# Sin servidor requerido — abrir directamente en el browser, o:
python3 -m http.server 8080
# o
npx serve .
```

## Deployment

**Docker + EasyPanel:**
```bash
docker build -t chepita .
docker run -p 80:80 chepita
```
El `Dockerfile` usa `nginx:alpine`, copia todos los archivos, sirve en el puerto 80.

## Architecture

Todo en `index.html`. Secciones planeadas:

| Sección | Propósito |
|---|---|
| Hero | CTA directo a WhatsApp + propuesta de valor: "35 años / delivery / calidad" |
| Productos | Catálogo con precios (packs + cortes especiales) |
| Delivery | Zonas de reparto: Curicó y Molina/Lontue |
| Testimonios | Social proof (clientes satisfechos) |
| Contacto | Botones WhatsApp + mapa/dirección |

## Client identity

| Campo | Valor |
|---|---|
| Nombre comercial | Carnes La Chepita |
| Fundación | Desde 1990 (35+ años) |
| Dirección | Av. 7 de Abril 2070, Lontue |
| Zonas de delivery | Curicó · Molina · Lontue |
| WhatsApp Curicó | +56 9 5486 9712 |
| WhatsApp Molina | +56 9 3884 1626 |
| Instagram | @carneslachepita |
| Facebook | @LachepitaCarnes |
| Mascota | "La Vaquita" (animada, parte de la identidad visual) |

## Products & pricing

| Producto | Precio |
|---|---|
| Chunchules frescos | $12.990 / kg |
| Pack familiar (asado completo) | $29.990 |
| Pack parrillero, pack pichanguero, carpaccio, crudo, queso de cabeza | Sin precio fijo — van en RRSS por temporada |

⚠️ Precios en CLP. Actualizar con el cliente antes de publicar — son datos de junio 2026.

## Brand & tone

- **Coloquial chileno:** "chiquillos", "pichangueros", "mucho corazón"
- **Alta energía:** "¡IMPERDIBLE!", "¡No te lo puedes perder!"
- **Credibilidad:** "35 años en el mercado" es el argumento central de confianza
- **Emojis frecuentes:** 🥩🤩❤️⚽️ — úsalos en copywriting cuando sea apropiado
- Paleta: rojo cárnico / blanco / negro. No definida todavía — proponer al cliente.

## Key differentiators (usar en copy)

1. Única carnicería local con delivery **y** marca activa en redes
2. Productos únicos en la zona: chunchules frescos, carpaccio, queso de cabeza, pack pichanguero
3. Trayectoria de 35 años = confianza que ninguna cadena puede igualar
4. Supermercados locales tienen reseñas negativas de calidad — La Chepita es la alternativa fresca

## Main competitor with web

**Carnes Kar** — `carneskar.cl` — Prat 501, Curicó. Cadena nacional, sin delivery propio, tono impersonal. Su ventaja actual: aparece en Google. La Chepita debe superarla en SEO local con keywords como "carnicería delivery Curicó", "carne a domicilio Molina", "pack parrillero Maule".

## SEO local (target keywords)

- carnicería delivery Curicó
- carne a domicilio Molina
- carnicería Lontue
- pack parrillero Maule
- chunchules frescos Curicó

## Key JS to implement

- `openWhatsapp(numero)` — abre wa.me con mensaje predefinido según zona (Curicó o Molina)
- Selector de zona (Curicó / Molina) que cambia el número de WhatsApp activo
- Sticky CTA flotante de WhatsApp en mobile
