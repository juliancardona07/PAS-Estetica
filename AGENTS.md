# AGENTS.md

## 1. Objetivo

Este proyecto corresponde al desarrollo de sitios web profesionales para
emprendimientos y pequeños negocios.

El sitio debe priorizar:

-   Diseño moderno y atractivo.

-   Excelente experiencia de usuario.

-   Responsive y Mobile First.

-   Alto rendimiento y tiempos de carga reducidos.

-   Accesibilidad.

-   SEO técnico básico.

-   Código limpio, mantenible y reutilizable.

-   Arquitectura sencilla y escalable.

-   Bajo acoplamiento y mínima dependencia de librerías innecesarias.

-   Facilidad de mantenimiento y actualización.

-   Compatibilidad con servicios de hosting modernos y despliegue desde GitHub.

El resultado debe sentirse como un sitio web profesional y personalizado, no
como una plantilla genérica generada automáticamente por IA.

# 2. Stack tecnológico

Para sitios principalmente informativos o corporativos se utilizará:

-   **Astro** como framework principal.

-   **HTML5** para estructura semántica.

-   **CSS / Tailwind CSS** para estilos.

-   **JavaScript o TypeScript** únicamente cuando sea necesario.

-   **Git** para control de versiones.

-   **GitHub** como repositorio.

-   Hosting compatible con despliegue automático desde GitHub.

### Principios

Utilizar la solución tecnológica más practica y eficiente que permita cumplir
los requerimientos.

No introducir frameworks, librerías o dependencias adicionales sin una
justificación técnica.

No utilizar React, Next.js u otros frameworks para funcionalidades que puedan
resolverse de manera sencilla con Astro, HTML, CSS y JavaScript.

Si los requerimientos superan las capacidades o conveniencia de esta
arquitectura, explicar la necesidad antes de cambiar el stack.

# 3. Arquitectura

La aplicación debe utilizar una arquitectura simple y componentizada.

Priorizar:

-   Componentes reutilizables.

-   Separación de responsabilidades.

-   Bajo acoplamiento.

-   Código fácil de entender.

-   Evitar duplicación.

-   Evitar componentes excesivamente grandes.

-   Mantener una estructura de carpetas lógica.

Ejemplo de estructura:

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ text
src/
├── components/
│   ├── Header.astro
│   ├── Footer.astro
│   ├── Hero.astro
│   ├── Button.astro
│   ├── Card.astro
│   ├── Gallery.astro
│   └── ...
│
├── layouts/
│   └── Layout.astro
│
├── pages/
│   ├── index.astro
│   ├── nosotros.astro
│   ├── servicios.astro
│   ├── galeria.astro
│   └── contacto.astro
│
├── data/
└── styles/
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

La estructura podrá modificarse cuando las necesidades del proyecto lo
justifiquen.

# 4. Componentización

Los elementos que se repitan en diferentes páginas deben convertirse en
componentes reutilizables.

Ejemplos:

-   Header.

-   Navbar.

-   Footer.

-   Botones.

-   Cards.

-   Secciones.

-   Formularios.

-   Testimonios.

-   Galerías.

-   CTA.

-   Elementos de navegación.

No duplicar código cuando pueda resolverse mediante un componente reutilizable.

Sin embargo, evitar crear componentes innecesariamente pequeños que dificulten
la comprensión del proyecto.

La componentización debe buscar un equilibrio entre reutilización, simplicidad y
mantenibilidad.

# 5. Diseño UI/UX

El diseño debe ser:

-   Moderno.

-   Profesional.

-   Visualmente atractivo.

-   Consistente.

-   Claro.

-   Intuitivo.

-   Orientado al objetivo del negocio.

-   Adaptable a dispositivos móviles.

El diseño debe priorizar la experiencia del usuario y no solamente la apariencia
visual.

## Jerarquía visual

Utilizar correctamente:

-   Títulos.

-   Subtítulos.

-   Texto descriptivo.

-   Espaciado.

-   Contraste.

-   Imágenes.

-   Botones.

-   CTA.

El usuario debe comprender rápidamente:

1.  Qué ofrece el negocio.

2.  Qué beneficio obtiene.

