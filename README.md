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

## EQUATIONS (ecuaciones personalizadas)

La pestaña **EQUATIONS** permite crear, guardar, buscar, abrir, editar, duplicar y eliminar ecuaciones con variables. La lista empieza vacía; no hay ecuaciones de ejemplo.

- **Expresión**: se escribe con el teclado virtual (letras QWERTY, números, operaciones y funciones) o con el teclado físico. Las variables son letras A–Z; `π` y `e` (minúscula) son constantes con valor inicial editable.
- **Mayúsculas y minúsculas**: el teclado virtual escribe mayúsculas por defecto y `⇧` alterna a minúsculas. El teclado físico escribe la letra tal cual. `x` y `X` son variables distintas.
- **Variables**: se detectan solas y solo aparecen sus campos. Cambiar un valor recalcula sin tocar la expresión guardada; para cambiar la expresión hay que pulsar **Editar** y luego **Guardar cambios**.
- **Funciones**: `sin cos tan asin acos atan sinh cosh tanh log ln sqrt cbrt exp` y factorial `!`. Las funciones se reconocen cuando el nombre va seguido de `(`; en otro caso las letras son variables, así que `sin` escrito sin paréntesis se lee como `s·i·n`.
- **Combinaciones y permutaciones**: igual que en la calculadora, con los operadores infijos `n nCr r` y `n nPr r` (teclas `nCr` y `nPr`). Tienen la misma precedencia que las potencias. La secuencia literal `nCr` se lee siempre como operador, así que no puede usarse como `n·C·r`. Las ecuaciones guardadas con la notación antigua `C(n,r)` se convierten al cargarlas.
- **Validación**: división por cero, expresiones mal formadas, argumentos inválidos en `C`/`P`/factorial, dominio de funciones, variables sin valor y valores no numéricos.
- **Guardado**: en `localStorage` del navegador (clave `calc.equations.v1`). Persiste entre sesiones en el mismo navegador.
- **Nombres repetidos**: se pide confirmación antes de guardar con un nombre que ya existe. Eliminar también pide confirmación.

Ejemplo de uso (no viene precargado): `(K nCr x)*((N-K) nCr (n-x))/(N nCr n)` con nombre `Distribución hipergeométrica`.

## Pendiente respecto a la fx-85WA original

- `ENG`, `a b/c` y `d/c` (fracciones), `°′″` y `DRG▶` no hacen nada todavía.
- No hay modo de entrada `INS` ni el formato `Rnd`.
- La precisión es de 10 cifras significativas.
- Los mensajes de error son `Syntax ERROR` y `Math ERROR`.
