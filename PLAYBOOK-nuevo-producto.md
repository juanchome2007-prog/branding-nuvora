# Playbook: lanzar un producto nuevo en Nuvora

Mismo proceso que se usó con el blanqueador de carbón de coco (oct 2026). Seguir los pasos en orden y no saltear la validación de números.

## 0a. Filtro de producto (MUST + puntaje, pasa con 15/20)
Reconstruido el 17/10/2026 (el material original del mentor se perdió). Ajustar si el dueño recuerda criterios distintos.

**MUST (si falla uno, se descarta):**
1. Meta lo deja anunciar: sin réplicas de marca, sin claims médicos ni resultados garantizados, sin categoría prohibida.
2. Precio de venta ≥ 3× el costo (producto + traída), y el margen del pack cubre un costo por venta de ~$400 y deja ganancia.
3. Resuelve un problema o un deseo claro.
4. Se puede demostrar en video.
5. Proveedor con stock y entrega rápida.
6. Se puede enviar por DAC: chico, liviano, no frágil, no peligroso.

**Puntaje (0, 1 o 2 cada uno; máximo 20):**
| # | Criterio | 0 | 1 | 2 |
|---|---|---|---|---|
| 1 | Efecto wow / demostración | no se nota | se nota | impacta en 3 s |
| 2 | Fuerza del problema o deseo | leve | medio | dolor/deseo fuerte |
| 3 | Mercado en Uruguay | nicho chico | medio | masivo |
| 4 | Difícil de conseguir en tiendas/súper | está en todos lados | en algunos | casi no se consigue |
| 5 | Precio de impulso ($790–$1.990) | muy fuera | cerca | dentro |
| 6 | Margen | 3× | 4× | 5× o más |
| 7 | Validación (anuncios de otros activos >1 mes) | no hay | pocos | varios, sin saturar |
| 8 | Se puede armar en packs / upsell | no | algo | 2x1, 4x2, 6x3 naturales |
| 9 | Recompra / consumible | no | a veces | se termina y se recompra |
| 10 | Bajo riesgo de quejas/devoluciones | alto | medio | bajo |

**Decisión:** 15–20 → seguir con los pasos de abajo. 12–14 → solo si sobra plata para testear. <12 → descartar.
El blanqueador como referencia: ver puntaje en el chat del 17/10.

## 0. Antes de comprar: ¿el producto da los números?
- Costo unitario + envío del proveedor → costo por unidad.
- Armar la oferta en packs (ej: 2x1 / 4x2 / 6x3) y calcular el margen por pack:
  `precio − producto − empaque (~$15) − MP 6% − envío si es gratis`.
- **Tope de costo por venta** = ese margen. Si con un costo por venta realista (~$400) no queda ganancia, no sirve.
- Cuántas ventas por mes hacen falta para cubrir herramientas (≈$4.613/mes).
- Reglas de Meta: nada de réplicas de marcas, ni promesas médicas o de resultados garantizados. Si el producto no puede anunciarse sin eso, se descarta.
- Primer lote chico para testear (como los 12 frascos iniciales). Reponer en grande solo con un ganador.

## 1. Investigación
- Biblioteca de anuncios de Meta: buscar competidores del producto. De cada anuncio que funcione anotar el **gancho** (primeros 2 s), el **formato** (UGC, producto solo, demostración), la **oferta** y el **CTA**.
- Sacar 4–5 ángulos: dolor/problema, demostración, objeción ("no es magia"), urgencia real, prueba social real.
- Claims: definir qué se puede decir y qué está prohibido, y agregarlo a CLAUDE.md (como la lista del blanqueador).

## 2. Tienda (Shopify)
- Producto con variantes por pack; el inventario de cada variante se calcula con las unidades reales: ⌊F/2⌋, ⌊F/4⌋, ⌊F/6⌋.
- Página de producto: reutilizar el template actual (tema oscuro, tarjeta "Medios de pago" con 12 cuotas por MP, botón WhatsApp para transferencia con el snippet `nv-wa-trust`, línea de pago seguro con candado).
- Para nuevas secciones: duplicar el tema publicado (`themeDuplicate`), editar con `themeFilesUpsert` en la copia, y el dueño la revisa y la publica a mano. **Preguntar cada cambio antes de hacerlo.**
- Envíos: DAC a agencia $260 / domicilio $330 al recibir; gratis solo en el pack grande (lo paga Nuvora).
- Fotos del producto: tapar cualquier "Before/After" o marcas de terceros impresas en la caja.

## 3. Creativos (8 para el testeo: 4 videos + 4 imágenes)
**Videos** (9:16, 30–40 s, estética UGC natural con luz de día):
- Un solo cuerpo (problema → producto → cómo se usa → oferta → CTA) y 4 ganchos distintos.
- Voz: audio grabado por el dueño.
- Cada gancho con una persona distinta del mismo género que la voz, generada en Higgsfield (imagen con `gpt_image_2_5` + referencia del producto).
- Lip sync del gancho: `seedance_2_0` (mode std, `generate_audio: false`, start_image + audio_references). Es el que mejor sigue la voz; kling y wan hicieron muecas.
- Planos de producto/b-roll: kling3_0 std sin sonido.
- Montaje con ffmpeg: duración de cada clip medida con ffprobe; revisar que audio e imagen arranquen juntos.

**Imágenes** (cada una en 1:1, 4:5, 9:16 y 1200×628):
1. Checks / beneficios (los checks se pueden poner desde IG y la franja de oferta la arma Claude).
2. Pack grande sobre fondo negro con precios.
3. Situación cotidiana del problema (como "mate culpable").
4. Pedidos reales (foto del dueño con datos personales tapados).

**Textos:** botón "Comprar", descripción "Pago seguro con Mercado Pago · Envíos a todo Uruguay", un texto principal y un título por creativo con la oferta. Entregar todo como links del CDN de Higgsfield, nunca .zip.

## 4. Campañas (Meta Ads Manager, cuenta 1580817367054085)
1. **Testeo:** CBO con destino a la web, 2 conjuntos (IMG y VID) con los 8 creativos (+ algún ganador previo si aplica), ~$1.000/día, 3–4 días sin tocar.
2. **Lectura:** costo por venta vs el tope, ROAS, CTR y costo por clic, carritos e inicios de pago. Sumar a mano las ventas por WhatsApp/IG que el píxel no ve.
3. Repetir 2–3 testeos con creativos nuevos.
4. **Escalado:** una campaña con todos los ganadores + un conjunto o campaña a WhatsApp.
5. **Iteraciones** de los ganadores (mismo ángulo, otro gancho o formato).
- Promocionar solo desde Ads Manager, nunca con el botón "promocionar" de IG.

## 5. Cuentas
- Sumar el producto a la contabilidad diaria (rutina 21:55): costo por unidad, unidades por pack, stock inicial.
- Sumarlo al cierre de mes y al capital (mercadería a costo).
- Actualizar CLAUDE.md con: oferta, claims permitidos/prohibidos, links de creativos, campañas y ganadores.
