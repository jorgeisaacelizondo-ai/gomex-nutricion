# Reglas de Diseño Visual y Estética Premium

Estas reglas se aplican siempre que se creen o modifiquen archivos de vista, plantillas HTML, CSS o componentes de interfaz.

---

## 1. Principios Visuales Obligatorios
- **Paletas Curadas:** Nunca usar colores primarios saturados sin calibrar (como `#ff0000` o `#0000ff`). Emplear siempre paletas HSL equilibradas.
- **Grilla de Espaciado:** Respetar la base de 4px/8px para padding y márgenes (`8px`, `12px`, `16px`, `24px`, `32px`, `48px`).
- **Profundidad y Capas:** Usar sombras suaves y difusas (múltiples capas con baja opacidad) en lugar de bordes negros o sombras duras.
- **Tipografía con Personalidad:** Utilizar fuentes modernas de Google Fonts adecuadas al producto y verificar siempre `line-height` (1.4 - 1.6 para texto, 1.1 - 1.25 para títulos) y `letter-spacing`.

## 2. Interactividad y Micro-Animaciones
- Todo botón, tarjeta o enlace interactivo debe responder con micro-animaciones en `hover`, `active` y `focus`.
- Usar curvas de aceleración naturales (`cubic-bezier(0.4, 0, 0.2, 1)` o resortes).
- No dejar estados sin estilizar (especialmente el foco de teclado para accesibilidad).

## 3. Patrones de Diseño Prohibidos (Clichés a Evitar)
- ❌ **No fondos con mallas o patrones genéricos:** A menos que sea solicitado explícitamente.
- ❌ **No tarjetas sobre-anidadas:** No colocar más de dos niveles de tarjetas dentro de otras tarjetas.
- ❌ **No bordes de neón o brillos excesivos sin justificación:** Mantener la estética limpia, moderna y refinada.
