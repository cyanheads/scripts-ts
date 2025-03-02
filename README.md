# TypeScript Project Scripts

A collection of standalone, platform-agnostic TypeScript utility scripts for managing common development tasks in any project.

[![GitHub Repository](https://img.shields.io/badge/GitHub-Repository-blue)](https://github.com/cyanheads/scripts-ts)

## Features

- 🧹 **Clean Script**: Remove build artifacts and temp directories
- 🌳 **Generate Tree**: Create a markdown representation of your project structure
- 🔑 **Make Executable**: Set executable permissions for script files (chmod +x)
- 📦 **Update Dependencies**: Update package.json dependencies to latest versions

## Installation

To use these scripts in your TypeScript project:

1. Clone or download this repository
2. Add it to your project or install it as a dependency:

```bash
# From npm
npm install typescript-scripts --save-dev

# Or locally
npm install ./path/to/typescript-scripts --save-dev
```

3. Build the TypeScript scripts:

```bash
npm run build
```

## Available Scripts

### Clean Script

Removes build artifacts and temporary directories.

```bash
# Default usage (cleans dist and logs directories)
npm run clean

# Specify custom directories to clean
npm run clean temp coverage

# Or directly
node dist/clean.js temp cache
```

Features:
- Cross-platform compatibility (Windows, macOS, Linux)
- Configurable directories to clean
- Reports success or skipped directories

### Generate Tree Script

Creates a visual tree representation of your project structure.

```bash
# Default usage (outputs to docs/tree.md)
npm run tree

# Specify custom output path
npm run tree ./documentation/project-structure.md

# Limit directory depth
npm run tree --depth=3

# Get help
npm run tree --help
```

Features:
- Respects .gitignore patterns
- Automatically excludes common directories (node_modules, .git, etc.)
- Configurable depth limit
- Sorts directories first, then files

### Make Executable Script

Makes script files executable on Unix-like systems.

```bash
# Default usage (makes dist/index.js executable)
npm run make-executable

# Specify custom files
npm run make-executable dist/cli.js bin/tool.js
```

Features:
- Cross-platform compatibility (no-op on Windows)
- Handles multiple files
- Useful for CLI applications

### Update Dependencies Script

Updates package.json dependencies using npm-check-updates.

```bash
# Update all dependencies to latest versions
npm run update-deps

# Update specific packages only
npm run update-deps react react-dom

# Update to minor versions only
npm run update-deps --target=minor

# Dry run (don't actually update package.json)
npm run update-deps --dry-run
```

Features:
- Uses npm-check-updates under the hood
- Supports all npm-check-updates options
- Cross-platform compatibility

## Integration with Your Project

Add these scripts to your project's package.json:

```json
"scripts": {
  "clean": "node node_modules/typescript-scripts/dist/clean.js",
  "tree": "node node_modules/typescript-scripts/dist/generate-tree.js",
  "make-executable": "node node_modules/typescript-scripts/dist/make-executable.js",
  "update-deps": "node node_modules/typescript-scripts/dist/update-deps.js",
  "rebuild": "npm run clean && npm run build",
  "postbuild": "npm run make-executable"
}
```

## Standalone Usage

You can also use these scripts directly, without adding them to package.json:

```bash
node dist/clean.js
node dist/generate-tree.js
node dist/make-executable.js
node dist/update-deps.js
```

Or make them globally available:

```bash
npm install -g typescript-scripts
```

Then use the provided commands anywhere:

```bash
ts-clean
ts-tree
ts-make-executable
ts-update-deps
```

## Customization

Each script is designed to be self-contained and easily customizable. You can:

1. Copy individual script files into your project
2. Modify default values to match your project needs
3. Add additional functionality as required

## License

[Apache License 2.0](LICENSE)

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request