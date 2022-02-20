# Meshtastic Web Config

[![Open in Visual Studio Code](https://open.vscode.dev/badges/open-in-vscode.svg)](https://open.vscode.dev/meshtastic/web-config) ![NPM](https://badgen.net/npm/v/@meshtastic/eslint-config) ![Downloads](https://badgen.net/npm/dt/@meshtastic/eslint-config) [![CI](https://github.com/meshtastic/web-config/actions/workflows/ci.yml/badge.svg)](https://github.com/meshtastic/web-config/actions/workflows/ci.yml)

## Overview

This package includes configurations for [ESLint](https://eslint.org/) and [Prettier](https://prettier.io/) used by [Meshtastic](https://meshtastic.org) for there JavaScript/TypeScript projects.

## Installation & Usage

The library is available from [NPM](https://www.npmjs.com/package/@meshtastic/eslint-config) and can be installed with:

```bash
pnpm add @meshtastic/eslint-config
```

Create ESLint and Prettier configuration files in your project root directory with the following content:

```js
// .eslintrc.cjs

/** @type {import("eslint").Linter.Config} */
module.exports = {
  extends: '@meshtastic/eslint-config',
  parserOptions: {
    tsconfigRootDir: __dirname,
    project: ['./tsconfig.json'],
  },
};
```

```js
// .prettierrc

"@meshtastic/eslint-config/prettier"
```

It is recommended to setup linting as a requirement before comitting:

```json
// package.json

"scripts": {
  "format": "prettier --write 'src/**/*.{ts,tsx}' && eslint src/*.{ts,tsx}"
},
"pre-commit": [
  "format"
],
```
