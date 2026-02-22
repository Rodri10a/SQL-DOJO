# ⚡ SQL Dojo — Entrenador Interactivo de SQL

> Plataforma web para practicar SQL desde cero hasta nivel avanzado, directamente en el navegador. Sin instalaciones, sin servidores, sin configuración.

---

## 📸 Vista general

SQL Dojo es una aplicación de una sola página (`index.html`) que permite escribir y ejecutar consultas SQL en tiempo real sobre datasets precargados, con validación automática de respuestas, sistema de pistas y seguimiento de progreso.

---

## ✨ Características

- **Ejecución SQL en el navegador** — Powered by [sql.js](https://github.com/sql-js/sql.js) (SQLite compilado a WebAssembly). No requiere backend.
- **3 datasets temáticos** con datos en español:
  - 🛒 **Tienda** — Clientes, productos, pedidos y detalle de pedido
  - 👥 **RRHH** — Empleados y departamentos
  - 📚 **Biblioteca** — Autores, libros, usuarios y préstamos
- **Ejercicios en 3 niveles** de dificultad:
  - 🟢 Principiante
  - 🔵 Intermedio
  - 🟣 Avanzado
- **Validación automática** — Compara el resultado de tu consulta con el esperado y muestra retroalimentación detallada.
- **Sistema de pistas** — Cada ejercicio incluye hints desbloqueables de forma progresiva.
- **Solución de referencia** — Visible bajo demanda, con advertencia para no spoilearse.
- **Chuleta SQL** — Panel de referencia rápida con sintaxis de los comandos más usados.
- **Visor de esquema** — Muestra las tablas, columnas, tipos y relaciones (PK/FK) del dataset activo.
- **Editor con numeración de líneas** — Área de código con soporte para Tab y fuente monoespaciada.
- **Progreso persistente** — Guardado automático en `localStorage`. Exportable e importable en JSON.
- **Diseño responsive** — Navegación adaptada a móvil con barra inferior y drawers deslizables.
- **Confetti 🎉** — Animación de celebración al completar un ejercicio.

---

## 🗂️ Estructura del proyecto

```
sql-dojo/
└── index.html   # Aplicación completa (HTML + CSS + JS en un solo archivo)
```

El proyecto es completamente autocontenido. No tiene dependencias locales ni archivos adicionales.

---

## 🚀 Cómo usar

### Opción 1 — Abrir directamente

```bash
# Clona el repositorio
git clone https://github.com/tu-usuario/sql-dojo.git

# Abre el archivo en tu navegador
open index.html
```

O simplemente arrastra `index.html` a cualquier navegador moderno.

### Opción 2 — Servidor local (recomendado para desarrollo)

```bash
# Con Python
python -m http.server 8000

# Con Node.js / npx
npx serve .
```

Luego accede a `http://localhost:8000`.

---

## 🧩 Datasets y esquemas

### 🛒 Tienda

| Tabla | Columnas clave |
|---|---|
| `clientes` | `id`, `nombre`, `email`, `ciudad`, `fecha_registro` |
| `productos` | `id`, `nombre`, `categoria`, `precio`, `stock` |
| `pedidos` | `id`, `cliente_id` (FK), `fecha`, `total` |
| `detalle_pedido` | `id`, `pedido_id` (FK), `producto_id` (FK), `cantidad`, `precio_unitario` |

### 👥 RRHH

| Tabla | Columnas clave |
|---|---|
| `departamentos` | `id`, `nombre`, `ubicacion` |
| `empleados` | `id`, `nombre`, `apellido`, `email`, `departamento_id` (FK), `salario`, `fecha_contratacion`, `cargo` |

### 📚 Biblioteca

| Tabla | Columnas clave |
|---|---|
| `autores` | `id`, `nombre`, `nacionalidad` |
| `libros` | `id`, `titulo`, `autor_id` (FK), `genero`, `anio_publicacion`, `disponible` |
| `usuarios` | `id`, `nombre`, `email`, `tipo_membresia` |
| `prestamos` | `id`, `libro_id` (FK), `usuario_id` (FK), `fecha_prestamo`, `fecha_devolucion` |

---

## 📊 Progreso

El progreso se guarda automáticamente en el `localStorage` del navegador bajo la clave `sql-dojo-progress`.

- **Exportar** — Descarga un archivo `sql-dojo-progreso.json` con todos los ejercicios completados.
- **Importar** — Pega el JSON exportado para restaurar el progreso (útil para cambiar de dispositivo o navegador).
- **Reiniciar** — Borra todo el progreso con confirmación previa.

---

## 🛠️ Tecnologías

| Tecnología | Uso |
|---|---|
| [sql.js v1.8.0](https://github.com/sql-js/sql.js) | Motor SQLite en WebAssembly |
| [JetBrains Mono](https://fonts.google.com/specimen/JetBrains+Mono) | Fuente del editor de código |
| [Outfit](https://fonts.google.com/specimen/Outfit) | Fuente de la interfaz |
| HTML5 / CSS3 / Vanilla JS | Sin frameworks adicionales |

---

## 🌐 Compatibilidad

Compatible con todos los navegadores modernos que soporten WebAssembly:

- ✅ Google Chrome / Chromium
- ✅ Mozilla Firefox
- ✅ Microsoft Edge
- ✅ Safari 15+
- ✅ Navegadores móviles (Android / iOS)

---

## 📝 Atajos y tips de uso

- **Tab** en el editor inserta 2 espacios de indentación.
- El botón **Ejecutar** corre la consulta y muestra los resultados en la pestaña *Resultados*.
- El botón **Validar** compara tu resultado con la solución esperada y marca el ejercicio como completado si es correcto.
- El panel **Esquema** muestra las tablas del dataset activo para consulta rápida.
- La **Chuleta** contiene sintaxis de referencia de SELECT, WHERE, JOIN, GROUP BY, ORDER BY, subqueries y más.

---

## 🤝 Contribuciones

¡Las contribuciones son bienvenidas! Podés ayudar:

- Agregando nuevos ejercicios en cualquier nivel de dificultad
- Creando nuevos datasets temáticos
- Mejorando la interfaz o la accesibilidad
- Reportando bugs o sugiriendo mejoras

Para contribuir:

```bash
# Fork del repositorio
# Creá una rama para tu feature
git checkout -b feature/nuevo-dataset-ventas

# Hacé tus cambios y comiteá
git commit -m "feat: agrego dataset de ventas con ejercicios de nivel intermedio"

# Pusheá y abrí un Pull Request
git push origin feature/nuevo-dataset-ventas
```

---

<div align="center">
  Hecho con ❤️ para aprender SQL en español
</div>
