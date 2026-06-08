# Proyecto-Dia3-MF0491

**Sesion 3 - 08/06/2026 - UF1841 - CSS Avanzado + Flexbox + Box Model**

---

## BLOQUE 1 - Conceptos Clave

### Box Model (Modelo de Caja)
- Todo elemento HTML es una caja rectangular
- Capas de afuera hacia adentro: margin → border → padding → content
- `box-sizing: border-box` incluye padding y border en el ancho total (recomendado)
- `box-sizing: content-box` (por defecto): el ancho NO incluye padding ni border

### Colores en CSS
- HEX: `#RRGGBB` o `#RGB` → ej: `#ff0000` (rojo)
- RGB: `rgb(255, 0, 0)` → valores de 0 a 255
- RGBA: `rgba(255, 0, 0, 0.5)` → ultimo valor = opacidad (0 transparente, 1 solido)
- HSL: `hsl(0, 100%, 50%)` → matiz, saturacion, luminosidad
- Nombres de color: `red`, `blue`, `white`, `black`, etc.

### Unidades de medida CSS
- Absolutas: `px` (pixeles), `pt`, `cm`
- Relativas: `%` (porcentaje del padre), `em` (relativo al font-size del padre), `rem` (relativo al font-size del root)
- Viewport: `vw` (% del ancho de ventana), `vh` (% del alto de ventana)

### Flexbox
- Sistema de maquetacion unidimensional (fila o columna)
- Se activa con `display: flex` en el contenedor padre
- Eje principal (main axis) y eje cruzado (cross axis)
- Propiedades del CONTENEDOR: `flex-direction`, `justify-content`, `align-items`, `flex-wrap`, `gap`
- Propiedades de los HIJOS: `flex`, `flex-grow`, `flex-shrink`, `flex-basis`, `align-self`, `order`

### Valores clave de Flexbox
- `flex-direction`: `row` (defecto) | `column` | `row-reverse` | `column-reverse`
- `justify-content`: `flex-start` | `flex-end` | `center` | `space-between` | `space-around` | `space-evenly`
- `align-items`: `stretch` (defecto) | `flex-start` | `flex-end` | `center` | `baseline`
- `flex-wrap`: `nowrap` (defecto) | `wrap` | `wrap-reverse`

---

## BLOQUE 2 - Codigo y Estructura

### Reset CSS + Box Model global
```css
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
```

### Demostracion Box Model
```css
.caja {
  width: 300px;
  height: 200px;
  padding: 20px;       /* espacio interior */
  border: 2px solid #333; /* borde */
  margin: 30px auto;   /* espacio exterior + centrado horizontal */
  background-color: #e8f4f8;
}
```

### Colores en practica
```css
body {
  background-color: #f0f0f0;        /* HEX */
  color: rgb(50, 50, 50);           /* RGB */
}

.destacado {
  background-color: rgba(0, 123, 255, 0.15); /* RGBA semitransparente */
  border-left: 4px solid #007bff;
}
```

### Layout con Flexbox - Navbar horizontal
```css
nav {
  display: flex;
  justify-content: space-between;
  align-items: center;
  background-color: #2c3e50;
  padding: 15px 30px;
}

nav a {
  color: white;
  text-decoration: none;
  padding: 8px 16px;
}

nav a:hover {
  background-color: rgba(255,255,255,0.2);
  border-radius: 4px;
}
```

### Layout con Flexbox - Tarjetas en fila
```css
.contenedor-tarjetas {
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
  justify-content: center;
  padding: 40px 20px;
}

.tarjeta {
  flex: 1 1 250px;  /* crece, se encoge, base 250px */
  max-width: 300px;
  background: white;
  border-radius: 8px;
  padding: 20px;
  box-shadow: 0 2px 10px rgba(0,0,0,0.1);
}
```

### HTML estructura con Flexbox aplicado
```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Pagina con Flexbox</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>
  <header>
    <nav>
      <h1>Mi Web</h1>
      <ul>
        <li><a href="#">Inicio</a></li>
        <li><a href="#">Sobre mi</a></li>
        <li><a href="#">Contacto</a></li>
      </ul>
    </nav>
  </header>
  <main class="contenedor-tarjetas">
    <div class="tarjeta">
      <h2>Tarjeta 1</h2>
      <p>Contenido de ejemplo...</p>
    </div>
    <div class="tarjeta">
      <h2>Tarjeta 2</h2>
      <p>Contenido de ejemplo...</p>
    </div>
    <div class="tarjeta">
      <h2>Tarjeta 3</h2>
      <p>Contenido de ejemplo...</p>
    </div>
  </main>
</body>
</html>
```

---

## BLOQUE 3 - Lo que entra SI o SI (Examen)

- [ ] Box Model: orden de capas de afuera hacia adentro (margin > border > padding > content)
- [ ] Diferencia entre `box-sizing: content-box` y `box-sizing: border-box`
- [ ] Formatos de color: HEX, RGB, RGBA (el 4to valor de RGBA es la opacidad)
- [ ] Diferencia entre `em` y `rem`: em relativo al padre, rem relativo al root (`<html>`)
- [ ] Para activar Flexbox: `display: flex` en el CONTENEDOR (no en los hijos)
- [ ] `justify-content` controla el eje principal (horizontal en row)
- [ ] `align-items` controla el eje cruzado (vertical en row)
- [ ] `flex-wrap: wrap` permite que los elementos salten de linea
- [ ] `gap` en Flexbox: espacio entre elementos hijos (sin usar margin)
- [ ] `space-between`: los extremos pegan a los bordes, espacio entre elementos
- [ ] `space-around`: espacio igual alrededor de cada elemento (mitad en extremos)
- [ ] `flex: 1 1 250px` = grow=1, shrink=1, basis=250px

---

## BLOQUE 4 - Tareas / Checklist del Dia

- [x] Revisar y comprender el Box Model con herramientas de desarrollador (F12)
- [x] Practicar formatos de color HEX, RGB y RGBA en CSS
- [x] Aplicar `display: flex` para crear navbar horizontal
- [x] Crear layout de tarjetas con Flexbox (`flex-wrap`, `gap`, `justify-content`)
- [x] Usar `box-sizing: border-box` como reset global
- [x] Probar `justify-content` y `align-items` con diferentes valores
- [x] Actualizar `index.html` de la pagina personal con layout Flexbox
- [x] Subir cambios a GitHub con commit descriptivo
