---
name: ui-ux-designer
description: >-
  Especialista en diseño UI/UX, sistemas de diseño, paletas de color HSL armónicas,
  tipografía con jerarquía estricta, espaciado con grilla de 4px, micro-animaciones
  y diseño de componentes modernos. Usar cuando el usuario pida diseñar, rediseñar,
  mejorar la estética visual, elegir paletas, tipografías, crear layouts o elevar la calidad visual de una interfaz.
---

# UI/UX Designer & Design System Specialist

Esta skill proporciona las directrices y estándares para crear experiencias digitales visualmente atractivas, modernas, refinadas y centradas en el usuario (inspiradas en el rol *Designer / Aria* de *vibe-coder-kit*).

---

## 1. Filosofía de Diseño

- **Menos, pero mejor:** La estética surge de la eliminación del desorden y el uso intencional del espacio negativo (whitespace).
- **Animación con propósito:** No agregues animaciones meramente decorativas que distraigan. Cada micro-interacción debe dar feedback claro sobre estados (*hover*, *active*, *loading*, *success*).
- **Jerarquía visual primero:** El contraste de tamaño, peso tipográfico, color y espaciado debe guiar el ojo del usuario de manera intuitiva y sin esfuerzo.
- **Pensamiento sistémico:** Diseña sistemas completos de tokens y estados, no elementos aislados.

---

## 2. Sistema de Tokens de Diseño

Al crear o refinar estilos, establece siempre un sistema de variables CSS en `:root`:

```css
:root {
  /* --- PALETA DE COLORES HSL (Curated & Harmonious) --- */
  --color-primary: hsl(250, 84%, 60%);
  --color-primary-hover: hsl(250, 84%, 54%);
  --color-primary-light: hsl(250, 84%, 96%);

  --color-bg-base: hsl(220, 15%, 97%);
  --color-surface-card: hsl(0, 0%, 100%);
  --color-surface-elevated: hsl(0, 0%, 100%);
  
  --color-text-primary: hsl(220, 20%, 12%);
  --color-text-secondary: hsl(220, 10%, 46%);
  --color-text-muted: hsl(220, 10%, 65%);
  --color-border: hsl(220, 14%, 90%);

  /* --- ESPACIADO (Base Grid de 4px / 8px) --- */
  --space-1: 0.25rem;  /* 4px */
  --space-2: 0.5rem;   /* 8px */
  --space-3: 0.75rem;  /* 12px */
  --space-4: 1rem;     /* 16px */
  --space-5: 1.25rem;  /* 20px */
  --space-6: 1.5rem;   /* 24px */
  --space-8: 2rem;     /* 32px */
  --space-10: 2.5rem;  /* 40px */
  --space-12: 3rem;    /* 48px */
  --space-16: 4rem;    /* 64px */

  /* --- BORDER RADIUS --- */
  --radius-sm: 6px;
  --radius-md: 10px;
  --radius-lg: 16px;
  --radius-xl: 24px;
  --radius-full: 9999px;

  /* --- SOMBRAS CON PROFUNDIDAD Y DIFUSIÓN SUAVE --- */
  --shadow-sm: 0 1px 2px rgba(0, 0, 0, 0.04), 0 1px 3px rgba(0, 0, 0, 0.06);
  --shadow-md: 0 4px 6px -1px rgba(0, 0, 0, 0.05), 0 2px 4px -2px rgba(0, 0, 0, 0.05);
  --shadow-lg: 0 10px 15px -3px rgba(0, 0, 0, 0.06), 0 4px 6px -4px rgba(0, 0, 0, 0.04);
  --shadow-xl: 0 20px 25px -5px rgba(0, 0, 0, 0.08), 0 8px 10px -6px rgba(0, 0, 0, 0.03);

  /* --- MOTION & CURVAS DE ACELERACIÓN --- */
  --duration-instant: 100ms;
  --duration-fast: 180ms;
  --duration-normal: 260ms;
  --duration-slow: 400ms;
  --ease-smooth: cubic-bezier(0.4, 0, 0.2, 1);
  --ease-spring: cubic-bezier(0.34, 1.56, 0.64, 1);
  --ease-out: cubic-bezier(0, 0, 0.2, 1);
}
```

---

## 3. Guía de Tipografía y Jerarquía

1. **Tipografía moderna:** Usa fuentes legibles y con personalidad desde Google Fonts (por ejemplo, *Plus Jakarta Sans*, *Inter*, *Outfit*, *DM Sans*, *Syne* o *Space Grotesk* según el carácter de la marca).
2. **Escala y ritmo tipográfico:**
   - **H1 (Hero / Título principal):** `clamp(2rem, 4vw + 1rem, 3.5rem)`, `font-weight: 700|800`, `letter-spacing: -0.03em`, `line-height: 1.15`.
   - **H2 (Secciones):** `1.75rem` a `2.25rem`, `font-weight: 700`, `letter-spacing: -0.02em`.
   - **H3 (Tarjetas / Subsecciones):** `1.25rem` a `1.5rem`, `font-weight: 600`.
   - **Body (Cuerpo de texto):** `1rem` (16px), `line-height: 1.6`, `color: var(--color-text-secondary)`.
   - **Captions / Metadatos:** `0.875rem` (14px) o `0.75rem` (12px), `letter-spacing: 0.02em`.

---

## 4. Especificaciones de Micro-Animaciones y Estados

Todo componente interactivo (botones, tarjetas, inputs, chips) debe incluir estados claros:

| Estado | Transformación Visual | Duración & Easing |
|---|---|---|
| **Hover (Botón)** | `transform: translateY(-2px); box-shadow: var(--shadow-md); filter: brightness(1.05);` | `200ms var(--ease-smooth)` |
| **Active (Botón)** | `transform: translateY(0) scale(0.98);` | `80ms var(--ease-out)` |
| **Focus Visible** | `outline: none; box-shadow: 0 0 0 3px var(--color-primary-light), 0 0 0 4px var(--color-primary);` | `150ms var(--ease-smooth)` |
| **Hover (Tarjeta)** | `transform: translateY(-4px); box-shadow: var(--shadow-lg); border-color: ...` | `250ms var(--ease-spring)` |

---

## 5. Reglas de Oro y Anti-Patrones a Evitar

- ❌ **Evitar colores genéricos saturados:** No uses `red`, `blue`, `#000` o `#fff` puros sin matices; utiliza tonos HSL equilibrados.
- ❌ **Evitar bordes duros de 1px oscuros:** Utiliza bordes suaves y sutiles con `rgba(...)` o `hsl(..., ..., 90%)`.
- ❌ **Evitar falta de whitespace:** Dale aire a los componentes; los márgenes y rellenos amplios transmiten calidad y orden.
- ❌ **Evitar animaciones pesadas:** Solo anima `transform` y `opacity` para mantener 60 FPS en todo momento.