3.  Qué debe hacer a continuación.

## Consistencia

Mantener consistencia en:

-   Tipografías.

-   Colores.

-   Tamaños.

-   Espaciados.

-   Bordes.

-   Sombras.

-   Botones.

-   Iconografía.

-   Animaciones.

No utilizar estilos diferentes sin una razón de diseño.

# 6. Responsive Design

El desarrollo debe seguir un enfoque **Mobile First**.

La página debe funcionar correctamente en:

-   Teléfonos.

-   Tablets.

-   Portátiles.

-   Monitores de escritorio.

Verificar especialmente:

-   Navegación.

-   Tamaños de texto.

-   Imágenes.

-   Botones.

-   Formularios.

-   Cards.

-   Galerías.

-   Espaciado.

-   Elementos que puedan provocar scroll horizontal.

No utilizar dimensiones rígidas que puedan romper el diseño en diferentes
resoluciones.

# 7. Accesibilidad

Aplicar buenas prácticas de accesibilidad desde el desarrollo.

Priorizar:

-   HTML semántico.

-   Jerarquía correcta de headings.

-   `alt` descriptivo en imágenes relevantes.

-   Labels asociados correctamente a formularios.

-   Navegación mediante teclado.

-   Estados `focus` visibles.

-   Contraste adecuado: En fondos oscuros o claros, garantizar siempre una
    relación de contraste mínima de 4.5:1 para texto normal conforme al estándar
    WCAG 2.1 AA (evitar colores atenuados como `slate-500` sobre fondos
    carbón/navy; priorizar `slate-400` / `#94a3b8` o superior).

-   Botones y enlaces claramente identificables con áreas táctiles mínimas
    adecuadas (mínimo 44x44 px).

-   No depender exclusivamente del color para transmitir información.

-   Uso correcto de elementos HTML nativos antes de crear soluciones
    personalizadas.

Evitar utilizar elementos `div` como sustitutos innecesarios de botones, enlaces
u otros elementos semánticos.

# 8. Rendimiento

El rendimiento es un requisito fundamental.

Priorizar:

-   Generación estática cuando sea posible.

-   Mínimo JavaScript en el cliente.

-   Optimización de fuentes: Prohibido usar `@import` de Google Fonts dentro de
    archivos CSS (provoca render-blocking). Utilizar siempre `<link
    rel="preconnect">` y `<link rel="stylesheet">` con `display=swap` en el
    `<head>`, o paquetes de fuentes autoalojadas (`@fontsource`).

-   Evitar librerías innecesarias.

-   Evitar scripts de terceros innecesarios.

-   Reducir recursos bloqueantes.

-   Mantener páginas ligeras (peso total de la página inferior a 1 MB en
    producción).

No agregar animaciones, librerías o funcionalidades que tengan un costo
significativo de rendimiento sin justificar su necesidad.

El objetivo es obtener puntuaciones superiores a 95-100 en herramientas como
Lighthouse y mantener métricas óptimas de Core Web Vitals (LCP \< 2.5s, CLS = 0,
TBT \< 200ms).

# 9. Imágenes y multimedia

Las imágenes deben estar optimizadas antes de incorporarlas al proyecto.

Considerar:

-   Resolución adecuada al contenedor de destino (no servir imágenes 4K para
    tarjetas de 400px).

-   Compresión de alta eficiencia (calidad 80-85%).

-   Formato apropiado: WebP o AVIF como estándar principal; SVG para logotipos e
    iconos vectoriales.

-   Peso estricto: Las imágenes individuales de tarjetas o banners no deben
    superar los 100-150 KB.

-   `width` y `height` explícitos en la etiqueta `<img>` para reservar el
    espacio.

-   `alt` descriptivo.

-   `loading="lazy"` y `decoding="async"` para imágenes fuera del viewport
    inicial.

-   No utilizar imágenes excesivamente grandes para espacios pequeños.

-   No incorporar imágenes de demostración como contenido definitivo.

-   Cuando falten imágenes reales del cliente, utilizar placeholders claramente
    identificables y dejar documentado qué contenido debe ser reemplazado.

# 10. SEO

