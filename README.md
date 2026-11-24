# Trenzadora – Belleza en Trenzas Africanas · Sitio WordPress

Sitio web en producción para el emprendimiento **Trenzadora – Belleza en Trenzas Africanas**, dedicado al arte y estilismo capilar protector, trenzas africanas (Box Braids, cornrows, twists) y cuidado integral del cabello.

- **Sitio en producción:** https://proyectotrenzadora.infinityfree.io/
- **Prototipo en Stitch:** https://stitch.withgoogle.com/
- **Repo del Parcial 02:** https://github.com/Angelverneant/mi_emprendimiento_wp
- **Autor/a:** Andjelica Verneant (Sección MKA1203)

---

## Contexto de la web

**Trenzadora – Belleza en Trenzas Africanas** es un emprendimiento especializado en el diseño, elaboración y mantenimiento de peinados tradicionales y contemporáneos con trenzas africanas (Box Braids, trenzas pegadas o cornrows, trenzas senegalesas y peinados protectores). 

El sitio web resuelve la necesidad fundamental de profesionalizar la presencia digital del negocio, exhibir un catálogo visual fidedigno de los trabajos realizados, transparentar los tiempos y tarifas de atención, y educar a la comunidad sobre el cuidado y la salud del cabello natural. La plataforma está dirigida principalmente a mujeres, hombres y jóvenes que buscan peinados de alta durabilidad que protejan su hebra capilar con una estética cuidada y moderna. El objetivo de conversión es que la visitante explore el catálogo, conozca las técnicas en el blog y coordine su cita o solicite presupuesto a través del formulario de contacto y canal directo de WhatsApp.

### Identidad visual de la marca
El sitio web proyecta una estética cálida, profesional y acogedora inspirada en la cultura afrodescendiente y la cosmética natural, basada en tres colores corporativos:
- **Beige (`#F5F5DC` / `#F7F4EE`):** Fondo principal y áreas de descanso visual, aportando luminosidad, limpieza y elegancia.
- **Marrón oscuro (`#3B2219` / `#2C1810`):** Color dominante para textos, títulos y bordes, simbolizando la firmeza, la raíz y el cabello natural con excelente legibilidad y contraste.
- **Dorado (`#D4AF37` / `#C5A059`):** Color de acento aplicado a botones de llamada a la acción (CTA), destacados, íconos y líneas divisorias, reflejando distinción, belleza y brillo capilar.

---

## Mi tema

- [x] **Tema descargado:** `Twenty Twenty-Four` · https://wordpress.org/themes/twentytwentyfour/

---

## Instrucciones si uso un tema descargado

### Requisitos del tema

