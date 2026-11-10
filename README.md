# 🏛️ Agenda Electrónica - Intranet TCP Bolivia

Sistema web modular y responsivo desarrollado para el **Tribunal Constitucional Plurinacional de Bolivia**, diseñado para la gestión y consulta del directorio interno de funcionarios públicos.

## 🛠️ Arquitectura Tecnológica

La aplicación está construida sobre una arquitectura SPA (Single Page Application) desacoplada y modular:

- **Frontend:** React 19 + Vite 6 (JavaScript Moderno - ESM).
- **Estilos:** CSS3 Puro Estructurado (Diseño Responsivo adaptado al Manual de Marca Institucional).
- **Almacenamiento (Base de Datos):** Fichero estático `funcionarios.json` manipulado dinámicamente mediante una API en red local expuesta por el servidor de desarrollo.

---

## 🗂️ Estructura del Proyecto (Componentes Modulares)

El código ha sido segmentado siguiendo los estándares de desarrollo limpio:

- `index.html`: Puerta de entrada del portal con metadatos institucionales y el Favicon oficial.
- `src/main.jsx`: Motor de arranque e inyección de la aplicación en el DOM.
- `src/App.jsx`: Componente maestro. Gestiona los estados globales, autenticación, filtros y lógica de segmentación.
- `src/FuncionarioCard.jsx`: Sub-módulo para el renderizado elástico e independiente de las fichas telefónicas.
- `src/FormularioModal.jsx`: Formulario modal de alta/modificación con validación integrada.
- `src/ModalConfirmacion.jsx`: Ventana emergente de seguridad para confirmación de borrados.
- `src/Paginacion.jsx`: Barra elástica de paginación que optimiza el rendimiento (12 ítems por ciclo) en equipos de gama baja.
- `src/App.css`: Estilos unificados con la paleta de colores institucional (**Granate y Oro Metálico**).

---

## 🔑 Credenciales del Sistema de Administración

El modo de edición en vivo y manipulación del archivo JSON requiere la activación del rol maestro:

- **Usuario:** `admin`
- **Contraseña:** `Bolivia2026*`

---

## 🚀 Instalación y Despliegue en Red Local

### 1. Requisitos Previos

Asegúrese de tener instalado [Node.js](https://nodejs.org) (versión 18 o superior) en el servidor de la intranet.

### 2. Instalación de Dependencias

Clone o copie la carpeta del proyecto en el servidor institucional y ejecute el comando para reconstruir los paquetes:

```bash
yarn install
```

### 3. Ejecución y Exposición a la Intranet

Para que la agenda electrónica pueda ser consultada por cualquier computadora conectada a la red local de la oficina, levante el servicio exponiendo el host:

```bash
yarn dev
```

_El sistema generará una dirección IP local en la consola (Ej: `http://192.168.1.50:5173`). Ese enlace debe ser publicado o mapeado en el portal interno del Tribunal._

---

## 📦 Compilación para Servidores de Producción (IIS / Apache)

Si se desea subir el sistema compilado y minificado a un servidor web tradicional, ejecute:

```bash
yarn build
```

Esto creará una carpeta optimizada llamada **`dist/`** en la raíz del proyecto. El contenido de esa carpeta está listo para ser copiado y servido directamente.

---

**Desarrollado y Optimizado para la Dirección de Sistemas e Informática del TCP.**
