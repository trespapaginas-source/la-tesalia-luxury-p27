LA TESALIA LUXURY P27 — BUILD OPTIMIZADO WEB + MÓVIL
=====================================================

PREVIEW
-------
Abre index.html o sirve la carpeta con cualquier servidor estático:
    python3 -m http.server 8765
    http://127.0.0.1:8765

ESTRUCTURA
----------
index.html      Sitio completo (referencia imágenes externas, ya no base64).
img/            17 imágenes WebP optimizadas con variantes responsive
                (srcset: 1080/1600/2400 según sección).
assets/         Material fuente original (PNG sin optimizar) — no usado por el sitio.
production/     Build anterior autónomo (referencia histórica).

QUÉ SE ARREGLÓ
--------------
- Rendimiento: de 2.5 MB en un solo HTML a ~35 KB de HTML + imágenes
  WebP externas con lazy loading y srcset. El hero carga en 16–85 KB
  según dispositivo.
- Imágenes: seleccionadas las mejores fotos reales de la galería
  (vista aérea IMG_8314 como hero, atardecer IMG_8319 en intro,
  palapa/BBQ IMG_8315 en pasadía, IMG_8321 recortada al centro para
  literas). Se descartaron las panorámicas 360° con distorsión visible
  como imagen principal (IMG_8323 se mantiene solo como fondo tenue
  de la sección final).
- Responsive: media queries consolidadas (900px / 400px), tipografía
  fluida con clamp(), mínimo 12px en texto de cuerpo móvil, cero
  scroll horizontal verificado en 360/390/1180/1440px.
- Accesibilidad: contraste verificado (full-bleed 6.5:1), foco visible,
  alt descriptivos, aria-expanded/aria-controls en controles táctiles,
  todos los targets táctiles ≥ 44px, prefers-reduced-motion respetado.
- Navegación móvil: menú overlay nuevo (antes los enlaces simplemente
  desaparecían), cierre con Escape y al navegar.
- CLS: todas las imágenes con width/height explícitos y aspect-ratio.

ANTES DE PRODUCCIÓN
-------------------
1. Colocar el número de WhatsApp en WHATSAPP_NUMBER (index.html, script final).
2. Confirmar habitaciones 3 y 4.
3. Confirmar ubicación exacta (el mapa apunta a Sabanagrande, Atlántico).
4. Confirmar condiciones exactas de hospedaje/pasadía.
5. Subir index.html + carpeta img/ juntas al hosting.
