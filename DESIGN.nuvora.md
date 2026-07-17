# DESIGN.md — Nuvora

> Fuentes: theme export real de Shopify (`theme_export__nuvora-2096-myshopify-com-horizon`), sitio Shopify (páginas Inicio y Contacto). El Instagram @_nuvora.uy está vacío (sin posts, foto ni bio) — no hay contenido publicado para analizar tono/estilo ahí todavía.

## Colores (extraídos del código real del tema)

**Paleta base del tema** (rige botones, bordes, inputs, carrito — en toda la tienda):

| Uso | Hex |
|---|---|
| Fondo (background) | `#FFFFFF` |
| Primer plano (foreground: texto, botones) | `#000000` |
| Color 1 | `#333333` |
| Color 2 (bordes, divisores) | `#DFDFDF` |

Esta paleta base sigue siendo **blanco/negro/gris**, no azul marino + verde menta. El resto del sitio (botones primarios, inputs, drawer del carrito, variantes) hereda de acá.

**Azul marino — sí está aplicado, pero solo en el hero de la home:**

| Bloque | Hex |
|---|---|
| Fondo del título "Innovación en tus manos" | `#193A5C` |
| Fondo del subtítulo | `#10263F` |

Confirma la dirección "azul marino oscuro" que definiste, pero hoy vive únicamente en el hero — no está extendido al resto del sitio (header, footer, botones siguen en negro/blanco).

**Verde menta — no aparece como color de marca aplicado.** Los verdes/azules/amarillos que sí aparecen en el código (`#034CBA`, `#1A7A5C`, `#FBB91C`, etc.) están todos dentro de bloques de una app de IA para páginas de producto (badges, reseñas, estrellas) — son colores por defecto de esos bloques generados automáticamente, no una paleta de marca elegida a propósito. Si querés que el verde menta esté realmente en la tienda, hay que aplicarlo a mano en el editor de temas (botones, header, footer).

**Recomendación para unificar lo que ya está con lo planeado:**

| Uso | Hex |
|---|---|
| Primario | `#193A5C` (el navy ya usado en el hero) |
| Secundario/acento | a definir — el menta no está aplicado en ningún lado todavía |
| Fondo | `#FFFFFF` |
| Texto | `#000000` |

## Tipografía (confirmada en `settings_data.json`)

Fuente: **Inter**, en tres pesos:
- Cuerpo de texto: Inter Regular (400)
- Subtítulos: Inter Medium (500)
- Encabezados y acentos: Inter Bold (700)
- Tamaños: párrafo 14px · H1 56px · H2 48px · H3 32px

## Tono de voz (según copy real del sitio)

- Voseo uruguayo consistente en el hero: *"Descubrí productos que combinan diseño y funcionalidad"*.
- Frases cortas, tipo eslogan, una idea por línea: "Envío a todo Uruguay", "Devoluciones sin problemas", "Soporte disponible".
- Mezcla profesional + cercano, sin exagerar informalidad — no usa emojis ni signos de exclamación en el copy de la tienda.
- Nombres de producto: descriptivos y técnicos, formato "Producto + característica clave – beneficio" (ej. *"Pistola Masajeadora Portátil – Recuperación Muscular Profesional en Casa"*).
- Firma institucional, no personal: "el equipo de Nuvora" (definido para posts tipo "¿Quiénes somos?").

**Inconsistencia detectada:** el newsletter usa tuteo ("Obtén ofertas exclusivas...") mientras el hero usa voseo ("Descubrí..."). Conviene unificar en voseo en todo el sitio.

## Frases que usa / dirección de marca

- "Innovación en tus manos"
- "Envío a todo Uruguay"
- "Devoluciones sin problemas"
- "Personas reales creando grandes productos"
- "el equipo de Nuvora" (firma)

## Frases a evitar

- Superlativos sin sustento ("el mejor", "increíble", "único en el mercado") — no aparecen en el copy actual, mantener esa línea.
- Jerga o slang muy informal — no es el registro que usa el sitio.
- Tuteo suelto — el sitio tiende a voseo, no mezclar.

## Estilo visual

- Fondos sólidos de color de marca con foto de producto real superpuesta (hero con la pistola masajeadora).
- Isotipo abstracto/geométrico simple (definido, no logo figurativo).
- Estructura de tienda: hero → beneficios en íconos (envío, devoluciones, soporte) → grilla de productos → newsletter.

## Copy adicional encontrado en el theme export (páginas de producto)