Implementar SEO técnico básico.

Cada página debe considerar:

-   `title`.

-   `meta description`.

-   URL amigable.

-   Heading principal `H1`.

-   Jerarquía adecuada de headings.

-   Texto alternativo.

-   Open Graph cuando corresponda.

-   Sitemap.

-   `robots.txt`.

-   Canonical cuando sea necesario.

El contenido debe estar estructurado pensando tanto en usuarios como en motores
de búsqueda.

No realizar prácticas de keyword stuffing.

# 11. JavaScript

JavaScript debe utilizarse únicamente cuando aporte una funcionalidad real.

Priorizar HTML y CSS cuando sean suficientes.

Ejemplos de funcionalidades apropiadas:

-   Menú móvil.

-   Galerías interactivas.

-   Modales.

-   Validaciones.

-   Interacciones específicas.

-   Animaciones que requieran JavaScript.

Evitar convertir funcionalidades sencillas en soluciones JavaScript
innecesariamente complejas.

# 12. Animaciones

Las animaciones deben utilizarse para mejorar la experiencia, no para decorar
excesivamente.

Priorizar:

-   Transiciones sutiles.

-   Hover.

-   Aparición progresiva de elementos cuando aporte valor.

-   Microinteracciones.

Evitar:

-   Animaciones excesivas.

-   Efectos que dificulten la navegación.

-   Animaciones que afecten el rendimiento.

-   Elementos que se muevan constantemente sin necesidad.

Respetar `prefers-reduced-motion` cuando corresponda.

# 13. Formularios y contacto

Los formularios deben:

-   Tener labels claros.

-   Validar los datos.

-   Mostrar mensajes de error comprensibles.

-   Mostrar confirmación después del envío.

-   Ser accesibles.

-   Funcionar correctamente en dispositivos móviles.

Si el proyecto no tiene backend, utilizar un servicio externo apropiado para el
procesamiento del formulario.

No almacenar credenciales, claves API o información sensible directamente en el
código frontend.

# 14. Seguridad

Aunque estos proyectos sean principalmente frontend:

-   No incluir secretos en el código.

-   No incluir contraseñas.

-   No exponer claves privadas.

-   Validar datos enviados a servicios externos.

-   Mantener dependencias actualizadas.

-   Evitar dependencias innecesarias.

-   No utilizar código de terceros sin revisar su procedencia.

Recordar que cualquier código enviado al navegador puede ser inspeccionado por
el usuario.

# 15. Contenido

El contenido del negocio se encuentra definido en `BRIEF.md`.

Lo que no encuentres como un preliminar inventarlo acorde al contenido del
brief, que información se podría solicitar y que puede estar o no en el
brief.md:

-   Precios.

-   Servicios.

-   Testimonios.

-   Direcciones.

-   Teléfonos.

-   Correos.

-   Horarios.

-   Redes sociales.

-   Información empresarial.

# 16. Diseño orientado a conversión

Cada página debe tener claramente definido su objetivo.

Cuando corresponda, utilizar CTA como:

-   Contactar.

-   Escribir por WhatsApp.

-   Solicitar información.

-   Reservar.

-   Comprar.

-   Ver servicios.

-   Ver productos.

Los CTA principales deben ser fácilmente identificables y estar ubicados
estratégicamente.

No saturar la página con múltiples llamadas a la acción que compitan entre sí.

# 17. Código limpio

El código debe ser:

-   Legible.

-   Consistente.

-   Simple.

-   Mantenible.

-   Reutilizable.

Utilizar nombres descriptivos.

Evitar:

-   Código duplicado.

-   Variables sin significado.

-   Funciones innecesariamente complejas.

-   Archivos excesivamente grandes.

-   Comentarios que simplemente describan código obvio.

Los comentarios deben utilizarse principalmente para explicar decisiones o
comportamientos que no sean evidentes.

# 18. Dependencias

Antes de agregar una dependencia:

1.  Verificar si realmente es necesaria.

2.  Revisar si Astro, CSS o JavaScript nativo pueden resolver el problema.

3.  Evaluar mantenimiento y estabilidad.

4.  Evaluar impacto en rendimiento.

