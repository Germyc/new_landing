# Pauta de Programación y Estándares de Desarrollo Web
**Realdreams-Services · Guía Maestra de Ingeniería Web y Conversión**
*Autor:* Germán Cortez  
*Ámbito:* Desarrollo de sitios nuevos, refactorización de webs existentes y armado de demos comerciales.

---

## 1. Principios Rectores y Filosofía de Desarrollo

Todo proyecto desarrollado bajo el sello de **Realdreams-Services** debe cumplir de forma irrenunciable con tres pilares:

1. **Velocidad Extrema (Performance First):** El tiempo de carga en dispositivos móviles sobre redes 4G debe ser inferior a 1 segundo. Puntuación mínima de 90/100 en Google PageSpeed / Lighthouse.
2. **Propiedad Total del Cliente:** Los proyectos se entregan limpios y autónomos. Se rechaza la práctica de retener al cliente mediante plataformas cerradas o códigos ofuscados que exijan abonos mensuales forzados.
3. **Conversión y Negocio Real:** Una página web no es una pieza artística decorativa; es una herramienta de ventas. Cada sección debe guiar la atención del usuario hacia una acción concreta (WhatsApp contextual, llamada o cotizador).

---

## 2. Pauta A: Auditoría y Refactorización de Sitios Existentes

Cuando un cliente llega con un sitio web ya creado (habitualmente desarrollado en WordPress con plantillas saturadas, Elementor, Divi o código desactualizado), se aplica el siguiente protocolo de intervención:

### 2.1. Diagnóstico Inicial y Línea de Base
- [ ] **Auditoría de Velocidad:** Registrar métricas iniciales con Google PageSpeed Insights (FCP, LCP, CLS) tanto en Mobile como en Desktop.
- [ ] **Inventario de Dependencias:** Identificar plugins inactivos, scripts de seguimiento no utilizados y librerías CSS/JS redundantes.
- [ ] **Revisión de Adaptabilidad Móvil:** Inspeccionar en pantallas pequeñas (360px a 414px) para detectar desbordes horizontales, tipografías ilegibles o botones inaccesibles.

### 2.2. Depuración y Optimización Técnica
- [ ] **Optimización de Medios:** Convertir todas las imágenes (PNG/JPG) a formato **WebP** o **AVIF** con compresión controlada (80-85%). Definir dimensiones explícitas (`width` y `height`) en cada etiqueta `<img>` para erradicar cambios acumulativos de diseño (CLS).
- [ ] **Eliminación de Elementos Obsoletos:**
  - Suprimir carruseles/sliders automáticos pesados (la estadística demuestra que menos del 1% de los usuarios interactúa con el segundo slide). Reemplazarlos por un Hero estático con mensaje claro.
  - Eliminar maquetadores de 20MB si el sitio solo muestra contenido institucional; migrar a maquetación limpia en HTML/CSS semántico o bloques nativos ligeros.
- [ ] **Carga Diferida de Recursos:**
  - Aplicar `loading="lazy"` a imágenes bajo el pliegue inicial (*below the fold*).
  - Configurar `defer` o `async` en scripts de terceros (analítica, mapas, widgets).
  - Cargar tipografías de Google Fonts con `display=swap`.

### 2.3. Rediseño y Mejora de Conversión
- [ ] **Reestructuración Visual (Estilo Bento Grid):** Transformar listas interminables de texto en tarjetas modulares con bordes redondeados y micro-interacciones sutiles.
- [ ] **Reemplazo de Formularios Tradicionales:** Los formularios estáticos por correo electrónico tienen baja tasa de respuesta en pymes. Reemplazarlos por **botones de WhatsApp inteligentes** que precarguen la consulta del cliente según la página o servicio que esté visitando.
- [ ] **Inyección de SEO Local:** Insertar marcado estructurado JSON-LD con el esquema `LocalBusiness` (nombre, dirección local, teléfono y coordenadas) para subsanar el mal posicionamiento en Google Maps.

---

## 3. Pauta B: Estándar para Desarrollo de Sitios Nuevos desde Cero

Para sitios creados desde cero, se sigue una arquitectura modular estandarizada:

### 3.1. Stack Tecnológico Recomendado
* **Opción Ligera / Standalone:** HTML5 semántico + CSS moderno (variables CSS, Flexbox/Grid, efectos de fondo con blur) + Vanilla JavaScript (sin frameworks pesados para landing pages e institucionales).
* **Opción JAMstack / Componentes:** Astro o Next.js con TailwindCSS cuando el proyecto requiera escalabilidad, blog dinámico o integración con CMS headless.
* **Opción E-Commerce:** Pasarela transparente conectada a Mercado Pago vía Webhooks o integración ágil autoadministrable sin comisiones ocultas por venta.

