# doo-iconik Development Guide

This document describes the clean, repeatable way we develop and maintain this multi-framework icon library.

## Architecture

- **Core** (`packages/core`) : Single source of truth for icon data, types, and utilities.
- **Adapters** : Thin framework-specific packages (React, Vue, Svelte, etc.).
- **Generation** : Root `generate.mjs` and scripts/ for processing icons.
- **Gallery** : `docs/index.html` — zero-build interactive demo.

## Key Commands

```bash
npm install                  # Link all workspaces
npm run generate             # Regenerate icon data
npm run build                # Build core + all packages
npm test                     # Run tests
npm run build --workspace=packages/react  # Target one package
```

## The Clean Development Rhythm

1. **Identify** inconsistency or improvement.
2. **Batch** similar changes (e.g. all package.json metadata).
3. **Minimal** targeted edits.
4. **One atomic commit** with clear message.
5. **Verify** (`npm install`, `npm test`, `npm run build`).
6. **Repeat**.

## Examples of batches we have done
- Core dependency standardization
- Repository/metadata standardization
- DevDependency standardization

This approach keeps the repo clean, history readable, and ready for publishing.

## Adding Icons

Edit icon sources or data → run `npm run generate` → check complexity report and gallery.

## Publishing

Use the existing workflow by creating a GitHub release.

Happy developing!