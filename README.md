# @deepsickdev/core

[![npm version](https://img.shields.io/npm/v/@deepsickdev/core?style=flat-square)](https://www.npmjs.com/package/@deepsickdev/core)
[![license](https://img.shields.io/npm/l/@deepsickdev/core?style=flat-square)](https://www.npmjs.com/package/@deepsickdev/core)

Shared configuration, utilities, and setup packages for `@deepsickdev` projects.

Currently, this package exposes a standardized, opinionated **Biome** configuration to ensure code consistency across projects.

---

## ✨ Features

- **Shared Biome config**: Reusable configuration for linting and formatting.
- **Consistent formatting**: Centralized rules (e.g., indentation, line endings, attribute positioning).
- **Easy updates**: Update rules once and roll them out everywhere.

---

## 📦 Installation

Biome is a peer dependency, so install both the config package and Biome itself.

### npm

```bash
npm install -D @deepsickdev/core @biomejs/biome
```

### Yarn

```bash
yarn add -D @deepsickdev/core @biomejs/biome
```

### pnpm

```bash
pnpm add -D @deepsickdev/core @biomejs/biome
```

---

## 🚀 Usage

### 1) Configure Biome

Create or update `biome.json` in the root of your project:

```json
{
  "$schema": "https://biomejs.dev/schemas/1.9.0/schema.json",
  "extends": ["@deepsickdev/core/biome"]
}
```

You can still override specific rules in your project's `biome.json` if needed.

### 2) Add scripts (optional)

Add scripts to your project's `package.json`:

```json
{
  "scripts": {
    "lint": "biome check .",
    "format": "biome format . --write",
    "check": "biome check . --write"
  }
}
```

## 🛠️ Development & Release

This package is published via GitHub Actions on tag push (`v*`).

### Release commands

```bash
npm run release:patch
npm run release:minor
npm run release:major
```

Push tags:

```bash
git push --follow-tags
```

---

## License

ISC