# ESLint for React + Vite Projects

This guide provides a comprehensive setup for ESLint in a React + Vite project, ensuring code quality and adherence to best practices.

## What is ESLint?

ESLint is a popular linting tool for JavaScript and TypeScript. It helps developers find and fix problems in their code, ensuring consistency and maintainability.

## Installation

### **Prerequisites**

- Node.js and npm installed.
- A React + Vite project initialized.

### Steps to Install ESLint

1. Navigate to your project directory:
    
    ```
    cd /path/to/your/project
    
    ```
    
2. Install ESLint and related plugins:
    
    ```
    npm install eslint eslint-plugin-react eslint-plugin-react-hooks eslint-plugin-jsx-a11y @typescript-eslint/parser @typescript-eslint/eslint-plugin --save-dev
    
    ```
    

## Initial Setup

### Creating an ESLint Configuration File

1. Run the ESLint initialization command:
    
    ```
    npx eslint --init
    
    ```
    
2. Answer the prompts to customize ESLint:
    - Select "To check syntax, find problems, and enforce code style."
    - Choose the type of project: "React"
    - Select JavaScript or TypeScript accordingly.
    - Enable modules and browser environments.
    - Choose "JSON" or "YAML" for configuration file format.

### Example Configuration (`.eslintrc.json`)

```json
{
  "env": {
    "browser": true,
    "es2021": true
  },
  "extends": [
    "eslint:recommended",
    "plugin:react/recommended",
    "plugin:react-hooks/recommended",
    "plugin:jsx-a11y/recommended",
    "plugin:@typescript-eslint/recommended"
  ],
  "parser": "@typescript-eslint/parser",
  "parserOptions": {
    "ecmaVersion": 12,
    "sourceType": "module"
  },
  "plugins": ["react", "react-hooks", "jsx-a11y", "@typescript-eslint"],
  "rules": {
    "react/prop-types": "off",
    "react/react-in-jsx-scope": "off",
    "@typescript-eslint/no-unused-vars": ["warn"],
    "indent": ["error", 2],
    "quotes": ["error", "double"],
    "semi": ["error", "always"],
    "eqeqeq": ["error", "always"],
    "no-console": "warn",
    "no-debugger": "error"
  }
}

```

## Updating Files

### **Adding ESLint to `package.json`**

```json
 "scripts": {
    "dev": "vite",
    "build": "vite build",
    "serve": "vite preview",
    "lint": "eslint .",
    "lint:fix": "eslint . --fix"
  }

```

### **Ignoring Files with `.eslintignore`**

```
node_modules/
dist/
build/
.vite/

```

## Configuring Rules

### Example Rule Adjustments

- **Warning for console.log usage**
- **Enforce strict equality**
- **Require consistent indentation and semicolons**

```json
"rules": {
    "no-console": "warn",
    "no-debugger": "error",
    "indent": ["error", 2],
    "semi": ["error", "always"],
    "eqeqeq": ["error", "always"]
}

```

## Using ESLint

### Linting Files

To check your code for linting issues:

```
npm run lint

```

### Auto-fixing Issues

To automatically fix issues where possible:

```
npm run lint:fix

```

## Integrations

### VS Code Setup

1. Install the "ESLint" extension from the VS Code marketplace.
2. Enable "Auto Fix On Save" in VS Code settings:
    
    ```json
    "editor.codeActionsOnSave": {
      "source.fixAll.eslint": true
    }
    
    ```
    

### Prettier Integration

If using Prettier, install and configure `eslint-config-prettier`:

```
npm install eslint-config-prettier --save-dev

```

Add it to your `.eslintrc.json` file:

```json
"extends": [
  "eslint:recommended",
  "plugin:react/recommended",
  "prettier"
]

```

## Common Rules

| **Rule Name** | **Description** | **Level** | **Example** |
| --- | --- | --- | --- |
| `semi` | Enforce semicolons | Error | `const x = 5;` |
| `quotes` | Use consistent double quotes | Error | `const a = "hello";` |
| `eqeqeq` | Require `===` instead of `==` | Error | `if (x === 5) {}` |
| `no-console` | Warns about `console` statements | Warning | `console.log("Debug");` |
| `no-debugger` | Disallows `debugger` | Error | `debugger;` |
| `react/react-in-jsx-scope` | Not needed in Vite | Off | `import React from "react";` |
| `indent` | Enforces consistent indentation (2 spaces) | Error | `function greet() {\n  console.log("Hi!");\n}` |

For a complete list of rules, visit the [ESLint documentation](https://eslint.org/docs/rules/).

## Best Practices

- Always lint your code before committing changes.
- Use `lint:fix` to automatically resolve minor issues.
- Keep your `.eslintrc.json` file consistent across projects.
- Periodically review and update ESLint settings to align with modern best practices.

---

**Company Name:** Endless Raven

**Writer:** Pasith Senevirathna

**Position:** Backend Developer and DevOps

**Contact Email:** [pasith.senevi02@gmail.com](mailto:pasith.senevi02@gmail.com)
