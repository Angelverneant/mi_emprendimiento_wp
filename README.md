# Trenzadora · Sitio WordPress

Sitio web en producción para el emprendimiento **Trenzadora**, especializado en peinados con trenzas africanas, cuidado capilar y asesoría de imagen.

- **Sitio en producción:** https://proyectotrenzadora.infinityfree.io/
- **Prototipo en Stitch:** https://stitch.withgoogle.com/
- **Repo del Parcial 02:** https://github.com/Angelverneant/mi_emprendimiento_wp
- **Autor/a:** Andjelica Verneant (Sección MKA1203)

---

## Contexto de la web

**Trenzadora** es un emprendimiento enfocado en el arte, diseño y confección de peinados con trenzas africanas (Box Braids, trenzas pegadas/cornrows, twists y peinados protectores). El sitio web resuelve la necesidad de centralizar el portafolio visual de peinados, educar a las clientas en técnicas de mantención capilar y transparentar la información de servicios, tarifas y contacto. Está dirigido principalmente a personas interesadas en estilos protectores duraderos que cuiden su cabello natural. El objetivo principal es que la usuaria descubra los estilos disponibles, aprenda a mantenerlos mediante el blog y solicite su cotización o cita mediante el formulario de contacto y canal directo de WhatsApp.

---

## Mi tema

- [x] **Tema descargado:** `Twenty Twenty-Four` · https://wordpress.org/themes/twentytwentyfour/

---

## Instrucciones si uso un tema descargado

### Requisitos del tema

