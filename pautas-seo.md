# Pautas SEO
**Realdreams-Services · Guía práctica para sitios y landing pages**

Esta guía ayuda a preparar páginas rastreables, comprensibles y útiles para personas que buscan servicios en una zona concreta. Aplicar estas pautas mejora la base técnica; no garantiza indexación, tráfico ni posiciones específicas.

## 1. Antes de publicar

- [ ] Definir qué servicio ofrece la página, a quién está dirigido y qué acción se espera del visitante.
- [ ] Elegir una URL pública y estable. Un dominio propio es recomendable para marca y control, pero no es requisito para indexar: Vercel y GitHub Pages también pueden alojar sitios indexables.
- [ ] Confirmar que la página de producción responde por HTTPS y no requiere iniciar sesión.
- [ ] No publicar como URL canónica una dirección inventada o provisional. La canonical, `og:url` y las URLs del sitemap deben usar la URL pública real y preferida.
- [ ] Evitar indexar demos privadas, sitios de prueba o duplicados. Para pruebas, usar autenticación o `noindex`; no confiar únicamente en `robots.txt` para ocultar una página.

## 2. Contenido y relevancia

- [ ] Escribir para las preguntas e intenciones reales de clientes, no para repetir palabras clave.
- [ ] Tener un título principal `<h1>` único, claro y descriptivo. Incluir servicio y localidad solo cuando correspondan naturalmente.
- [ ] Organizar la página con encabezados jerárquicos (`<h2>`, `<h3>`) y secciones semánticas.
- [ ] Explicar con texto concreto los servicios, público, proceso, zona de atención y formas de contacto.
- [ ] Crear páginas distintas solo si cada una aporta contenido propio y útil; no generar páginas casi idénticas para muchas localidades.
- [ ] Usar nombres, dirección, teléfono, horarios y área de servicio reales y consistentes en el sitio y los perfiles públicos del negocio.
- [ ] Evitar afirmaciones no demostradas (por ejemplo, “#1 en Google”, puntuaciones Lighthouse o aumentos de ventas garantizados).
- [ ] No depender de `<meta name="keywords">`: los buscadores principales no la usan para posicionar.

## 3. Etiquetas del documento

- [ ] Definir un `<title>` único, descriptivo y conciso para cada página.
- [ ] Escribir una meta description específica que resuma la oferta y ayude a decidir si visitar la página. Google puede generar otro fragmento y no garantiza mostrarla.
- [ ] Definir el idioma correcto en `<html lang="es">` o la variante que corresponda.
- [ ] Permitir el rastreo e indexación de páginas públicas con una directiva `robots` adecuada; revisar que no haya `noindex` accidental.
- [ ] Añadir Open Graph (`og:title`, `og:description`, `og:type`, `og:url`, `og:image`) para compartir en redes. Usar una imagen propia, accesible y con dimensiones apropiadas.
- [ ] Añadir `twitter:card` y metadatos asociados si se necesitan tarjetas de vista previa.
- [ ] Usar canonical solo cuando exista una URL pública preferida y confirmada. La canonical es una señal, no una garantía.

## 4. SEO local y datos estructurados

- [ ] Usar un tipo Schema.org que describa correctamente la actividad real, por ejemplo `LocalBusiness` o un subtipo apropiado.
- [ ] Añadir únicamente datos verificables: nombre, teléfono, dirección, horario, coordenadas, URL e imágenes reales cuando estén disponibles.
- [ ] No marcar como dirección física una dirección donde el negocio no atiende al público. Para un negocio de área de servicio, representar la actividad de forma fiel y seguir las directrices vigentes de Google Business Profile.
- [ ] Usar `areaServed` solo para zonas atendidas de verdad.
- [ ] Añadir FAQ u otros datos estructurados solo si el contenido equivalente está visible para las personas y coincide exactamente con el marcado.
- [ ] Validar el JSON-LD con Schema Markup Validator y los resultados enriquecidos compatibles con Google cuando corresponda. El marcado válido no asegura un resultado enriquecido ni una mejor posición.
- [ ] Mantener consistentes nombre, dirección y teléfono entre web, Google Business Profile y otros directorios confiables.
- [ ] Reclamar y completar Google Business Profile solo si el negocio cumple los requisitos de elegibilidad. No crear fichas para direcciones ficticias.

## 5. Rastreo, indexación y hosting

- [ ] Publicar `robots.txt` en la raíz del host para indicar reglas de rastreo. No bloquear CSS, JavaScript o recursos necesarios para renderizar la página.
- [ ] Publicar `sitemap.xml` cuando haya varias URLs públicas; usar URLs canónicas absolutas y actuales. En sitios de una sola página es útil pero no siempre imprescindible.
- [ ] Enviar el sitemap y revisar la cobertura en Google Search Console y Bing Webmaster Tools.
- [ ] Verificar la URL de producción con las herramientas de inspección después de publicar. El rastreo y la indexación pueden tardar.
- [ ] Asegurarse de que rutas y enlaces internos devuelvan estados HTTP correctos y no terminen en páginas rotas.
- [ ] En Vercel o GitHub Pages, comprobar que el proyecto se publica desde la carpeta correcta y que el host permite servir `robots.txt`, sitemap e imágenes.
- [ ] Al migrar a dominio propio, actualizar redirects, canonical, Open Graph, JSON-LD, sitemap y propiedades de Search Console; conservar redirecciones permanentes desde las URLs antiguas cuando se controlen.

## 6. Rendimiento, móvil y accesibilidad

- [ ] Verificar la experiencia a 360 px, 768 px y escritorio; evitar desplazamiento horizontal y controles demasiado pequeños.
- [ ] Medir Core Web Vitals y rendimiento con Lighthouse/PageSpeed en la URL publicada, no prometer valores antes de medirlos.
- [ ] Usar imágenes comprimidas y dimensionadas; incluir `width` y `height` para reducir saltos de diseño.
- [ ] Usar `loading="lazy"` para imágenes fuera de la primera pantalla; no retrasar la imagen principal si es el elemento LCP.
- [ ] Reducir scripts, fuentes y recursos externos innecesarios. Usar `font-display: swap` en fuentes web.
- [ ] Dar texto alternativo útil a imágenes informativas; usar `alt=""` en imágenes decorativas. No introducir palabras clave sin contexto.
- [ ] Mantener enlaces descriptivos, contraste legible, navegación por teclado y etiquetas accesibles.

## 7. Medición y mejora continua

- [ ] Instalar analítica solo si es necesaria y configurarla conforme a privacidad y consentimiento aplicables.
- [ ] Medir consultas, llamadas o ventas para evaluar conversiones, además de impresiones y clics orgánicos.
- [ ] Revisar periódicamente Search Console: páginas indexadas, consultas, errores y acciones manuales.
- [ ] Actualizar información, precios, horarios y enlaces cuando cambien.
- [ ] No comprar enlaces, generar reseñas falsas ni crear páginas automáticas repetitivas.
- [ ] Evaluar resultados durante el tiempo; ninguna etiqueta, plugin o schema puede garantizar una posición.

## Checklist mínimo de lanzamiento

- [ ] URL pública HTTPS y contenido accesible sin iniciar sesión.
- [ ] Un `<title>`, meta description y `<h1>` claros y específicos.
- [ ] Contenido útil y preciso, con servicios y localidades reales.
- [ ] Sin `noindex` accidental; canonical solo si la URL preferida ya está confirmada.
- [ ] Datos estructurados reales, válidos y coherentes con el contenido visible.
- [ ] Enlaces, WhatsApp, imágenes y navegación móvil comprobados.
- [ ] Search Console configurado y sitemap enviado cuando corresponda.
- [ ] Rendimiento y accesibilidad medidos en la versión publicada.

## Referencias oficiales

- [Google Search Central: SEO Starter Guide](https://developers.google.com/search/docs/fundamentals/seo-starter-guide)
- [Google Search Central: controles de rastreo e indexación](https://developers.google.com/search/docs/crawling-indexing)
- [Google Search Central: datos estructurados](https://developers.google.com/search/docs/appearance/structured-data/intro-structured-data)
- [Google Search Central: directrices de representación de empresas locales](https://developers.google.com/search/docs/appearance/structured-data/local-business)
- [Google Business Profile: directrices para representar empresas](https://support.google.com/business/answer/3038177)
- [Schema.org: LocalBusiness](https://schema.org/LocalBusiness)
