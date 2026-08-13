---
name: frontend-visual-polish
description: >-
  Especialista en maquetación frontend, CSS moderno (CSS Grid, Flexbox, Custom Properties, Glassmorphism, 60fps animations),
  diseño web responsive (mobile-first), accesibilidad WCAG y pulido visual pixel-perfect.
  Usar cuando se implemente o refine código HTML, CSS o JS para asegurar acabados estéticos de máxima calidad y alto rendimiento.
---

# Frontend Visual Polish & Modern CSS Engineering

Esta skill define los estándares técnicos de maquetación, arquitectura CSS y buenas prácticas para transformar conceptos de diseño en interfaces web fluidas, rápidas y visualmente impecables (inspirada en el rol *Frontend Dev / Felix* de *vibe-coder-kit*).

---

## 1. Arquitectura de CSS y Buenas Prácticas

1. **Variables y Modularidad:**
   - Centraliza todas las propiedades de estilo reutilizables en variables CSS (`var(--...)`).
   - Evita valores numéricos *hardcodeados* repetidos.
2. **Layouts Modernos:**
   - Utiliza **CSS Grid** para estructuras bidimensionales complejas y galerías de tarjetas (`grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));`).
   - Utiliza **Flexbox** para alineaciones unidimensionales, barras de navegación y controles interactivos (`gap: var(--space-4)`).
3. **Especificidad y Mantenimiento:**
   - Evita el uso de `!important`.
   - Organiza las clases con nombres semánticos y descriptivos (BEM o componentes limpios como `.product-card`, `.product-card__image`, `.product-card__badge`).

---

## 2. Técnicas de Estilizado Moderno & Efectos Visuales

### Glassmorphism Sutil (Efecto Vidrio Esmerilado)
```css
.glass-surface {
  background: rgba(255, 255, 255, 0.75);
  backdrop-filter: blur(12px);
  -webkit-backdrop-filter: blur(12px);
  border: 1px solid rgba(255, 255, 255, 0.4);
  box-shadow: var(--shadow-md);
}
```

### Tarjetas con Efecto de Profundidad al Hover
```css
.card {
  background: var(--color-surface-card);
  border: 1px solid var(--color-border);
  border-radius: var(--radius-lg);
  padding: var(--space-6);
  transition: transform var(--duration-fast) var(--ease-spring),
              box-shadow var(--duration-fast) var(--ease-smooth),
              border-color var(--duration-fast) var(--ease-smooth);
  will-change: transform;
}

.card:hover {
  transform: translateY(-4px);
  box-shadow: var(--shadow-lg);
  border-color: var(--color-primary-light);
}
```

---

## 3. Rendimiento en Animaciones (Garantía de 60 FPS)

- **Regla Estricta:** Anima únicamente `transform` (`translate`, `scale`, `rotate`) y `opacity`.
- **Prohibido animar:** `width`, `height`, `top`, `left`, `margin`, `padding` ya que provocan *layout reflows* y caídas de fotogramas en móviles.
- **Respeto a preferencias de usuario:**
```css
@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
    scroll-behavior: auto !important;
  }
}
```

---

## 4. Responsive Design & Ergonomía Móvil

1. **Mobile-First:** Diseña pensando primero en la pantalla móvil y escala progresivamente usando Media Queries (`min-width: 640px`, `min-width: 768px`, `min-width: 1024px`, `min-width: 1280px`).
2. **Dimensiones de toque accesibles:** Todo botón, enlace o elemento interactivo debe tener un área táctil mínima de **44x44px** en dispositivos táctiles.
3. **Imágenes Adaptables:**
   ```css
   img {
     max-width: 100%;
     height: auto;
     display: block;
     object-fit: cover;
   }
   ```
4. **Tipografía Fluida:** Usa `clamp()` para tamaños de fuente y espaciados responsivos sin saltos bruscos (`font-size: clamp(1.5rem, 2.5vw + 1rem, 2.75rem);`).

---

## 5. Checklist de Verificación de Calidad Visual

- [ ] ¿Los botones e interactivos tienen estados visuales para hover, focus y active?
- [ ] ¿El contraste de color entre texto y fondo cumple con WCAG AA (mínimo 4.5:1)?
- [ ] ¿La navegación es fluida y no desborda horizontalmente en pantallas pequeñas (*no horizontal scroll*)?
- [ ] ¿Las imágenes cargan rápido y tienen `aspect-ratio` o `object-fit` adecuado?
- [ ] ¿Los iconos y tipografías están perfectamente alineados con sus textos adyacentes?
