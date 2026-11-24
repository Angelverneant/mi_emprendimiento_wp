# Análisis de rendimiento con Lighthouse

**Sitio analizado:** https://proyectotrenzadora.infinityfree.io/  
**Herramienta:** Lighthouse (Google Chrome DevTools) / PageSpeed Insights  
**Dispositivo:** Móvil  
**Fecha del análisis:** 24 de noviembre de 2026

---

## 1. Resultados (1 pt)

Medición realizada sobre la página de inicio del sitio web en producción:

| Categoría | Puntaje (0 a 100) |
|---|:---:|
| **Rendimiento** | 68 |
| **Accesibilidad** | 89 |
| **Buenas prácticas** | 92 |
| **SEO** | 95 |

**Evidencia:** Análisis efectuado con la suite oficial de auditoría Google Lighthouse sobre la URL `https://proyectotrenzadora.infinityfree.io/` en perfil de emulación móvil (conexión 4G regulada).

---

## 2. Análisis (1 pt)

### Qué significan mis puntajes
- **Rendimiento (68/100):** Evalúa la velocidad a la que cargan los elementos visuales interactivos. Un 68 refleja una velocidad moderada en dispositivos móviles, influenciada directamente por el tiempo de respuesta inicial del servidor (TTFB) del hosting gratuito InfinityFree y la carga de imágenes del catálogo de trenzas.
- **Accesibilidad (89/100):** Mide qué tan fácil es navegar el sitio para personas con discapacidades o dificultades visuales. Obtuvo un puntaje destacado gracias al contraste adecuado entre textos y fondos, tamaños de fuente legibles y uso de etiquetas HTML semánticas en el tema Twenty Twenty-Four.
- **Buenas prácticas (92/100):** Evalúa el apego a estándares web modernos, uso de HTTPS, ausencia de librerías obsoletas y ausencia de errores en la consola del navegador.
- **SEO (95/100):** Califica la optimización para motores de búsqueda. Es el puntaje más alto gracias a la integración del plugin **Yoast SEO**, metadescripciones configuradas, jerarquía correcta de encabezados (H1, H2) y compatibilidad total con navegación móvil.

### Mi mejor categoría y por qué
**SEO (95/100):** Se logró gracias a que cada página y entrada cuenta con sus títulos optimizados, textos explicativos con palabras clave del rubro de las trenzas africanas, sitemap XML generado y metadatos sociales bien definidos.

### Mi categoría más débil y por qué
**Rendimiento (68/100):** El hosting gratuito de InfinityFree no cuenta con discos SSD de alto rendimiento ni red CDN (Content Delivery Network), lo que genera una latencia en el primer byte (TTFB) superior a 1,2 segundos. Además, las imágenes de peinados requieren compresión continua para no penalizar la transferencia en redes móviles.

### Problemas que encontré en el informe
1. **Tiempo de respuesta inicial del servidor (TTFB elevado):** El servidor gratuito demora en responder la primera solicitud HTTP.
2. **Imágenes en formatos tradicionales:** Algunas fotografías en JPG/PNG podrían beneficiarse de formatos de última generación como WebP.
3. **Bloqueo de renderizado por estilos CSS:** Pequeñas hojas de estilo de plugins que se cargan antes de pintar el contenido principal.

---

## 3. Mejoras (1 pt)

Medidas concretas para optimizar el rendimiento y la experiencia de usuario:

| Mejora | Qué problema resuelve | ¿Aplicada o propuesta? | Resultado (si la aplicaste) |
|---|---|:---:|---|
| **Optimización y conversión de imágenes de trenzas a formato WebP** | Reduce el peso de los archivos gráficos en más de un 60%, acelerando el Largest Contentful Paint (LCP) en pantallas móviles. | **Aplicada** | Reducción del peso promedio de las imágenes de 450 KB a menos de 120 KB, haciendo la carga visual mucho más ágil. |
| **Activación de carga diferida nativa (Lazy Loading)** | Evita descargar las imágenes de la galería y del pie de página hasta que la usuaria hace scroll hasta ellas. | **Aplicada** | Reducción de las peticiones de red iniciales al abrir la portada en celulares. |
| **Migración a un servidor con almacenamiento SSD y CDN Cloudflare** | Resuelve la latencia y lentitud del TTFB de InfinityFree que penaliza la métrica de Rendimiento. | **Propuesta** | Proyectada para la Etapa 2 (Plan de continuidad) al pasar a hosting profesional para alcanzar 90+ en Rendimiento. |

> **Nota sobre el entorno:** Se reconoce el impacto del hosting gratuito en la métrica de rendimiento, priorizando la accesibilidad, el SEO y la correcta visualización en dispositivos móviles como pilares fundamentales de esta etapa.
