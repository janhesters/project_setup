# React

## Redux

```bash
yarn add redux react redux
```

## Unit tests

```bash
yarn add --dev riteway @babel/core @babel/polyfill @babel/preset-env @babel/register @babel/preset-react tap-nirvana
```

`package.json`:

```json
"test": "riteway -r @babel/register -r @babel/polyfill 'src/**/*.test.js' | tap-nirvana",
```

`.babelrc`:

```json
{
  "presets": [
    [
      "@babel/preset-env",
      {
        "targets": ["last 2 versions", "safari >= 7"]
      }
    ],
    "@babel/preset-react"
  ]
}
```

## ESLint

```bash
yarn add --dev eslint eslint-plugin-simple-import-sort eslint-config-prettier
```

`.eslintrc.json`:

```json
{
  "extends": ["react-app", "prettier"],
  "plugins": ["simple-import-sort"],
  "rules": {
    "simple-import-sort/sort": "error",
    "import/order": "off"
  }
}
```

## PropTypes

Yarn

```bash
yarn add --dev prop-types
```

## E2E

Yarn:

```bash
yarn add --dev cypress eslint-plugin-cypress cypress-testing-library
```

`.eslintrc.json`:

```json
{
  "extends": ["react-app", "plugin:cypress/recommended", "prettier"],
  "plugins": ["cypress", "simple-import-sort"],
  "env": {
    "cypress/globals": true
  },
  "rules": {
    "simple-import-sort/sort": "error",
    "import/order": "off"
  }
}
```

`package.json`:

```json
"cypress:open": "cypress open",
```

Next, replace `command.js` with:

```js
import 'cypress-testing-library/add-commands';
```

Replace `cypress.json`:

```json
{
  "baseUrl": "http://localhost:3000",
  "env": {
    "email": "jan.hesters@rwth-aachen.de",
    "password": "digichurch-x3"
  }
}
```

And add it to your `.gitignore`.