| Dato | Mi tema |
|---|---|
| **Nombre y enlace a la ficha** | Twenty Twenty-Four (https://wordpress.org/themes/twentytwentyfour/) |
| **Gratis o de pago** | Gratuito y de código abierto (WordPress.org) |
| **Tipo (clásico o de bloques)** | Tema de bloques (Full Site Editing) |
| **Versión de WordPress que requiere** | WordPress 6.4 o superior |
| **Versión de PHP que requiere** | PHP 7.0 o superior (recomendado PHP 8.1 o superior) |
| **Plugins que necesita (si alguno)** | Ninguno obligatorio; compatible con Yoast SEO, Contact Form 7, FooGallery |
| **Licencia** | GNU General Public License v2 o posterior |

### Cómo llevar mi sitio de Local a producción

Para transferir los datos del entorno local en Local WP hacia el hosting de producción (InfinityFree):

- **Plugin de migración que uso:** All-in-One WP Migration (https://wordpress.org/plugins/all-in-one-wp-migration/) y BackWPup. Versión gratuita con exportación directa en formato `.wpress`.
- **Qué se exporta:** Entradas del blog, páginas estáticas, imágenes de peinados subidas a `uploads/`, menús de navegación y configuración general de la base de datos.

**Pasos para migrar:**
1. **En Local WP:** Con el sitio finalizado, ir a **All-in-One WP Migration > Exportar > Exportar a Archivo**. Se descarga el archivo comprimido del sitio completo.
2. **En producción (InfinityFree):** Instalar un WordPress limpio desde el panel de control (Softaculous), instalar el tema Twenty Twenty-Four y activar el plugin All-in-One WP Migration.
3. **Importa:** Ir a **All-in-One WP Migration > Importar** y subir el archivo `.wpress` exportado.
4. **Revisa:** Ir a **Ajustes > Enlaces permanentes** y pulsar *Guardar cambios* dos veces para regenerar los enlaces; verificar que la página de Inicio esté asignada como portada estática (**Ajustes > Lectura**), comprobar el menú principal y enviar un mensaje de prueba en el formulario de Contacto.
5. **Problemas que tuve y cómo los resolví:** Debido a los límites de tamaño de subida en InfinityFree, se optimizaron las imágenes previamente para que el paquete de respaldo pesara menos de 100 MB, permitiendo una restauración rápida y sin errores de memoria.

---

## Respaldo y reinstalación en otro servidor

El objetivo central de este proyecto es que cualquier persona pueda **respaldar el sitio y reinstalarlo en cualquier servidor profesional**.

### Qué respaldar
- **Los archivos de WordPress:** La carpeta `wp-content` completa (tema Twenty Twenty-Four, plugins instalados y carpeta `uploads` con las fotografías de las trenzas).
- **La base de datos MySQL:** Contiene las páginas, entradas, categorías, usuarios y configuraciones del sitio.

### Cómo respaldo mi sitio
- Utilizando el plugin **BackWPup** o la herramienta nativa de **All-in-One WP Migration**: Se programa un respaldo completo semanal y se descarga una copia manual en formato comprimido (.zip o .wpress) guardada fuera del servidor (en el computador local y Google Drive).

### Cómo reinstalo en un servidor nuevo (Paso a paso)
1. **Requisitos del servidor:** Servidor web Apache o Nginx, PHP 7.4 o superior (ideal PHP 8.2), MySQL 5.7+ o MariaDB 10.3+, y al menos 1 GB de espacio disponible en disco.
2. **Instalar WordPress limpio:** Instalar la versión oficial de WordPress en el nuevo servidor mediante cPanel/Softaculous o descargando WordPress.org a la carpeta raíz (`public_html`).
3. **Restaurar el respaldo:** Instalar el plugin All-in-One WP Migration en el WordPress limpio e importar el archivo `.wpress` de respaldo. *(Método alternativo manual: subir la carpeta `wp-content` vía FTP y restaurar la base de datos `.sql` en phpMyAdmin).*
4. **Ajustar:**
   - Si cambió el dominio, actualizar la URL en la tabla `wp_options` (`siteurl` y `home`).
   - Ir a **Ajustes > Enlaces permanentes** y guardar cambios.
   - Verificar en **Ajustes > Lectura** que la portada sea `Inicio` y la página de entradas sea `Blog`.
5. **Probar:** Navegar por la portada, galería, servicios y blog; verificar la adaptabilidad en celular y enviar un mensaje de prueba desde la página de Contacto para confirmar la recepción del correo.

**Problemas que tuve y cómo los resolví:** En servidores gratuitos la función estándar de correo PHP puede verse limitada; como mitigación se incorporó un botón de enlace directo a WhatsApp en la página de Contacto para asegurar que ninguna clienta quede sin respuesta.

---

## Plugins instalados

| Plugin | Para qué lo uso | Gratis o de pago | Versión probada |
|---|---|---|:---:|
| **Yoast SEO** (obligatorio SEO) | Optimización de títulos, metadescripciones, legibilidad y generación de mapa XML. | Freemium (Gratis) | 7.1.4 |
| **Contact Form 7** (obligatorio contacto) | Formulario para solicitudes de presupuesto, consultas y agendamiento. | Gratuito | 7.1.3 |
| **FooGallery** | Galería visual responsive con lightbox para exhibir el catálogo de peinados de trenzas. | Freemium (Gratis) | 7.1.3 |
| **Smash Balloon Social Photo Feed** | Muestra el feed de publicaciones de Instagram de Trenzadora en el sitio. | Freemium (Gratis) | 7.1.3 |
| **Wordfence Security** | Firewall WAF y escáner de seguridad para proteger el acceso al panel admin. | Freemium (Gratis) | 7.1.4 |

---

## Páginas y entradas

- **Páginas:**
  1. **Inicio:** Portada principal, presentación del emprendimiento, propuesta de valor y llamada a la acción.
  2. **Nosotros:** Historia, dedicación al cuidado capilar y trayectoria de la trenzadora.
  3. **Servicios:** Catálogo detallado de técnicas de trenzas (Box Braids, pegadas, twist) con descripciones.
  4. **Blog:** Sección de artículos informativos y consejos de cuidado capilar.
  5. **Contacto:** Formulario de consulta/cotización con Contact Form 7 y botón directo a WhatsApp.

- **Entradas del blog:**
  1. *Cuidados esenciales para que tus trenzas africanas duren más tiempo* (Consejos de mantenimiento nocturno y uso de gorro de satén).
  2. *Cómo lavar e hidratar tu cuero cabelludo llevando trenzas* (Técnicas de lavado con atomizador e hidratación con aceites).
  3. *Guía de estilos: Box Braids, trenzas pegadas y cómo elegir tu look* (Comparativa de estilos según el largo y ocasión).

---

## Cómo me organicé

Mi planificación inicial, selección de plugins, carta Gantt (5 al 25 de noviembre) y Plan B de riesgos se encuentran documentados en [`proyecto/decisiones.md`](proyecto/decisiones.md). En el Checkpoint del 18 de noviembre se ratificó el uso del tema Twenty Twenty-Four y la identidad bajo la marca Trenzadora.

---

## Plan de continuidad y rendimiento

- **Plan de continuidad (etapa 2 de mi web):** [`proyecto/plan-de-continuidad.md`](proyecto/plan-de-continuidad.md)
- **Análisis de rendimiento con Lighthouse:** [`proyecto/lighthouse.md`](proyecto/lighthouse.md)

---

## Uso de IA

- **Antigravity / Gemini:** Se utilizó asistencia de IA para estructurar y redactar la documentación técnica del repositorio (`decisiones.md`, `plan-de-continuidad.md`, `lighthouse.md` y `README.md`), verificar requisitos y compatibilidad de plugins en WordPress.org y formular la matriz de mitigación de riesgos. Todas las decisiones de diseño, catálogo de peinados y configuración en WordPress fueron validadas y adaptadas a las necesidades reales de Trenzadora.
