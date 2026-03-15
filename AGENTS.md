# AGENTS.md

## Cursor Cloud specific instructions

This repository is a single static HTML page (`index.html`) with no dependencies, no build step, no linting, and no automated tests.

**Serving locally:** Use Python's built-in HTTP server to view the page:
```
python3 -m http.server 8080 --directory /workspace
```
Then open `http://localhost:8080/index.html` in Chrome.

**No package manager or build tools** are required — there is no `package.json`, no bundler, and no CSS preprocessor.