- Badges de confianza: "Favorito de Clientes", "Calidad Probada"
- Beneficios (íconos): "Envío Gratis", "Devoluciones Fáciles", "Fórmulas Limpias", "Soporte Real"
- Reseñas placeholder con nombres y comentarios de ejemplo (Martín R., Carolina L., Tomás G.) — **son contenido de muestra generado por la app de IA de la tienda, no reseñas reales.** Reemplazar antes de publicar para no mostrar testimonios falsos.
- "4.8 · 970+ reseñas verificadas" — también placeholder, mismo cuidado.

## Inspiración de formato de posts (de competencia — estructura, no colores)

Analizando las referencias que pasaste (Aurlux, comparativas de celulares, Cellular Trade, mundotech.tuc, Electrónica JL), se repiten estos patrones de estructura que se pueden adaptar a Nuvora sin tocar la paleta:

**1. Formato "VS" (problema vs. solución)**
- Split de pantalla en dos mitades: lado izquierdo = el problema/competencia, lado derecho = el producto propio.
- Cada lado tiene su propia lista corta de bullets en cajitas blancas (3 ítems máx, frase corta).
- Cierra con una franja inferior con la promesa central en una sola línea.
- Aplicable a Nuvora: "Cargador de mesa" vs. "Mini aspiradora Nuvora", o "Recuperación con hielo" vs. "Pistola masajeadora Nuvora".

**2. Formato ficha técnica / comparativa (carrusel editorial)**
- Portada con categoría chica arriba ("CAMERA") + titular grande de 2 líneas tipo eslogan ("Capture everything.").
- Foto de producto grande, con etiquetas de specs apuntando a partes específicas.
- Debajo, tabla de 2 columnas con ícono de marca + nombre + lista de specs con su explicación en una línea.
- Aplicable a Nuvora: portada "CÁMARA" → "Reviví el momento." → specs de la cámara vintage con etiquetas apuntando al lente/pantalla.

**3. Formato listicle/roundup (portada de carrusel)**
- Primera slide: número grande + sustantivo ("5 gadgets") + subtítulo more chico ("que dominaron este mes").
- Productos flotando en distintos ángulos alrededor del texto, sin fondo limpio (más caótico/dinámico).
- Logo de marca como watermark discreto.
- Aplicable a Nuvora: "3 productos que ya podés pedir" como portada de carrusel presentando cámara + aspiradora + masajeador juntos.

**4. Formato ficha de producto individual (repetido dentro del mismo carrusel)**
- Mismo layout para cada producto, cambia solo el contenido: logo arriba centrado → nombre del producto en 2 líneas bold → bajada descriptiva de una línea → foto de producto centrada → badge/etiqueta de precio en una esquina (rectángulo con el valor).
- Es una plantilla reutilizable: mismo orden de elementos, mismo tamaño de badge, mismo lugar de precio en todos los posts.
- Aplicable a Nuvora: crear esta plantilla fija y reutilizarla para cámara, aspiradora y masajeador — refuerza reconocimiento de marca por repetición.

**5. Formato "hook + mockup de nota/chat"**
- Titular gancho arriba en 2-3 líneas sobre foto de contexto (local, mesada, producto en mano).
- Superpuesto: una "nota" tipo iPhone Notes o burbuja de chat con bullets cortos de beneficio — le da aspecto de recomendación personal/auténtica, no de anuncio.
- Watermark de usuario/marca abajo.
- Aplicable a Nuvora: útil para reels/posts que buscan sensación "boca a boca" en vez de publicidad directa.

**6. Formato póster de catálogo completo (post institucional, no por producto)**
- Título con ícono de check + frase de marca arriba.
- Grilla de fotos de producto (sin fondo, recortadas) alrededor de un isotipo/mascota central.
- Nombre de marca + sitio web en grande.
- Barra de contacto al pie: WhatsApp, Instagram, Facebook con iconitos.
- Aplicable a Nuvora: un post "todo lo que tenemos" con los 3 productos + WhatsApp +598 92428556 al pie, para fijar en el perfil.

**Orden sugerido para el feed/carrusel de lanzamiento de Nuvora**, tomando el orden que usan estas referencias:
1. Portada tipo listicle (formato 3) presentando los 3 productos.
2. Una ficha individual por producto (formato 4), misma plantilla repetida.
3. Un "VS" (formato 1) para el producto que tenga comparación más clara (ej. pistola masajeadora vs. masajes profesionales).
4. Post institucional de catálogo completo (formato 6) para fijar en el perfil, con WhatsApp de contacto.



- Definir y aplicar de verdad el verde menta en el editor de temas (hoy no existe en el sitio).
- Extender el navy del hero al resto del sitio si querés consistencia (header, footer, botones).
- Reemplazar las reseñas y el badge "970+ reseñas verificadas" por contenido real antes de lanzar.
- Tono de Instagram: no hay posts todavía para analizar.