### 3.2. Estructura Arquitectónica Obligatoria
1. **`<header>` (Navegación Limpia):**
   * Logotipo y nombre comercial con isotipo moderno.
   * Menú con enlaces ancla suaves (`scroll-smooth`).
   * Botón destacado de acción rápida (CTA a WhatsApp).
   * Efecto *glassmorphism* con `backdrop-filter: blur(16px)` para fijación superior.
2. **Hero Section (Primer Impacto):**
   * *Badge pill* con microanimación de pulso indicando especialidad y zona geográfica.
   * Título principal (H1) con tipografía contrastada y gradiente de acento.
   * Propuesta de valor en un párrafo conciso de máximo 3 líneas.
   * Barra de métricas/diferenciales rápidos (velocidad, propiedad, soporte directo).
3. **Bento Grid de Servicios y Diferenciales:**
   * Distribución en grilla de 12 columnas (tarjetas `col-span-8` y `col-span-4`).
   * Iconografía moderna o emojis de alta resolución.
   * Explicación de beneficios concretos, no descripciones técnicas aburridas.
4. **Cotizador Interactivo en 3 Pasos:**
   * **Paso 1:** Selector de plan base (Tarjetas interactivas con estado activo).
   * **Paso 2:** Checkboxes con adicionales opcionales (SEO local, pasarela de cobro, sistema de turnos).
   * **Paso 3:** Caja de cálculo en vivo en moneda local (ARS) y botón dinámico que compila el texto formateado y abre el chat de WhatsApp con el presupuesto desglosado.
5. **Tabla Comparativa de Mercado:**
   * Comparación cara a cara entre la solución ofrecida y las agencias tradicionales (tiempos de carga, costos de mantenimiento, propiedad del código).
6. **Bloque de Contacto y Ubicación Local:**
   * Dirección física clara (localidad, partido, código postal).
   * Enlace directo a Google Maps (`https://maps.google.com/?q=...`).
   * Nombre del responsable del proyecto y canal directo de atención.
7. **`<footer>` Institucional:**
   * Cláusula legal de Copyright: `Copyright © [Año] [Titular] - [Marca]. Todos los derechos reservados.`
   * Marcado Schema.org `LocalBusiness` debidamente validado.

---

## 4. Pauta C: Elaboración de Demos Comerciales de Alto Cierre

Las demos son el arma principal para captar clientes en Burzaco y el corredor de Zona Sur. No deben ser conceptos abstractos, sino prototipos tangibles que resuelvan la necesidad del cliente antes de firmar el contrato.

### 4.1. Estrategia de la Demo de Impacto
- **Personalización Rápida:** Tomar los datos públicos del prospecto (su logo de Instagram, fotos de su local en Google Maps, su número de WhatsApp) e insertarlos en la plantilla demo.
- **Demostración de Contraste:** Al presentar la demo, mostrar en pantalla dividida:
  * A la izquierda: El sitio actual del cliente (o de su competidor directo) tardando 4 segundos en cargar.
  * A la derecha: La demo de Realdreams-Services cargando de forma instantánea en menos de 0.8 segundos con diseño oscuro premium o minimalista.
- **Cotizador Adaptado al Rubro del Cliente:**
  * Para talleres/oficios: Cotizador de reparaciones o presupuestos de visita técnica.
  * Para gastronomía/comercios: Selector de productos con pedido directo por WhatsApp.
  * Para consultorios/profesionales: Sistema de selección de turnos o asesorías.

---

## 5. Checklist Técnico de Control de Calidad (Pre-Lanzamiento)

Antes de entregar cualquier sitio al cliente o publicar una demo:

- [ ] **Validación HTML5:** Sin etiquetas sin cerrar ni errores de jerarquía de encabezados (solo un `<h1>` por página).
- [ ] **Responsividad Verificada:** Probar en 360px (móvil estándar), 768px (tablet) y 1440px (escritorio).
- [ ] **Prueba de Enlaces de WhatsApp:** Verificar que todos los enlaces contengan el formato internacional correcto (`https://wa.me/54911...`) y que el texto use codificación URL segura (`encodeURIComponent`).
- [ ] **Metadatos y Open Graph:**
  * `<title>` descriptivo que incluya la palabra clave y la localidad (ej: *[Servicio] en Burzaco | [Marca]*).
  * `<meta name="description">` persuasivo de 140 a 160 caracteres.
  * Etiquetas `og:title`, `og:description` e `og:image` para que al compartir el link por WhatsApp aparezca una vista previa atractiva con imagen y descripción.
- [ ] **Certificado SSL (HTTPS):** Confirmar candado de seguridad activo sin advertencias de contenido mixto.
- [ ] **Prueba en Navegadores:** Chrome, Safari (iOS), Edge y Firefox.
- [ ] **Entrega de Archivos:** Proporcionar al cliente el archivo comprimido con el código fuente y las credenciales correspondientes si contrata servidor propio.