5.  Evitar dependencias para funcionalidades triviales.

No instalar paquetes únicamente porque faciliten ligeramente una tarea sencilla.

# 19. Vibe Coding / Uso de IA

La IA debe actuar como asistente de desarrollo, pero las decisiones importantes
deben mantenerse bajo control humano.

Antes de realizar cambios importantes:

-   Analizar el código existente.

-   Comprender la arquitectura.

-   Identificar posibles impactos.

-   Explicar cambios relevantes cuando sea necesario.

No modificar archivos indiscriminadamente.

No eliminar funcionalidades existentes para solucionar un problema sin
autorización.

No cambiar el stack tecnológico sin justificarlo.

No introducir funcionalidades que no estén contempladas en `BRIEF.md`.

Si existe una ambigüedad funcional o de diseño, preguntar antes de asumir.

Cuando una solución tenga varias alternativas razonables, presentar brevemente
las opciones y recomendar una.

# 20. Desarrollo incremental

No desarrollar todo el proyecto en una única generación masiva.

Trabajar por etapas:

1.  Analizar requerimientos.

2.  Proponer arquitectura.

3.  Proponer estructura de páginas.

4.  Proponer componentes.

5.  Proponer diseño.

6.  Implementar estructura base.

7.  Implementar componentes.

8.  Implementar páginas.

9.  Implementar interacciones.

10. Optimizar.

11. Revisar accesibilidad.

12. Revisar SEO.

13. Realizar pruebas.

Después de cada etapa importante verificar que el proyecto continúe funcionando.

# 21. Git

Utilizar Git para controlar los cambios.

Los commits deben ser claros y descriptivos.

Ejemplos:

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ text
feat: add services section
feat: add contact form
fix: correct mobile navigation
style: improve hero spacing
perf: optimize gallery images
refactor: extract reusable card component
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Para cambios importantes utilizar ramas.

Ejemplo:

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ text
main
├── feature/gallery
├── feature/contact-form
└── fix/mobile-navbar
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

No realizar cambios experimentales directamente sobre `main`.

# 22. Testing y control de calidad

Antes de considerar terminado el proyecto verificar:

### Funcionalidad

-   Los enlaces funcionan.

-   Los botones funcionan.

-   WhatsApp funciona.

-   Formularios funcionan.

-   Menú funciona.

-   Navegación funciona.

-   No existen enlaces rotos.

### Responsive

Verificar:

-   Mobile.

-   Tablet.

-   Desktop.

### Visual

Revisar:

-   Alineación.

-   Espaciado.

-   Tipografía.

-   Imágenes.

-   Colores.

-   Consistencia.

-   Estados hover/focus.

### Accesibilidad

Verificar:

-   Navegación con teclado.

-   Headings.

-   Labels.

-   Alt.

-   Contraste.

-   Focus.

### Performance

Verificar:

-   Peso de imágenes (todas en WebP/AVIF y \< 150 KB).

-   Dimensiones explícitas (`width` y `height`) en todas las imágenes.

-   Eliminación de recursos bloqueantes (fuentes con `<link rel="preconnect">` y
    `display=swap`).

-   JavaScript innecesario o dependencias pesadas.

-   Auditorías de Lighthouse: Ejecutadas siempre sobre la compilación de
    producción (`npm run build && npm run preview` o la URL en vivo de Vercel)
    para obtener métricas reales sin interferencia de herramientas de
    desarrollo.

-   Métricas de Core Web Vitals (LCP, CLS, TBT, INP).

### SEO

Verificar:

-   Title.

-   Description.

-   H1.

-   Headings.

-   Sitemap.

-   Robots.

-   Open Graph.

# 23. Regla principal

**No sobreingenierizar.**

El objetivo es construir sitios web:

>   Profesionales + modernos + rápidos + accesibles + mantenibles + escalables.

La solución más sencilla que cumpla correctamente los requerimientos debe ser
preferida frente a una solución técnicamente más compleja.

La tecnología debe adaptarse al negocio y no el negocio a la tecnología.

Cuando una necesidad del proyecto requiera una arquitectura diferente, explicar
primero el motivo y sus implicaciones antes de implementarla.
