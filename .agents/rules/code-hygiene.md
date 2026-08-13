# Reglas de Higiene y Limpieza de Código

Estas reglas aseguran que el código entregado sea mantenible, limpio y listo para producción.

---

## 1. CSS Limpio y Mantenible
- Centralizar tokens en `:root` antes de escribir estilos de componentes.
- No usar `!important` a menos que sea para sobreescribir utilidades de accesibilidad (`prefers-reduced-motion`).
- Eliminar selectores huérfanos o reglas de estilo no utilizadas antes de dar por terminado un cambio.

## 2. HTML Semántico
- Usar etiquetas semánticas (`<header>`, `<main>`, `<nav>`, `<section>`, `<article>`, `<footer>`).
- No usar `<div>` para elementos interactivos como botones o enlaces (`<button>` y `<a>` son obligatorios).
- Asegurar que todas las imágenes tengan un atributo `alt` descriptivo.

## 3. JavaScript y Rendimiento
- Eliminar llamadas a `console.log` o código de depuración antes de finalizar.
- Optimizar animaciones por hardware (`transform` y `opacity`).
