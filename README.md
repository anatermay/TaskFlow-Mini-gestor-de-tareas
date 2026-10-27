# TaskFlow-Mini-gestor-de-tareas
Una pequeña aplicación para gestionar tareas de trabajo, con una interfaz moderna y funcional. El usuario podrá añadir tareas, marcarlas como completadas, filtrarlas y eliminarlas.

## Requisitos

## Tecnologías empleadas

### Node Package Manager

`npm` (Node Package Manager) es el sistema de gestión de paquetes predeterminado para Node.js y el ecosistema de JavaScript. Funciona como una gran tienda de código donde los desarrolladores pueden descargar, compartir y administrar bibliotecas, frameworks y herramientas para sus proyectos.

Sus características principales son:
• Instalación automática: Se instala en tu ordenador de forma predeterminada cuando instalas Node.js.
• Línea de comandos (CLI): Permite ejecutar órdenes desde la terminal para instalar, actualizar o eliminar librerías (como npm install o npm update).
• Archivo package.json: Registra todas las dependencias y versiones que utiliza un proyecto para facilitar el trabajo en equipo.
• Repositorio global: Cuenta con un registro público enorme con más de un millón de paquetes de software reutilizables.
Puedes consultar más detalles y buscar librerías directamente en la página oficial de npm.

### Vite

Vite es una herramienta de compilación y un servidor de desarrollo para la web moderna, creada por Evan You (el autor de Vue.js). Su nombre significa "rápido" en francés.

Está diseñada para reemplazar a empaquetadores más antiguos y pesados como Webpack, ofreciendo un arranque de servidor casi instantáneo y una recarga en caliente extremadamente veloz (HMR). Funciona con JavaScript, TypeScript y frameworks populares como React, Vue, Svelte y Angular.

Vite utiliza los módulos de ES nativos del navegador. Al modificar el código, solo se actualiza el módulo específico que cambió. Viiene configurado para comenzar a trabajar de inmediato con JSX, TypeScript, CSS y más. Además, utiliza herramientas avanzadas, como Rolldown, para generar archivos estáticos limpios y rápidos.

#### Módulos ES nativos

Los módulos ES nativos (ESM o ECMAScript Modules) son el estándar oficial de JavaScript para dividir y organizar el código en múltiples archivos sin necesidad de empaquetadores externos (bundlers) como Webpack o Vite.

El concepto es similar a los _header files_ de C. Ambos sirven para organizar y reorganizar código en múltiples archivos. Las analogías serían:

| JavaScript  | C           |
| ----------- | ----------- |
| Archivo .js | Archivo .c  |
| `export`    | Archivo .h  |
| `import`    | `include`   |

En C, si haces un #include "archivo.h", el preprocesador literalmente "copia y pega" el código de ese cabecero dentro de tu archivo antes de compilar. Si te equivocas e incluyes el mismo archivo varias veces, puedes duplicar código (por eso se usan los Include Guards como #ifndef).

En JavaScript, el navegador lee los import, busca los archivos de forma inteligente, crea una sola instancia de cada módulo y le da a tu script acceso a las funciones que se hayan "exportado". No hay duplicación ni peligro de romper el código por importarlo en varios sitios.

#### ¿Cómo crear un proyecto en Vite?

```
# 1. Crear el proyecto.
npm create vite@latest

# Sigue las instrucciones para elegir el nombre del proyecto y el framework.

# 2. Entrar en la carpeta del proyecto.
cd <nombre-de-tu-proyecto>

# 3. Instalar las dependencias.
bash npm install

# 4. Iniciar el servidor de desarrollo.
bash npm run dev

```

_El [enlace local](http://localhost:5173) se abrirá generalmente en el puerto 5173 del ordenador_

#### Linter

Un linter es una herramienta de análisis estático de código que examina tu proyecto en busca de errores de sintaxis, variables sin usar, fallos lógicos y malas prácticas antes de que se ejecute. En el ecosistema de Vite, un linter no viene integrado de serie en el núcleo de la herramienta. Vite se enfoca principalmente en ser un empaquetador y servidor de desarrollo ultrarrápido. Sin embargo, es fundamental añadirlo para mantener la calidad del código.

`ESLint` es el estándar clásico y más utilizado para proyectos de JavaScript y TypeScript en Vite. Analiza el código mediante reglas personalizables y se integra con tu editor.


---

# React + TypeScript + Vite

This template provides a minimal setup to get React working in Vite with HMR and some ESLint rules.

Currently, two official plugins are available:

- [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react) uses [Oxc](https://oxc.rs)
- [@vitejs/plugin-react-swc](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react-swc) uses [SWC](https://swc.rs/)

## React Compiler

The React Compiler is not enabled on this template because of its impact on dev & build performances. To add it, see [this documentation](https://react.dev/learn/react-compiler/installation).

## Expanding the ESLint configuration

If you are developing a production application, we recommend updating the configuration to enable type-aware lint rules:

```js
export default defineConfig([
  globalIgnores(['dist']),
  {
    files: ['**/*.{ts,tsx}'],
    extends: [
      // Other configs...

      // Remove tseslint.configs.recommended and replace with this
      tseslint.configs.recommendedTypeChecked,
      // Alternatively, use this for stricter rules
      tseslint.configs.strictTypeChecked,
      // Optionally, add this for stylistic rules
      tseslint.configs.stylisticTypeChecked,

      // Other configs...
    ],
    languageOptions: {
      parserOptions: {
        project: ['./tsconfig.node.json', './tsconfig.app.json'],
        tsconfigRootDir: import.meta.dirname,
      },
      // other options...
    },
  },
])

```

You can also install [eslint-plugin-react-x](https://npmx.dev/package/eslint-plugin-react-x) and [eslint-plugin-react-dom](https://npmx.dev/package/eslint-plugin-react-dom) for React-specific lint rules:

```js
// eslint.config.js
import reactX from 'eslint-plugin-react-x'
import reactDom from 'eslint-plugin-react-dom'

export default defineConfig([
  globalIgnores(['dist']),
  {
    files: ['**/*.{ts,tsx}'],
    extends: [
      // Other configs...
      // Enable lint rules for React
      reactX.configs['recommended-typescript'],
      // Enable lint rules for React DOM
      reactDom.configs.recommended,
    ],
    languageOptions: {
      parserOptions: {
        project: ['./tsconfig.node.json', './tsconfig.app.json'],
        tsconfigRootDir: import.meta.dirname,
      },
      // other options...
    },
  },
])

```
