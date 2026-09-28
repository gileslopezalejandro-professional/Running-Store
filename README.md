# Dromos — Built to Run

Web de venta de tenis de running ASICS en Santa Cruz, Bolivia. Sin pago online: el carrito arma el pedido y lo envía por WhatsApp.

## Archivos
- `index.html` — la web completa (home, catálogo, ficha de producto, buscador, carrito, Shoe Finder, guía de tallas).
- `inventory.json` — inventario: modelos, colores, fotos, tallas en stock y datos de RunRepeat. Reemplazable por una API/BD con el mismo formato.
- `support.js` — runtime necesario para `index.html` (no editar).
- `image-slot.js` — espacios para arrastrar fotos (hero y secciones "Para correr" / "Todo el día").
- `brand/` — logo del corredor en SVG (rojo, blanco, negro) y PNG de 2000 px.
- `brand-logo.html` — hoja con todas las versiones del logo y la paleta.

## Configuración pendiente
- **Número de WhatsApp**: prop `whatsappNumber` en `index.html` (dentro de `data-props`, o buscar `this.props.whatsappNumber`).
- **Instagram / TikTok**: links `href="#"` en el footer.
- **Tipo de cambio**: `const FX = 12;` en `index.html`. Precios en `inventory.json` están en USD y se muestran en Bs redondeados a la decena.
- **Stock**: en `inventory.json` → `colors[modelo][i].sizes` = `{ "40": "stock", ... }` (talla BR).

## Correr localmente
`inventory.json` se carga con `fetch`, así que hay que servir la carpeta (no abrir el archivo con doble clic):

```
npx serve .
```

## Publicar
Funciona tal cual en GitHub Pages, Netlify, Vercel o Coolify (sitio estático).

## Notas
- Fotos de producto enlazadas desde Running Warehouse; para producción conviene alojar fotos propias o del distribuidor.
- Paleta: blanco #FFFFFF, negro #0B0D10, rojo rosado #D63A5B (acento).
