# Accessibility Refactoring Project: WCAG 2.2 Compliance
# Proyecto de Refactorización de Accesibilidad: Cumplimiento WCAG 2.2

## 🇬🇧 English Description

### Project Overview
This repository documents the process of refactoring a non-accessible HTML page into a fully accessible document complying with **WCAG 2.2 Level AA/AAA** standards. The refactoring was performed using an AI Programming Assistant guided by a specifically engineered prompt.

### Methodology
1.  **Original State:** An `index_original.html` file was created with deliberate accessibility errors (lack of semantics, poor contrast, inaccessible forms, "div soup").
2.  **Prompt Engineering:** A comprehensive prompt was designed focusing on Semantic HTML5, ARIA roles, Contrast ratios, and Keyboard navigation.
3.  **Validation Loop:** The code was tested using WAVE, Axe, and Lighthouse. If errors persisted, the prompt was iterated.

### Tools Used
* **AI Assistant:** [GitHub Copilot / Gemini / ChatGPT]
* **Validation:** WAVE Web Accessibility Tool, Google Lighthouse, Axe DevTools.

### Key Improvements
* **Semantics:** Replaced `<div>` layouts with `<header>`, `<main>`, `<nav>`.
* **Forms:** Added explicit `<label>` associations and removed "div buttons" in favor of native `<button>`.
* **Visuals:** Adjusted color contrast ratios to meet the 4.5:1 standard.

---

## 🇪🇸 Descripción en Español

### Resumen del Proyecto
Este repositorio documenta el proceso de refactorización de una página web no accesible para convertirla en un documento que cumple con los estándares **WCAG 2.2 Nivel AA/AAA**. La corrección se realizó utilizando un Asistente de Programación basado en IA guiado por un "prompt" (instrucción) diseñado específicamente para este fin.

### Metodología
1.  **Estado Original:** Se creó el archivo `index_original.html` con errores intencionados de accesibilidad (falta de semántica, bajo contraste, formularios inaccesibles, abuso de `divs`).
2.  **Ingeniería del Prompt:** Se redactó un prompt detallado enfocado en HTML5 Semántico, roles ARIA, Ratios de contraste y Navegación por teclado, siguiendo las recomendaciones de expertos como Olga Carreras.
3.  **Ciclo de Validación:** El código resultante se testeó con WAVE, Axe y Lighthouse.

### Herramientas Utilizadas
* **Asistente IA:** [GitHub Copilot / Gemini / ChatGPT]
* **Validación:** WAVE Web Accessibility Tool, Google Lighthouse, Axe DevTools.

### Mejoras Clave Implementadas
* **Semántica:** Se reemplazó la estructura de `<div>` por regiones semánticas como `<header>`, `<main>`, `<nav>`.
* **Formularios:** Se añadieron etiquetas `<label>` explícitas y se sustituyeron los botones hechos con `div` por la etiqueta nativa `<button>`.
* **Jerarquía:** Se estableció un orden lógico de encabezados (`<h1>` seguido de `<h2>`).
* **Visual:** Se ajustaron los colores hexadecimales para cumplir con el ratio de contraste 4.5:1.

## 📊 Validation Screenshots / Capturas de Validación

*(Insert your screenshots here / Inserta tus capturas aquí)*
* **Before / Antes:** (Screenshot of WAVE showing errors)
* **After / Después:** (Screenshot of WAVE showing 0 errors)

## PROMPT USADO PARA EL AGENTE COPILOT EN VSCODE

Rol: Actúa como un Desarrollador Frontend Senior especializado en Accesibilidad Web (WCAG 2.2) y Auditor certificado por la IAAP.

Tarea: Refactoriza completamente el código HTML proporcionado para cumplir estrictamente con los criterios de conformidad de nivel AA (y AAA donde sea posible sin romper el diseño visual) de las pautas WCAG 2.2.

Instrucciones Críticas de Accesibilidad:

Semántica HTML5 (Landmarks): Estructura el documento usando <header>, <main>, <nav>, <footer>, <section> y <article> para definir regiones de la página programáticamente.

Jerarquía de Encabezados: Asegura una estructura lógica estricta (<h1> único, seguido de <h2>, etc.). No saltes niveles.

Formularios Accesibles:

Asocia explícitamente todos los inputs con etiquetas <label> usando for e id.

Añade autocomplete donde aplique.

Si es necesario, añade instrucciones de ayuda con aria-describedby.

Imágenes y Medios: Añade atributos alt descriptivos. Si la imagen es decorativa, usa alt="" o role="presentation".

Interactividad (Teclado y Foco):

Reemplaza elementos no interactivos (como <div class="boton">) por elementos nativos <button> o <a>.

Asegura que el tabindex sea lógico (evita valores positivos mayores a 0).

Garantiza que el foco sea visible (puedes agregar estilos CSS en línea o en bloque para cumplir el criterio de contraste de foco).

Enlaces: Reescribe los textos de los enlaces genéricos (ej: "pincha aquí") para que tengan sentido fuera de contexto.

Tablas: Usa <thead>, <tbody>, <th> con atributos scope="col" o scope="row" para definir las relaciones de las celdas.

ARIA (Accessible Rich Internet Applications): Sigue la primera regla de ARIA: "No uses ARIA si el HTML nativo lo soluciona". Úsalo solo para mejorar estados (ej: aria-expanded, aria-current) o roles faltantes, no para parchar mal HTML.

Contraste (Color): Modifica los estilos CSS (hex codes) para asegurar un ratio de contraste mínimo de 4.5:1 para texto normal y 3:1 para texto grande o componentes de interfaz.

Idioma: Asegura que la etiqueta <html> tenga el atributo lang correcto.

Salida: Entrega únicamente el código HTML/CSS completo y corregido, listo para copiar y pegar. Añade comentarios breves explicando por qué hiciste cambios clave de accesibilidad.
