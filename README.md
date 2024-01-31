## Guia paso a paso para instalar y configurar tipos de props en React y el Testing en Jest

## Instalación de React

1. `npm create vite@latest`
2. `cd my-vite-app`
3. `npm i -y`
4. `npm run dev`

## Instalación de PropTypes

1. `npm i prop-types`
2. `import PropType from 'prop-types'`
3. `MyComponent.propTypes = { prop: PropType.string.isRequired }`
4. `MyComponent.defaultProps = { prop: 'default value' }`

## Instalación de Jest

1. `npm i -D jest` para instalar Jest. [Documentación](https://jestjs.io/docs/getting-started)
2. En el package.json agregar `"test": "jest --watchAll"` en scripts.
3. `npm i -D @types/jest` para tener autocompletado.
4. `npm run test` para correr los tests.
5. `npm i -D babel-jest @babel/core @babel/preset-env` para poder usar ES6.
6. `npm i -D @babel/preset-react` para poder usar JSX en los tests
7. Crear un archivo babel.config.js con el siguiente contenido:
```
module.exports = {
  presets: [
    ['@babel/preset-env', {targets: { node: 'current'}}],
    ['@babel/preset-react', {runtime: 'automatic'}]
  ],
};
```
8. `npm i -D @testing-library/react` para poder usar test en React de manera más sencilla.
9. `import { render } from "@testing-library/react"` para poder usar render en los tests de React.
10. `npm i -D jest-environment-jsdom` para poder usar el DOM en los tests
11. `npm i -D whatwg-fetch` para poder usar fetch en los tests.
12. Crear un archivo jest.config.js con el siguiente contenido:
```
module.exports = {
  testEnvironment: 'jest-environment-jsdom',
  setupFiles: ['./jest.setup.js']
}
```
13. Crear un archivo jest.setup.js con el siguiente contenido:
```
import 'whatwg-fetch';
```

> Si marca que no se puede usar con módulos, cambiar la extensión del archivo a .cjs para babel.config.cjs y jest.config.cjs