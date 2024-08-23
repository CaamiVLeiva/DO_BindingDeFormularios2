# BindingDeFormularios2

Este proyecto es una aplicación Vue.js que permite a los usuarios ingresar datos de evaluación a través de un formulario y ver una vista previa de esos datos.

## Estructura del Proyecto

```sh
bindingdeformularios2/
├── public/
├── src/
│   ├── assets/
│   ├── components/
│   │   ├── FormularioIngreso.vue
│   │   └── VistaPrevia.vue
│   ├── App.vue
│   └── main.js
├── .gitignore
├── index.html
├── package.json
├── README.md
└── vite.config.js
```

- **App.vue**: Componente principal que integra el formulario y la vista previa.
- **FormularioIngreso.vue**: Componente del formulario para ingresar datos.
- **VistaPrevia.vue**: Componente para mostrar una vista previa de los datos ingresados.

## Tecnologías Utilizadas
- **Vue.js**: Framework progresivo para construir interfaces de usuario.
- **Bootstrap**: Framework de CSS para una interfaz moderna y responsiva.
- **Vite**: Herramienta de construcción rápida y moderna para aplicaciones web.
- **ESLint y Prettier**: Herramientas para mantener un código limpio y consistente.

## Recommended IDE Setup

[VSCode](https://code.visualstudio.com/) + [Volar](https://marketplace.visualstudio.com/items?itemName=Vue.volar) (and disable Vetur).

## Customize configuration

See [Vite Configuration Reference](https://vitejs.dev/config/).

## Project Setup

```sh
npm install
```

### Compile and Hot-Reload for Development

```sh
npm run dev
```

### Compile and Minify for Production

```sh
npm run build
```

### Lint with [ESLint](https://eslint.org/)

```sh
npm run lint
```
