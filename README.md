# 🛠️ TypeScript Project Scripts

<div align="center">

[![Node.js Version](https://img.shields.io/badge/node-%3E%3D%2016.0.0-brightgreen.svg)](https://nodejs.org/)
[![License](https://img.shields.io/badge/license-Apache%202.0-blue.svg)](LICENSE)
[![TypeScript](https://img.shields.io/badge/TypeScript-Ready-blue.svg)](https://www.typescriptlang.org/)
[![GitHub Repository](https://img.shields.io/badge/GitHub-Repository-24292e)](https://github.com/cyanheads/scripts-ts)

A collection of standalone, platform-agnostic TypeScript utility scripts for managing common development tasks in any project.

</div>

---

## ✨ Features

- **🧹 Clean Script** - Remove build artifacts and temp directories
- **🌳 Generate Tree** - Create a markdown representation of your project structure
- **🔑 Make Executable** - Set executable permissions for script files (chmod +x)
- **📦 Update Dependencies** - Update package.json dependencies to latest versions

All scripts are:
- 🔄 **Cross-platform** - Works on Windows, macOS, and Linux
- 🧩 **Standalone** - Each script is self-contained
- 🌐 **Project-agnostic** - Use in any TypeScript/JavaScript project
- 🛡️ **Typed** - Full TypeScript definitions and type safety

## 📥 Installation

```bash
# Install from npm
npm install scripts-ts --save-dev

# Or yarn
yarn add scripts-ts --dev

# Or pnpm
pnpm add -D scripts-ts
```

### 🔨 Build from Source

```bash
# Clone the repository
git clone https://github.com/cyanheads/scripts-ts.git

# Install dependencies
npm install

# Build the project
npm run build
```

## 📚 Usage

### Clean Script

```bash
# Default (cleans dist and logs directories)
npm run clean

# Specify custom directories
npm run clean temp coverage node_modules/.cache

# Direct usage
npx ts-clean temp cache
```

### Generate Tree Script

```bash
# Default (outputs to docs/tree.md)
npm run tree

# Custom output path
npm run tree ./documentation/project-structure.md

# Limit depth
npm run tree --depth=3

# Help
npm run tree --help
```

### Make Executable Script

```bash
# Default (makes dist/index.js executable)
npm run make-executable

# Specify files
npm run make-executable dist/cli.js bin/*.js

# Direct usage
npx ts-make-executable dist/cli.js
```

### Update Dependencies Script

```bash
# Update all dependencies
npm run update-deps

# Update specific packages
npm run update-deps react react-dom

# Update to minor versions only
npm run update-deps --target=minor

# Dry run
npm run update-deps --dry-run
```

## 🔧 Integration

Add to your project's package.json:

```json
"scripts": {
  "clean": "scripts-ts-clean",
  "tree": "scripts-ts-tree",
  "make-executable": "scripts-ts-make-executable",
  "update-deps": "scripts-ts-update-deps",
  "rebuild": "npm run clean && npm run build",
  "postbuild": "npm run make-executable"
}
```

## 🛠️ Customization

Each script is designed to be easily customizable:

1. Copy individual script files into your project
2. Modify default values to match your project needs
3. Add additional functionality as required

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the [Apache License 2.0](LICENSE).