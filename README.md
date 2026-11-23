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
- **ENG**: tras un resultado, `ENG` lo muestra con exponente múltiplo de 3 (`12345` → `12.345E3`); otra pulsación sube el exponente y `SHIFT` + `ENG` lo baja.
- **Edición**: `◄ ►` (REPLAY) mueven el cursor, `DEL` borra antes del cursor.

## EQUATIONS (ecuaciones personalizadas)

La pestaña **EQUATIONS** permite crear, guardar, buscar, abrir, editar, duplicar y eliminar ecuaciones con variables. La lista empieza vacía; no hay ecuaciones de ejemplo.

- **Expresión**: se escribe con el teclado virtual o con el teclado físico. En pantalla `nCr` y `nPr` se muestran como `C` y `P`. Las variables son letras A–Z; `π` y `e` (minúscula) son constantes con valor inicial editable.
- **Teclado**: la misma disposición que la calculadora. `ABC` cambia entre números y letras (en el teclado de letras la tecla pasa a `123`). `ALPHA` alterna mayúsculas y minúsculas. `SHIFT` activa las funciones secundarias (`x!`, `nPr`, `10ˣ`, `eˣ`, `sin⁻¹`, `π`...). Las teclas sin función en EQUATIONS (ENG, a b/c, Pol(, hyp, STO, RCL, M+, MODE) se muestran deshabilitadas.
- **Variables**: se detectan solas y solo aparecen sus campos. Cambiar un valor recalcula sin tocar la expresión guardada; para cambiar la expresión hay que pulsar **Editar** y luego **Guardar** (arriba, junto al nombre).
- **Calcular**: muestra el resultado y lo pasa a la calculadora normal como valor actual y como `Ans`, para seguir operando con él.
- **Funciones**: `sin cos tan asin acos atan sinh cosh tanh log ln sqrt cbrt exp` y factorial `!`. Las funciones se reconocen cuando el nombre va seguido de `(`; en otro caso las letras son variables, así que `sin` escrito sin paréntesis se lee como `s·i·n`.
- **Combinaciones y permutaciones**: igual que en la calculadora, con los operadores infijos `n nCr r` y `n nPr r` (teclas `nCr` y `nPr`). Tienen la misma precedencia que las potencias. La secuencia literal `nCr` se lee siempre como operador, así que no puede usarse como `n·C·r`. Las ecuaciones guardadas con la notación antigua `C(n,r)` se convierten al cargarlas.
- **Validación**: división por cero, expresiones mal formadas, argumentos inválidos en `nCr`, `nPr` y factorial, dominio de funciones, variables sin valor y valores no numéricos.
- **Guardado**: en `localStorage` del navegador (clave `calc.equations.v1`). Persiste entre sesiones en el mismo navegador.
- **Nombres repetidos**: se pide confirmación antes de guardar con un nombre que ya existe. Eliminar también pide confirmación.

Ejemplo de uso (no viene precargado): `(K nCr x)*((N-K) nCr (n-x))/(N nCr n)` con nombre `Distribución hipergeométrica`.

## NOTAS (promedio ponderado)

La pestaña **NOTAS** calcula notas con ponderaciones. Cada fila tiene la nota y su ponderación en %.

- **Validación**: las ponderaciones deben sumar 100%; si no, avisa cuánto falta o cuánto sobra. También valida números y que la nota esté dentro de la escala (mínima y máxima editables, 1 a 7 por defecto).
- **Nota que falta**: agrega una fila con la ponderación restante (por ejemplo, con 25% y 25% agrega una de 50%).
- **Precisión**: el redondeo es escolar (mitad hacia arriba) y limpia el ruido de coma flotante; la nota necesaria se redondea siempre hacia arriba a 4 decimales para que realmente alcance el objetivo.
- **Resolver**: deja una nota vacía (solo con su ponderación) y escribe la nota objetivo; calcula qué nota necesitas. Si hay varias vacías, indica la nota necesaria en cada una. Avisa si no es alcanzable o si ya lo tienes asegurado.
- **Repartir lo que falta equitativamente**: reparte el % que falta para 100% solo entre las notas (o subnotas de una fila) que no tienen ponderación; las que ya la tienen no se tocan. La última toma el resto del redondeo para que sume exactamente 100%. Si no hay casillas vacías o ya se llegó a 100%, no hace nada.
- **Subnotas**: el botón `+▾` de una fila le agrega subnotas (por ejemplo, un taller que vale 10% y tiene 3 notas). La ponderación de cada subnota es un % de esa fila y deben sumar 100% (hay botón `+ Subnota que falta`). La nota de la fila pasa a ser el promedio de sus subnotas, y la nota objetivo también se resuelve sobre una subnota vacía. Al quitar todas las subnotas la fila vuelve a ser normal.
- Sin ninguna nota vacía y con 100%, muestra la nota final.
- Los datos se guardan en `localStorage` (clave `calc.grades.v1`).

## Ajustes (⚙)

- **Tema**: `Sistema` (sigue el modo del dispositivo), `Claro` u `Oscuro`. Se recuerda entre sesiones (`calc.settings.v1`).
- **Aproximación de notas**: activada por defecto, a 1 decimal (configurable de 0 a 4). Redondea la nota final como lo hacen muchas universidades (3.95 → 4.0) y se usa también al resolver: con objetivo 4 y 1 decimal basta una nota final de 3.95. Los cálculos intermedios no se redondean.
- **Datos**: botones, con confirmación, para borrar el historial, limpiar las notas o borrar todas las ecuaciones.

## Pendiente respecto a la fx-85WA original

- `a b/c` y `d/c` (fracciones), `°′″` y `DRG▶` no hacen nada todavía.
- No hay modo de entrada `INS` ni el formato `Rnd`.
- La precisión es de 10 cifras significativas.
- Los mensajes de error son `Syntax ERROR` y `Math ERROR`.
