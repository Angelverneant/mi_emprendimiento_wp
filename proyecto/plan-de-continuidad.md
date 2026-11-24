# Plan de continuidad · Etapa 2 de mi sitio

**Emprendimiento:** Trenzadora (Proyecto trenzas marketing)  
**Sitio de la etapa 1:** https://proyectotrenzadora.infinityfree.io/  
**Fecha:** 25 de noviembre de 2026

---

## 1. Qué quedó fuera de la etapa 1 y por qué (3 pts)

Para el lanzamiento inicial de la web se priorizó la presencia digital, la exhibición del catálogo de estilos de peinados y el contacto directo con las clientas. Las siguientes funcionalidades fueron planificadas pero quedaron reservadas para la segunda etapa del proyecto:

| Funcionalidad | Por qué quedó fuera (tiempo, recursos, costo, conocimientos) | Qué aporta a mi emprendimiento |
|---|---|---|
| **Tienda online con WooCommerce (venta de extensiones y productos capilares)** | **Reglas del encargo y recursos:** La pauta de la Etapa 1 prohibió expresamente carros de compra y pasarelas de pago para acotar el alcance. Además, requiere gestionar inventario físico de kanekalon, envíos y validación de pasarelas bancarias (Webpay / Stripe). | Permitirá diversificar ingresos vendiendo extensiones de cabello, geles fijadores, aceites hidratantes y gorros de satén directamente a todo el país, sin depender únicamente de las horas de peinado presencial. |
| **Sistema de reserva y agendamiento automático de citas en línea** | **Tiempo y conocimientos técnicos:** Configurar la sincronización de calendarios bidireccionales con Google Calendar, tiempos variables por tipo de peinado (de 2 a 6 horas) y cobro de abonos previos requería pruebas extensas que excedían el plazo de esta etapa. | Automatiza la recepción de citas las 24 horas, reduce cancelaciones mediante recordatorios automáticos por WhatsApp/correo y evita la fricción de coordinar disponibilidad manualmente. |
| **Galería avanzada con filtros por técnica y largo de trenzas** | **Recursos y costo:** La versión gratuita de FooGallery cumple con la visualización adaptativa, pero los filtros dinámicos por categorías (ej. *box braids finas*, *trenzas pegadas*, *peinados para niñas*) y búsqueda por etiquetas requieren la versión de pago FooGallery Pro. | Mejora la experiencia de usuario facilitando que cada clienta encuentre en segundos el estilo exacto que desea cotizar antes de agendar. |
| **Boletín informativo y fidelización de clientas (Newsletter)** | **Tiempo:** Se priorizó redactar los contenidos de las páginas principales y las 3 entradas del blog. No se disponía de tiempo para diseñar plantillas de email y automatizaciones de bienvenida. | Mantiene informadas a las clientas habituales con ofertas estacionales, consejos mensuales de cuidado capilar y lanzamientos de nuevas técnicas. |

---

## 2. Recursos que necesito (2 pts)

Para llevar a cabo la Etapa 2 con éxito se requerirán los siguientes plugins, herramientas y capacitaciones:

| Funcionalidad | Plugin o herramienta | Gratis o de pago | Costo aproximado | Qué tendría que aprender |
|---|---|---|---|---|
| **Tienda y pagos online** | WooCommerce + Transbank Webpay Plus | Plugin gratuito; comisión bancaria por venta | $0 inicial + 2,5% a 3,5% por transacción con tarjeta | Configuración de impuestos, zonas de envío y pasarelas de pago en moneda local (CLP). |
| **Agendamiento de citas** | Amelia Booking o Simply Schedule Appointments | Freemium (versión Pro recomendada para pagos) | Gratis versión básica / ~$49 a $79 USD anuales la versión Pro | Configurar franjas horarias, descansos entre peinados y cobro de abono de reserva. |
| **Filtros de galería visual** | FooGallery PRO | De pago | ~$39 USD anuales | Manejo de taxonomías avanzadas, lightbox de alta resolución y etiquetas de búsqueda. |
| **Email marketing y fidelización** | MailPoet o Brevo (Sendinblue) | Freemium (gratuito hasta 500 contactos) | $0 inicial | Automatización de secuencias de correo de bienvenida y segmentación de clientas. |

### Servidor y hosting para la Etapa 2

Para la segunda etapa es **indispensable migrar desde InfinityFree a un hosting profesional compartido o VPS básico** (por ejemplo, Hostinger Business o SiteGround):
- **Capacidad y almacenamiento:** Mínimo 15-20 GB de almacenamiento SSD NVMe para soportar el catálogo de productos de WooCommerce y fotografías en alta definición.
- **Rendimiento PHP y base de datos:** PHP 8.2 o superior con `memory_limit` de al menos 256 MB (ideal 512 MB) para ejecutar procesos de checkout sin cuelgues, y base de datos MariaDB sin límites restrictivos de consultas por hora (eliminando los errores 429 y 500 de InfinityFree).
- **Seguridad y SSL:** Certificado SSL comercial o Let's Encrypt automatizado permanente con protocolo HTTP/2 o HTTP/3, indispensable para procesar pagos seguros con tarjeta de crédito/débito.
- **Dominio propio:** Adquisición de un dominio `.cl` (a través de NIC Chile, ~$12.000 CLP/año) para transmitir seriedad y reconocimiento de marca local.

---

## 3. Priorización y cronograma (2 pts)

Plan ordenado para implementar las mejoras en un periodo de dos meses posteriores a la entrega final:

| Prioridad | Qué hago | Cuándo (mes o semana) | Resultado esperado |
|---|---|---|---|
| **1** | **Migración a hosting profesional y dominio propio `.cl`** | Diciembre 2026 (Semanas 1 y 2) | Sitio con carga ultrarrápida, certificado SSL activo sin advertencias y correo corporativo `@trenzadora.cl`. |
| **2** | **Implementación del sistema de reservas de citas** | Diciembre 2026 (Semanas 3 y 4) | Calendario operativo donde las clientas pueden agendar su cita de trenzas seleccionando fecha y peinado. |
| **3** | **Instalación y configuración de WooCommerce** | Enero 2027 (Semanas 1 y 2) | Catálogo de productos (extensiones de kanekalon, gorros de satén, fijadores) con pasarela Webpay habilitada. |
| **4** | **Galería con filtros avanzados y captura de newsletter** | Enero 2027 (Semanas 3 y 4) | Galería visual categorizada y formulario de suscripción a consejos capilares con descuento de bienvenida. |

---

## 4. Riesgos y mitigación (1 pt)

| Riesgo | Qué haría | Cuándo se activa |
|---|---|---|
| **Los costos de licencias o pasarelas superan el presupuesto inicial.** | Iniciar la etapa con las versiones gratuitas de los plugins (Amelia Free y pagos de reserva mediante transferencia bancaria manual validada por WhatsApp) antes de adquirir licencias Pro. | Si en el primer mes de evaluación los ingresos no justifican el pago de suscripciones en dólares. |
| **Incompatibilidad entre WooCommerce y el tema Twenty Twenty-Four.** | Utilizar un tema secundario optimizado para comercio (como Astra o Storefront) o diseñar una plantilla de tienda limpia mediante el editor de bloques nativo. | Si al activar WooCommerce se producen fallos de maquetación en las páginas de producto o carrito. |
| **Las clientas no se adaptan al sistema de reservas y prefieren escribir por WhatsApp.** | Mantener de manera prominente el botón flotante de WhatsApp en la cabecera y en la página de reservas como alternativa directa y personalizada. | Si durante las primeras dos semanas de lanzamiento más del 40% de las reservas siguen solicitándose vía mensaje directo. |
