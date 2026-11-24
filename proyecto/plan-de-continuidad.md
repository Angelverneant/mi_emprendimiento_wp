# Plan de continuidad · Etapa 2 de mi sitio

**Emprendimiento:** Trenzadora – Belleza en Trenzas Africanas  
**Sitio de la etapa 1:** https://proyectotrenzadora.infinityfree.io/  
**Fecha:** 25 de noviembre de 2026

---

## 1. Qué quedó fuera de la etapa 1 y por qué (3 pts)

Durante la primera etapa de desarrollo se priorizó establecer la identidad digital del emprendimiento, estructurar el catálogo de servicios de trenzas africanas bajo una estética cuidada (tonos beige, marrón oscuro y dorado) y asegurar canales de comunicación directa. Las siguientes funcionalidades fueron contempladas pero debieron postergarse para la Etapa 2:

| Funcionalidad | Por qué quedó fuera (tiempo, recursos, costo, conocimientos) | Qué aporta a mi emprendimiento |
|---|---|---|
| **Tienda online de productos capilares y extensiones con WooCommerce** | **Restricción de encargo y recursos:** Las pautas académicas de la Etapa 1 prohibieron expresamente el uso de carros de compra y pasarelas de pago para acotar el alcance. Adicionalmente, implementar un e-commerce exige gestionar inventario físico de paquetes de kanekalon, geles fijadores y convenios de pago electrónico (Webpay / Stripe). | Permitirá abrir una línea de negocio complementaria a los servicios de peinado, comercializando extensiones, gorros de satén protectores y aceites nutritivos a clientas de todo el país. |
| **Sistema de reservas y agendamiento automatizado de citas en línea** | **Tiempo y complejidad técnica:** Configurar un calendario de reservas sincronizado con Google Calendar, con cálculo de tiempos variables por peinado (de 2 a 6 horas) y cobro de abonos previos requería pruebas exhaustivas que excedían los plazos de entrega. | Automatiza la gestión de citas las 24 horas del día, minimiza inasistencias mediante recordatorios automáticos por correo o WhatsApp y ahorra tiempo operativo de coordinación manual. |
| **Galería fotográfica interactiva con filtros avanzados por técnica** | **Recursos y costo:** La versión comunitaria de FooGallery cubre eficientemente la visualización en cuadrícula y lightbox, pero los filtros dinámicos por categorías (ej. *Box Braids*, *trenzas pegadas*, *trenzas para hombres/niñas*) y búsqueda facetada requieren una licencia de pago (FooGallery PRO). | Facilita que las clientas filtren rápidamente el catálogo por largo, grosor o estilo, reduciendo dudas previas a la reserva de hora. |
| **Boletín informativo y fidelización por correo electrónico (Newsletter)** | **Tiempo:** Se dio prioridad a la redacción de las páginas base y los 3 artículos educativos del blog, aplazando el diseño de plantillas de captura de suscriptores y secuencias automáticas de bienvenida. | Posibilita el contacto recurrente con clientas fidelizadas para comunicar promociones especiales, disponibilidad de cupos en fechas festivas y consejos capilares exclusivos. |

---

## 2. Recursos que necesito (2 pts)

Para implementar las funcionalidades de la Etapa 2 se requerirán los siguientes recursos tecnológicos, financieros y formativos:

| Funcionalidad | Plugin o herramienta | Gratis o de pago | Costo aproximado | Qué tendría que aprender |
|---|---|---|---|---|
| **E-commerce y pagos online** | WooCommerce + Transbank Webpay Plus Oficial | Plugin gratuito; comisión por venta | $0 costo inicial + 2,5% a 3,5% por transacción con tarjeta | Configuración de impuestos, zonas y costos de despacho (Starken/Chilexpress) y gestión de inventario en WordPress. |
| **Agendamiento de citas online** | Amelia Booking o Simply Schedule Appointments | Freemium (versión Pro recomendada para pagos de abono) | Versión básica gratuita / ~$49 a $79 USD anuales la licencia Pro | Configuración de franjas horarias, pausas entre servicios largos y sincronización de agenda con calendarios externos. |
| **Filtros avanzados de catálogo** | FooGallery PRO Commerce | De pago | ~$39 USD anuales | Manejo avanzado de taxonomías personalizadas, etiquetas de búsqueda y maquetación de álbumes dinámicos. |
| **Email marketing automatizado** | Brevo (Sendinblue) o MailPoet | Freemium (plan gratuito hasta 300-500 correos/día) | $0 costo inicial | Diseño de formularios de suscripción en bloques y automatización de correos transaccionales. |