| Parámetro | Especificación de Twenty Twenty-Four |
|---|---|
| **Nombre y enlace a la ficha** | Twenty Twenty-Four (https://wordpress.org/themes/twentytwentyfour/) |
| **Gratis o de pago** | 100% Gratuito y de código abierto (Directorio oficial de WordPress.org) |
| **Tipo de tema** | Tema de bloques (Full Site Editing / Edición del Sitio Completo) |
| **Versión de WordPress requerida** | WordPress 6.4 o superior |
| **Versión de PHP requerida** | PHP 7.0 o superior (recomendado PHP 8.1 o PHP 8.2) |
| **Plugins obligatorios** | Ninguno; alta compatibilidad nativa con bloques Gutenberg, Yoast SEO y Contact Form 7 |
| **Licencia** | GNU General Public License v2 o posterior |

### Cómo llevar mi sitio de Local a producción

Para transferir la totalidad de la estructura, diseño y contenidos desde el entorno de desarrollo local (Local WP) hacia el servidor de producción en InfinityFree:

- **Herramienta de migración utilizada:** Plugin oficial **All-in-One WP Migration** (https://wordpress.org/plugins/all-in-one-wp-migration/) complementado con **BackWPup**. Se utiliza la versión gratuita que permite exportar e importar el sitio completo en un único archivo empaquetado `.wpress`.
- **Contenido transferido:** Base de datos relacional (entradas, páginas, metadatos de Yoast SEO, configuraciones y usuarios), temas, plugins instalados y archivos multimedia de la biblioteca (`wp-content/uploads/`).

**Procedimiento de migración:**
1. **Fase local (Local WP):**
   - Asegurar que todas las imágenes de peinados estén optimizadas y los enlaces permanentes configurados.
   - Acceder a **All-in-One WP Migration > Exportar > Exportar a: Archivo**.
   - Descargar el archivo `.wpress` resultante al almacenamiento local.
2. **Fase de producción (InfinityFree):**
   - Instalar una instancia limpia de WordPress mediante Softaculous en el panel de control.
   - Instalar y activar el tema **Twenty Twenty-Four** y el plugin **All-in-One WP Migration**.
   - Ir a **All-in-One WP Migration > Importar** y arrastrar el archivo `.wpress`.
3. **Ajustes posteriores a la importación:**
   - Ir a **Ajustes > Enlaces permanentes** y pulsar *Guardar cambios* dos veces consecutivas para regenerar las reglas de reescritura `.htaccess`.
   - Verificar en **Ajustes > Lectura** que la portada estática esté asignada a la página `Inicio` y las entradas a `Blog`.
   - Comprobar que los menús mantengan las rutas correctas y enviar un mensaje de prueba a través de Contact Form 7.
4. **Resolución de incidencias:** Dado que los servidores compartidos gratuitos presentan límites bajos en `upload_max_filesize`, se mantuvo el tamaño total de la exportación bajo los 80 MB mediante la compresión de fotografías a formatos eficientes.

---

## Respaldo y reinstalación en otro servidor

El objetivo de esta sección es proporcionar una guía técnica reproducible para que cualquier desarrollador o administradora pueda respaldar y reinstalar el sitio en cualquier servidor profesional.

### Qué respaldar
1. **Directorio `wp-content/` completo:**
   - `themes/twentytwentyfour/`: Estructura visual y plantillas de bloques personalizadas.
   - `plugins/`: Yoast SEO, Contact Form 7, FooGallery, Smash Balloon y Wordfence.
   - `uploads/`: Fotografías de peinados organizadas por año y mes.
2. **Base de datos MySQL / MariaDB:**
   - Volcado completo de tablas (`.sql`) con codificación UTF-8 / `utf8mb4`, que almacena páginas, entradas del blog, formularios, configuraciones de diseño y taxonomías.

### Cómo respaldar el sitio
- **Método automatizado:** Configuración del plugin **BackWPup** programado semanalmente para empaquetar la base de datos y la carpeta `wp-content` en un archivo comprimido `.zip` descargado localmente.
- **Método de respaldo rápido:** Exportación manual con **All-in-One WP Migration**, descargando el archivo `.wpress` y archivándolo en una carpeta de almacenamiento seguro (Google Drive / disco externo).

### Guía de reinstalación paso a paso en un nuevo servidor
1. **Verificación de requisitos del nuevo hosting:**
   - Servidor web Apache o Nginx con módulo `mod_rewrite` habilitado.
   - PHP 7.4, 8.1 o 8.2 con extensiones `curl`, `mbstring`, `openssl`, `zip` y `gd` activas.
   - Base de datos MySQL 5.7+ o MariaDB 10.3+.
   - Al menos 1 GB de espacio disponible y soporte SSL (Let's Encrypt).
2. **Despliegue inicial de WordPress:**
   - Instalar WordPress limpio a través del instalador automático del hosting (cPanel, Plesk) o subiendo los archivos oficiales de WordPress.org a la raíz `public_html`.
3. **Restauración del respaldo:**
   - Instalar el plugin **All-in-One WP Migration** en la instalación limpia.
   - Importar el archivo `.wpress` y confirmar la sobreescritura de la base de datos.
   - *(Vía manual alternativa: Subir la carpeta `wp-content/` mediante FTP/SFTP e importar el archivo `.sql` a través de phpMyAdmin tras ajustar el prefijo de tablas).*
4. **Ajustes de dominio y configuración:**
   - Si el sitio cambia de dominio, ejecutar la actualización de URL en la base de datos (campos `siteurl` y `home` en la tabla `wp_options`).
   - Iniciar sesión en el panel de administración de WordPress.
   - Entrar en **Ajustes > Enlaces permanentes** y pulsar *Guardar cambios*.
   - Revisar en **Ajustes > Lectura** la asignación de la página de Inicio y Blog.
5. **Protocolo de verificación post-instalación:**
   - Comprobar la visualización responsiva del home y la paleta institucional (beige, marrón oscuro y dorado).
   - Revisar que la galería de FooGallery cargue correctamente con su visualizador lightbox.
   - Realizar un envío de prueba desde el formulario de contacto para comprobar la entrega de mensajes y el funcionamiento del botón directo de WhatsApp.

---

## Plugins instalados

| Plugin | Propósito en el sitio | Versión | Tipo de licencia | Compatibilidad comprobada |
|---|---|:---:|:---:|:---:|
| **Yoast SEO** (obligatorio) | Optimización para motores de búsqueda, edición de metadatos, análisis de legibilidad y sitemaps XML. | 7.1.4 | Freemium | Total con temas de bloques |
| **Contact Form 7** (obligatorio) | Formulario de contacto para presupuestos, consultas de clientas y solicitudes de citas. | 7.1.3 | Gratuito | Integración por shortcode y bloque nativo |
| **FooGallery** | Galería fotográfica responsive para el catálogo de estilos y peinados de trenzas. | 7.1.3 | Freemium | Integración con bloques Gutenberg y lightbox |
| **Smash Balloon Social Photo Feed** | Despliegue dinámico de las publicaciones del Instagram oficial del emprendimiento. | 7.1.3 | Freemium | Compatible con shortcode y bloque nativo |
| **Wordfence Security** | Cortafuegos (WAF) a nivel de aplicación, protección del inicio de sesión y detección de malware. | 7.1.4 | Freemium | Compatible a nivel de núcleo de WordPress |

---

## Páginas y entradas

### Páginas del sitio
1. **Inicio:** Portada institucional con propuesta de valor, llamado a la acción y bienvenida a la comunidad de trenzas africanas.
2. **Nosotros:** Historia, dedicación al cuidado capilar, trayectoria y valores de la marca.
3. **Servicios:** Catálogo descriptivo de técnicas (Box Braids, trenzas pegadas/cornrows, twists) con especificaciones de tiempo y estilo.
4. **Blog:** Centro de publicaciones con consejos prácticos de mantenimiento capilar y tendencias.
5. **Contacto:** Formulario operativo de consultas y botón directo de atención personalizada por WhatsApp.

### Entradas del blog publicadas
1. *Cuidados esenciales para que tus trenzas africanas duren más tiempo:* Recomendaciones de protección nocturna con gorro de satén e hidratación ligera.
2. *Cómo lavar e hidratar tu cuero cabelludo llevando trenzas:* Guía técnica de lavado con atomizador y secado seguro para evitar acumulación de humedad.
3. *Guía de estilos: Box Braids, trenzas pegadas y cómo elegir tu look:* Análisis comparativo para seleccionar el peinado ideal según la ocasión y tipo de cabello.

---

## Cómo me organicé

El desarrollo del proyecto, la selección técnica de plugins, la carta Gantt (5 al 25 de noviembre) y la matriz de riesgos se detallan en [`proyecto/decisiones.md`](proyecto/decisiones.md). En el Checkpoint del 18 de noviembre se ratificó el uso del tema Twenty Twenty-Four y la identidad de marca bajo el nombre **Trenzadora – Belleza en Trenzas Africanas**.

---

## Plan de continuidad y rendimiento

- **Plan de continuidad (etapa 2 de mi web):** [`proyecto/plan-de-continuidad.md`](proyecto/plan-de-continuidad.md)
- **Análisis de rendimiento con Lighthouse:** [`proyecto/lighthouse.md`](proyecto/lighthouse.md)

---

## Uso de IA

- **Herramientas utilizadas:** Antigravity / Gemini 3.8 Flash.
- **Alcance y ajustes realizados:** Se utilizó asistencia de inteligencia artificial para la redacción técnica estructurada de los documentos Markdown (`decisiones.md`, `plan-de-continuidad.md`, `lighthouse.md` y `README.md`), la verificación de versiones oficiales en WordPress.org y el diseño de contingencias técnicas. Todos los requerimientos del rubro, paleta cromática (beige, marrón oscuro y dorado), contenidos del blog y configuración en WordPress fueron supervisados, revisados y validados manualmente para asegurar coherencia académica y técnica.
