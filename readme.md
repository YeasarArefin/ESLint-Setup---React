ESLint Setup For React

- Install `ESLint` and `Prettier` VSCcode extention.

<br/>

- Install The Packages

```sh $ 
yarn add -D eslint eslint-plugin-react eslint-config-airbnb@latest eslint-plugin-import eslint-plugin-jsx-a11y eslint-plugin-react-hooks prettier eslint-config-prettier eslint-plugin-prettier
```

<br/>

- Create a `.eslintrc` file in the project root and enter the below contents:

```json
{
  "env": {
    "browser": true,
    "es2021": true
  },
  "extends": [
    "airbnb",
    "airbnb/hooks",
    "eslint:recommended",
    "prettier",
    "plugin:jsx-a11y/recommended"
  ],
  "overrides": [],
  "parserOptions": {
    "ecmaVersion": "latest",
    "sourceType": "module"
  },
  "plugins": ["prettier", "react", "react-hooks"],
  "rules": {
    "react/react-in-jsx-scope": 0,
    "react-hooks/rules-of-hooks": "error",
    "no-console": 0,
    "react/state-in-constructor": 0,
    "indent": 0,
    "linebreak-style": 0,
    "react/prop-types": 0,
    "jsx-a11y/click-events-have-key-events": 0,
    "no-unused-vars": "off",
    "no-shadow": "off",
    "arrow-body-style": "off",
    "global-require": 0,
    "react/jsx-filename-extension": [
      1,
      {
        "extensions": [".js", ".jsx"]
      }
    ],
    "prettier/prettier": [
      "error",
      {
        "trailingComma": "es5",
        "singleQuote": true,
        "printWidth": 100,
        "tabWidth": 4,
        "semi": true,
        "endOfLine": "auto"
      }
    ],
    "react/function-component-definition": [
      2,
      {
        "namedComponents": ["arrow-function", "function-declaration"],
        "unnamedComponents": "arrow-function"
      }
    ]
  }
}

```

<br/>

- Create  `.vscode>settings.json` file in project root folder and enter the bellow contents

```json
{
  "editor.defaultFormatter": "esbenp.prettier-vscode",
  "editor.formatOnSave": true,
  "[javascript]": {
    "editor.formatOnSave": false,
    "editor.defaultFormatter": null
  },
  "[javascriptreact]": {
    "editor.formatOnSave": false,
    "editor.defaultFormatter": null
  },
  "javascript.validate.enable": false,
  "editor.codeActionsOnSave": {
    "source.fixAll.eslint": true,
    "source.fixAll.tslint": true,
    "source.organizeImports": true
  },
  "eslint.alwaysShowStatus": true,
}
```
