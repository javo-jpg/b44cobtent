# Sistema de contenido B44 — cómo funciona

Guía del flujo con el que se produce, revisa y programa el contenido de redes de B44 Studio (IG, FB, TikTok, LinkedIn).

---

## 1. Resumen en una línea

**Material (fotos, videos, chats, juntas) → piezas renderizadas (HTML → imagen / ffmpeg → video) → repo `javo-jpg/b44cobtent` → Metricool (programado y autopublicado) → página de revisión.**

Nada se sube a mano: todo, incluidas las stories, se publica solo desde Metricool.

---

## 2. Piezas del sistema

| Pieza | Para qué sirve |
|---|---|
| **Fuentes** | Fotos/videos de Drive, IG de colaboradores (con su crédito), WhatsApp exportado, cotizaciones, juntas de Otter |
| **Plantillas (HTML)** | Posts 1080×1350, stories y reels 1080×1920, portadas. Colores B44: `#1D1D1B` negro, `#EFEBE0` crema, `#E3C93B` amarillo. Tipografías Montserrat / Everett |
| **Render** | Playwright convierte HTML a PNG/JPG; ffmpeg arma los videos y les pone música |
| **Música** | Epidemic Sound (licenciada) |
| **Repo** `javo-jpg/b44cobtent` | Guarda cada pieza final, el copy y `calendario.csv`. Metricool toma los archivos de aquí (raw.githubusercontent) |
| **Metricool** (brand 7566826, CDMX) | Programa y publica: IG + FB (+ TikTok en reels), LinkedIn con copy propio, stories IG + FB |
| **Página de revisión** (artifact) | Calendario visual del mes con imágenes, videos, copies, highlights y pendientes |

### Estructura del repo

```
2026-11/
  v2/<MM-DD>_<ID>/    pieza de feed: imágenes/video, portada, copy.txt
  v2/stories/         stories del mes
  v2/prev/  v2/v3/    versiones corregidas (se usan rutas nuevas para evitar caché)
highlights/portadas/  portadas de highlights
calendario.csv        todo el calendario en una tabla
```

---

## 3. Flujo mensual

1. **Recopilar.** Juntas (Otter), pendientes del equipo, eventos (ej. Brasa Brava), servicios a empujar (daypass, paquetes, Renueva tu Book), material nuevo.
2. **Planear.** Calendario: feed casi diario, stories todos los días, LinkedIn 2–3 veces por semana. Cada pieza tiene objetivo (reservar, evento, comunidad).
3. **Producir.** Se renderizan posts, carruseles, reels, stories y portadas.
4. **Revisar (QA).** Se revisa cuadro por cuadro con las reglas de la sección 4.
5. **Subir al repo** y hacer commit.
6. **Programar en Metricool.** Se crean/actualizan los posts. Cada actualización cambia el `id` del post pero no el `uuid`.
7. **Publicar la página de revisión** para que el equipo vea el mes completo.
8. **Ajustar en vivo.** Cambios de precio, fotos nuevas o correcciones → se re-renderiza la pieza, se sube con nombre nuevo y se actualiza el post en Metricool.

---

## 4. Reglas de calidad (no negociables)

**Caras y personas**
- Ningún texto tapa caras. Si hay personas, el título va abajo o en una franja sólida.
- No se recortan caras ni fotos de creadores (las fotos de terceros se muestran completas).
- Portadas de reel: todo lo importante dentro del **recorte 3:4 del grid** (zona central y 240–1680 de 1920). El grid de IG corta arriba y abajo.

**Zonas seguras**
- Reels: texto entre x 72–880, y 270–1380 (fuera de la barra derecha y el caption).
- Stories: texto entre y 250–1640; barra de CTA en y ≈1480.
- Posts: márgenes de 96 px.

**Movimiento**
- Sin zoom/pan sobre fotos. El movimiento viene de video real.

**Copy**
- Decir lo que **sí incluye**, nunca lo que no incluye.
- CTA siempre escrito en la imagen (las stories se publican sin stickers).
- Reservas en la web (b44.studio), excepto Renueva tu Book y eventos: DM o WhatsApp 55 3522 3320.

**Contenido**
- *Hecho en B44*: cronológico, del más viejo al más nuevo, con créditos completos y “Todo el contenido pertenece a sus autores”.
- No repostear como colab lo que ya está en el perfil.
- Casa Roja: solo fotos de la chimenea, nunca del cuarto amarillo.
- Casa 1904: no promover mientras dure la obra.

---

## 5. Tipos de contenido

| Tipo | Formato | Redes |
|---|---|---|
| Post / carrusel | 1080×1350 | IG + FB (+ LinkedIn con texto propio) |
| Reel | 1080×1920 video + portada | IG + FB + TikTok |
| Story | 1080×1920 imagen o video corto | IG + FB, autopublicada |
| Highlights | Portadas en `highlights/portadas` | Se fijan a mano en IG |

**Líneas de noviembre:** Daypass y paquetes · Renueva tu Book (miércoles y domingo) · Brasa Brava (countdown y precio especial $500 la última semana) · Espacios · Hecho en B44 · “Mándanos tu proyecto por DM”.

---

## 6. Highlights

| Highlight | Stories que se guardan |
|---|---|
| Daypass | DP_b, PK_a, PK_b |
| Reservar | W1_b, W2_b |
| ¿Qué set? | W2_a, W_roja, W4_a, W_garza, W_cristina, W_marte |
| Renueva tu Book | RB1_info, RB2_trio, RB3_how, RB4_faq, RB7_hazel, video RB1 |
| Brasa Brava → “Experiencias” después del 22 | BB1_info, BB2_chef, video BB1, recap |
| Hecho en B44 | UGC |
| Scouting / Equipo | W3_b / W4_b |

---

## 7. Qué se hace a mano

- Fijar stories en highlights.
- Cambiar portadas de reels ya publicados (IG no deja hacerlo por API).
- Compartir en grupos de Facebook (Metricool no los programa).
- Mandar la invitación a invitados por WhatsApp.

## 8. Cómo pedir cambios

Manda: **qué pieza** (fecha o captura), **qué está mal** y **qué quieres**. Se corrige la pieza, se sube versión nueva al repo y se actualiza en Metricool; la página de revisión se refresca.
