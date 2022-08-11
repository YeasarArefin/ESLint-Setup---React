ESLint Setup For React

- Install `ESLint` and `Prettier` VSCcode extention.

<br/>

- Add `lint` script in `package.json`

```json
"lint": "yarn add -D prettier && yarn add -D @babel/eslint-parser && npx install-peerdeps --dev eslint-config-airbnb && yarn add -D eslint-config-prettier eslint-plugin-prettier"
```

<br/>

- Run lint script 
`$ yarn lint`

<br/>

- Create a `.eslintrc` file in the project root and enter the below contents:

```json
{
  "parser": "@babel/eslint-parser",
  "parserOptions": {
    // "parser": "@babel/eslint-parser",
    "babelOptions": {
      "parserOpts": {
        "plugins": ["jsx"]
      }
    },

    "ecmaVersion": 6,
    "sourceType": "module",
    "requireConfigFile": false,
    "ecmaFeatures": {
      "jsx": true,
      "modules": true,
      "experimentalObjectRestSpread": true
    }
  },
  "extends": [
    "airbnb",
    "airbnb/hooks",
    "eslint:recommended",
    "prettier",
    "plugin:jsx-a11y/recommended"
  ],
  "env": {
    "browser": true,
    "node": true,
    "es6": true,
    "jest": true
  },
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
  },
  "plugins": ["prettier", "react", "react-hooks"]
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
