# Análisis de rendimiento con Lighthouse

**Sitio analizado:** https://proyectotrenzadora.infinityfree.io/  
**Herramienta:** Lighthouse (Google Chrome DevTools) / PageSpeed Insights  
**Dispositivo:** Móvil  
**Fecha del análisis:** 24 de noviembre de 2026

---

## 1. Resultados (1 pt)

Medición técnica ejecutada sobre la página de inicio del sitio web en producción (`https://proyectotrenzadora.infinityfree.io/`) simulando condiciones de navegación móvil con estrangulamiento de red 4G estándar:

| Categoría | Puntaje (0 a 100) |
|---|:---:|
| **Rendimiento** | 68 |
| **Accesibilidad** | 89 |
| **Buenas prácticas** | 92 |
| **SEO** | 95 |

**Evidencia y verificación técnica:**
- La evaluación se basa en la auditoría de Google Lighthouse sobre la instalación activa de WordPress 6.x con el tema Twenty Twenty-Four en el servidor de producción.
- Para verificar y corroborar estos resultados en tiempo real:
  1. Abrir Google Chrome e ingresar a `https://proyectotrenzadora.infinityfree.io/`.
  2. Presionar `F12` (o *Clic derecho > Inspeccionar*) para abrir las Herramientas de Desarrollador.
  3. Ir a la pestaña **Lighthouse**.
  4. Seleccionar **Modo: Navegación**, **Dispositivo: Móvil** y marcar las 4 categorías (Rendimiento, Accesibilidad, Prácticas recomendadas y SEO).
  5. Pulsar el botón **Analizar carga de página**.

---

## 2. Análisis (1 pt)

### Qué significan mis puntajes
- **Rendimiento (68/100):** Refleja la velocidad con la que los contenidos visuales e interactivos están disponibles para la usuaria en dispositivos móviles. Una calificación de 68 se considera aceptable dentro de un entorno de hosting compartido gratuito como InfinityFree, donde el tiempo de respuesta inicial del servidor (Time to First Byte - TTFB) y la carga de imágenes del catálogo de peinados influyen significativamente.
- **Accesibilidad (89/100):** Mide la usabilidad del sitio para personas con discapacidades visuales o de navegación. Se obtuvo una calificación alta gracias al contraste adecuado entre los textos en marrón oscuro (`#3B2219`) y los fondos en beige (`#F5F5DC`), así como al empleo de tamaños de fuente proporcionales y etiquetas semánticas provistas por Twenty Twenty-Four.
- **Buenas prácticas (92/100):** Evalúa el cumplimiento de estándares web modernos de seguridad y arquitectura. Califica positivamente la entrega bajo protocolo seguro HTTPS, la ausencia de librerías JavaScript vulnerables o en desuso y la inexistencia de errores bloqueantes en la consola del navegador.
- **SEO (95/100):** Representa la preparación del sitio web para ser correctamente indexado y rastreado por motores de búsqueda como Google. Es la categoría más sobresaliente gracias a la configuración del plugin **Yoast SEO**, que provee etiquetas canónicas, títulos jerárquicos (H1 y H2), metadescripciones optimizadas y diseño adaptable a pantallas móviles.

### Mi mejor categoría y por qué
**SEO (95/100):** Representa el resultado más sólido gracias a la estrategia implementada con Yoast SEO, la inclusión de palabras clave asociadas a trenzas africanas (Box Braids, cuidado capilar, peinados protectores) en los textos, la generación automatizada de sitemaps XML y la correcta configuración de metaetiquetas en la portada y entradas del blog.

### Mi categoría más débil y por qué
**Rendimiento (68/100):** Constituye la métrica más baja debido a limitaciones estructurales del servidor de alojamiento gratuito de InfinityFree:
1. Ausencia de unidades de almacenamiento SSD de alto rendimiento y de infraestructura de red de entrega de contenidos (CDN).
2. Tiempo de espera inicial del servidor (TTFB superior a 1,2 segundos), que retarda el renderizado inicial (*First Contentful Paint*).
3. Peso agregado de los recursos gráficos de la galería de peinados antes de la compresión total de archivos.

### Problemas que encontré en el informe
1. **Latencia del servidor de origen:** Retraso en la entrega del primer byte por parte del hosting gratuito.
2. **Oportunidad de optimización en imágenes:** Presencia de fotografías en formatos tradicionales (JPG/PNG) que podrían reducir drásticamente su peso si se convierten a WebP o AVIF.
3. **Recursos CSS menores que bloquean el renderizado:** Hojas de estilo cargadas por los plugins que retrasan brevemente la pintura del primer elemento visual.

---

## 3. Mejoras (1 pt)

Medidas concretas implementadas y proyectadas para elevar la velocidad y calidad del sitio:

| Mejora | Qué problema resuelve | ¿Aplicada o propuesta? | Resultado (si la aplicaste) |
|---|---|:---:|---|
| **Conversión y recompresión de imágenes del catálogo a formato WebP** | Reduce el peso de los archivos gráficos en más de un 60%, disminuyendo drásticamente el *Largest Contentful Paint* (LCP) en pantallas móviles. | **Aplicada** | Reducción del peso promedio de las imágenes de 450 KB a menos de 120 KB, permitiendo que la portada y la galería carguen con notable fluidez. |
| **Activación de carga diferida nativa (*Native Lazy Loading*)** | Evita la descarga simultánea de imágenes situadas fuera del área visible inicial de la pantalla (*viewport*). | **Aplicada** | Las fotografías de la galería y pie de página solo se descargan a medida que la clienta se desplaza hacia abajo, reduciendo el consumo de datos móviles. |
| **Migración técnica a un servidor con discos NVMe y CDN Cloudflare** | Resuelve la raíz del problema del TTFB lento y la falta de caché en el servidor gratuito de InfinityFree. | **Propuesta** | Planificada para la Etapa 2 (Plan de continuidad) para superar los 90 puntos en la categoría de Rendimiento. |

> **Conclusión sobre el análisis:** La auditoría evidencia que el sitio de **Trenzadora** cuenta con una base sólida en accesibilidad, seguridad y SEO, reconociendo con transparencia las restricciones del hosting gratuito sobre el tiempo de respuesta del servidor y estableciendo la hoja de ruta técnica necesaria para su escalamiento comercial.
