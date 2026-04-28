En este proyecto encontraras todo lo esencial de una pagina web.


/*
body {
  height: 100vh;
  display: flex;
  justify-content: center; /* horizontal */
  align-items: center;     /* vertical */
  margin: 0;
}

👉 Esto centra todo en el medio de la pantalla
💡 Muy usado en login pages o landing pages

*/


/////////////////////////////////////////////////////////////////////////////////////////////////////////

🔹 2. box-sizing
👉 ¿Qué problema resuelve?

Por defecto (content-box):

div {
  width: 200px;
  padding: 20px;
  border: 10px solid black;
}
👉 Tamaño REAL:
200 + 40 (padding) + 20 (border) = 260px
⚠️ Esto rompe layouts fácilmente

🔹 Valores de box-sizing
1. content-box (por defecto)

❌ Suma todo extra

box-sizing: content-box;

👉 El width NO incluye padding ni border

2. border-box (el que SI debes usar)
box-sizing: border-box;

👉 El tamaño TOTAL siempre será el que tú defines

✅ Ejemplo comparativo
❌ Con content-box
.caja {
  width: 200px;
  padding: 20px;
  border: 10px solid red;
}

👉 Resultado real: 260px

✅ Con border-box
.caja {
  width: 200px;
  padding: 20px;
  border: 10px solid red;
  box-sizing: border-box;
}

👉 Resultado real: 200px exactos

✔ Todo se ajusta dentro

///////////////////////////////////////////////////////////////////////////////////////////////////

👉 Lo correcto en proyectos reales es esto:

✅ Forma profesional (usada en todos lados)
*,
*::before,
*::after {
  box-sizing: border-box;
}
👉 ¿Por qué así?

Porque:

Aplica a TODOS los elementos
Incluye pseudo-elementos (::before, ::after)
Evita errores de diseño

💡 No basta solo con el body

🔥 Ejemplo real completo (muy típico)
/* Reset básico */
*,
*::before,
*::after {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  height: 100vh;
  font-family: Arial, sans-serif;
}

/* Contenedor */
.container {
  width: 300px;
  padding: 20px;
  border: 5px solid black;
}

👉 Resultado:

El .container mide exactamente 300px
No se rompe el layout
El body ocupa toda la pantalla


////////////////////////////////////////////////////////////

Si estás trabajando con:

WordPress (como tú)
React / Next.js

👉 SIEMPRE usa border-box global

Te ahorra:

bugs visuales
desbordes raros
cálculos innecesarios