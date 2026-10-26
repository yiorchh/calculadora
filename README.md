# Calculadora científica

Calculadora científica web de un solo archivo (`index.html`), con la misma organización de teclas que una fx-85WA. Funciona sin dependencias ni build, así que se puede publicar directamente con GitHub Pages.

## Uso

Abre `index.html` en el navegador o activa GitHub Pages sobre la rama con este archivo. Está pensada para pantallas de 360px o más (por ejemplo, iPhone 13 Pro).

Teclado físico: dígitos, `+ - * /`, `( ) , . ^`, `Enter` para `=`, `Backspace` para DEL, `Esc` para AC y flechas para REPLAY.

## Funciones incluidas

- **Básicas**: `+ − × ÷`, paréntesis, multiplicación implícita (`2π`), `%`, `Ans`.
- **Potencias y raíces**: `x²`, `x³`, `xʸ`, `√`, `³√`, `ˣ√` (SHIFT + xʸ).
- **Logaritmos y exponenciales**: `log`, `ln`, `10ˣ` y `eˣ` (SHIFT).
- **Trigonometría**: `sin`, `cos`, `tan` y sus inversas con SHIFT; `hyp` para hiperbólicas. Modo `DEG`, `RAD` o `GRA` con `MODE` seguido de `3`, `4` o `5`.
- **Combinatoria**: `x⁻¹` (inverso), `x!` (SHIFT), `nCr`, `nPr` (SHIFT).
- **Coordenadas**: `Pol(` y `Rec(` (SHIFT). Se guarda el ángulo o la coordenada secundaria en la variable `Y`.
- **Memoria**: `STO` / `RCL` seguido de `ALPHA` + variable (`A B C D E F X Y M`), `M+` y `M−`, `Ans`.
- **Estadística** (`MODE` + `2`): `M+` agrega datos, `SHIFT` + `M+` quita el último, `n`, `Σx`, `Σx²`, `x̄`, `xσn`, `xσn-1`. `SHIFT` + `AC` (Mcl) borra los datos.
- **Constantes**: `π` (SHIFT + EXP) y `Ran#` (SHIFT + `.`).
- **Edición**: `◄ ►` (REPLAY) mueven el cursor, `DEL` borra antes del cursor.

## Pendiente respecto a la fx-85WA original

- `ENG`, `a b/c` y `d/c` (fracciones), `°′″` y `DRG▶` no hacen nada todavía.
- No hay modo de entrada `INS` ni el formato `Rnd`.
- La precisión es de 10 cifras significativas.
- Los mensajes de error son `Syntax ERROR` y `Math ERROR`.