### Servidor y hosting para la Etapa 2

Para sostener las nuevas funcionalidades comerciales, **es indispensable migrar el sitio web desde el hosting gratuito de InfinityFree hacia un proveedor de hosting profesional compartido o VPS administrado** (como Hostinger Business o SiteGround):
- **Almacenamiento y rendimiento:** Mínimo 15 a 20 GB de almacenamiento en unidades SSD NVMe para alojar el catálogo ampliado de productos y galerías en alta resolución.
- **Entorno de ejecución PHP:** PHP 8.2 o superior con directivas de servidor optimizadas (`memory_limit` de al menos 256 MB o 512 MB, `max_execution_time` de 120s) para procesar transacciones de WooCommerce y generación de facturas sin caídas ni errores de tiempo de espera (*timeout*).
- **Base de datos dedicada:** Instancia de MariaDB o MySQL sin restricciones de peticiones simultáneas, eliminando los errores 500 y 429 habituales de los servidores gratuitos compartidos.
- **Seguridad y confianza:** Certificado SSL comercial o Let's Encrypt automatizado de por vida bajo protocolo HTTP/2 o HTTP/3, requisito obligatorio para operar pasarelas de pago electrónico seguras.
- **Dominio corporativo:** Registro de un dominio propio `.cl` (a través de NIC Chile, ~$12.000 CLP anuales) para formalizar la identidad institucional de **Trenzadora**.

---

## 3. Priorización y cronograma (2 pts)

Cronograma estratégico ordenado en fases de implementación a lo largo de los dos meses posteriores a la entrega final:

| Prioridad | Qué hago | Cuándo (mes o semana) | Resultado esperado |
|---|---|---|---|
| **1** | **Migración técnica a hosting profesional y dominio propio `.cl`** | Diciembre 2026 (Semanas 1 y 2) | Sitio con tiempos de carga inferiores a 2 segundos, certificado SSL activo sin advertencias y correo corporativo `@trenzadora.cl`. |
| **2** | **Implementación del sistema de reservas de citas online (Amelia)** | Diciembre 2026 (Semanas 3 y 4) | Calendario operativo donde las clientas agendan sus sesiones de trenzado con confirmación automática. |
| **3** | **Despliegue y configuración de WooCommerce con pasarela Webpay** | Enero 2027 (Semanas 1 y 2) | Catálogo de productos capilares y extensiones activo con cobro seguro mediante tarjetas de débito/crédito. |
| **4** | **Activación de galería con filtros Pro y suscripción a Newsletter** | Enero 2027 (Semanas 3 y 4) | Galería visual categorizada por técnica y formulario de captura de clientas con cupón de descuento en su primer servicio. |

---

## 4. Riesgos y mitigación (1 pt)

| Riesgo | Qué haría | Cuándo se activa |
|---|---|---|
| **Los costos de licencias de software o comisiones superan el flujo de caja inicial.** | Iniciar la fase con versiones gratuitas de los complementos (Amelia Free y pagos de reserva mediante transferencia bancaria manual acreditada por WhatsApp) antes de asumir compromisos de suscripción en dólares. | Si en el primer mes de evaluación los ingresos de ventas online no cubren el costo de licencias. |
| **Incompatibilidades visuales entre WooCommerce y el tema Twenty Twenty-Four.** | Diseñar plantillas de producto y catálogo limpias usando el editor de bloques nativo, o alternativamente emplear un tema clásico ligero y optimizado para comercio electrónico como Astra. | Si durante la instalación de prueba de WooCommerce se detectan desbordes visuales en dispositivos móviles. |
| **Resistencia de las clientas a utilizar el sistema de reservas automatizado.** | Mantener de forma permanente y destacada el botón flotante de WhatsApp en la cabecera y pie de página como vía de soporte y agendamiento personalizado. | Si transcurridas dos semanas de lanzamiento más del 35% de las clientas sigue solicitando cita por mensaje directo. |
