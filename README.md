# Nexo Caps — Landing y catálogo de gorras

Proyecto web estático para un negocio de venta de gorras. Incluye una **landing principal** y una **página de catálogo** con fichas de producto, filtros, búsqueda y un modal de detalle.

---

## ✨ Características

### `index.html` — Landing principal
- Header sticky con navegación desktop y menú móvil.
- Hero con ilustración SVG de gorra, CTA y estadísticas.
- Sección de modelos destacados.
- Beneficios, personalización, opiniones y newsletter.
- Footer completo y botón flotante de WhatsApp.
- Enlaces a `catalogo.html` en el menú, hero, carrito, CTA final y footer.

### `catalogo.html` — Catálogo de modelos
- Mismo sistema visual que la landing: colores, tipografías, SVG y componentes.
- 6 modelos con precio, descripción, material, ajuste, tallas y colores.
- Filtros por categoría: **Todos, Clásicas, Snapback, Edición limitada, Personalizables**.
- Buscador por nombre y orden por precio o nombre.
- Modal de detalle con vista ampliada, selección de color, talla y cantidad.
- Botón **“Volver al inicio”** y enlaces a secciones de `index.html`.

### Generales
- Diseño **responsive** (móvil, tablet y escritorio).
- **Tailwind CSS vía CDN**, sin pasos de compilación.
- Ilustraciones **SVG inline** personalizables, sin depender de fotos externas.
- Carrito persistente compartido entre ambas páginas con `localStorage`.
- JavaScript vanilla para interacciones.

---

## 📁 Estructura del proyecto

```text
proy_page_01/
├── index.html      # Página principal (landing)
├── catalogo.html   # Catálogo con fichas de productos
└── README.md       # Este archivo
```

---

## 🚀 Cómo ejecutarlo

### Opción 1: abrir directamente
Abre `index.html` o `catalogo.html` con doble clic en tu navegador.

### Opción 2: servidor local (recomendado)

Desde la carpeta del proyecto:

```bash
python -m http.server 8000
```

En Windows también puedes usar:

```bash
py -m http.server 8000
```

Luego visita:

```text
http://localhost:8000
```

> Nota: Tailwind CDN y Google Fonts requieren conexión a internet.

---

## 🛠️ Tecnologías

| Tecnología | Uso |
|---|---|
| HTML5 | Estructura de ambas páginas |
| Tailwind CSS (CDN) | Estilos y sistema responsive |
| JavaScript vanilla | Filtros, modal, carrito y menú móvil |
| Google Fonts | Tipografías **Outfit** y **Inter** |
| SVG inline | Ilustraciones de gorras e íconos |
| `localStorage` | Contador de carrito compartido |

---

## 🔗 Navegación entre páginas

### Desde `index.html` hacia `catalogo.html`
- Enlace **Modelos** en el menú desktop y móvil.
- Botón del carrito en el header.
- CTA **Ver modelos** en el hero.
- CTA **Ver todos los modelos** al final de la sección de modelos.
- Enlace **Modelos** en el footer.

### Desde `catalogo.html` hacia `index.html`
- Logo en el header y footer.
- Enlace **Inicio** en el menú desktop y móvil.
- Breadcrumb **Inicio / Modelos**.
- Botón **Volver al inicio** al final del grid.
- Enlaces a **Beneficios**, **Opiniones**, **Personalización** y **Ayuda**.

---

## 🎨 Personalización

### Colores y fuentes
Cada archivo HTML tiene su propia configuración de Tailwind al inicio:

```js
tailwind.config = {
  theme: {
    extend: {
      colors: {
        ink: '#111318',
        lime: '#d7ff4f',
        cream: '#f7f6f2'
      },
      fontFamily: {
        sans: ['Inter', 'system-ui', 'sans-serif'],
        display: ['Outfit', 'Inter', 'sans-serif']
      }
    }
  }
};
```

Modifica esos valores para cambiar toda la paleta o las tipografías.

### Ilustraciones de gorra
El SVG de la gorra usa variables CSS:

```html
--crown: color de la copa
--brim: color de la visera
--accent: color del botón superior
--patch: color del parche frontal
--patchText: color de la letra del parche
```

Ejemplo:

```html
<svg style="--crown:#20242c; --brim:#0f1115; --accent:#d7ff4f;">
  <use href="#cap" />
</svg>
```

### Productos
Los datos del modal están en el objeto `products` dentro de `catalogo.html`.

Si agregas un modelo nuevo, actualiza:

1. La tarjeta en `index.html`.
2. La tarjeta en `catalogo.html`.
3. El objeto `products` en `catalogo.html`.

### Datos de contacto
Reemplaza estos valores de ejemplo por los reales:

- Teléfono de WhatsApp: `51999999999`
- Correo: `hola@nexocaps.com`
- Horario de atención
- Precios y nombres de productos

---

## 🛒 Carrito compartido

Ambas páginas usan la clave `nexoCartCount` en `localStorage`:

- Al añadir productos, el contador se actualiza y se guarda.
- Al cambiar de página, el contador se conserva.

Es una implementación de demostración. Para una tienda real, reemplázala por un backend o un carrito con persistencia de usuario.

---

## 📝 Notas

- No hay backend: el formulario de newsletter y el carrito son demostrativos.
- Los precios, opiniones y datos de contacto son de ejemplo.
- Las gorras se renderizan con SVG, por lo que no hay archivos de imágenes que reemplazar. Si quieres fotos reales, sustituye cada `<svg>` de producto por un `<img>`.

---

## 📄 Licencia

Proyecto de ejemplo libre para usar y adaptar.
