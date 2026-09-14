# Development Guide

This document covers developer workflows, npm scripts, code styling standards, and verification commands for **DiNotes**.

---

## Workspace Setup

Follow the initialization instructions in [GETTING_STARTED.md](GETTING_STARTED.md).

```bash
git clone https://github.com/TheVicky1/DiNotes.git
cd DiNotes
npm install
```

---

## Available Scripts

In the project root, you can run:

### `npm run dev`
Starts the local Vite development server with Hot Module Replacement (HMR).
- Default URL: `http://localhost:5173`

### `npm run build`
Bundles the application for production into the `dist/` directory.
- Compiles React 19 JSX components.
- Optimizes Tailwind CSS via PostCSS.
- Code-splits heavy dependencies (`pdfjs-dist`, `mammoth`, `reactflow`).

### `npm run lint`
Runs ESLint using the Flat Config system (`eslint.config.js`).
- Enforces React Hooks rules, React Refresh constraints, and unused variable policies.

### `npm run preview`
Locally serves the built `dist/` production bundle to test production behavior.

---

## Styling Architecture

- **Tailwind CSS 3**: Configured in `tailwind.config.js` with custom color tokens (`primary`, `surface`, `surfaceBorder`, `textPrimary`, `textSecondary`).
- **Glassmorphism & Effects**: Defined in `src/index.css` (`.glass`, backdrop filters, custom scrollbars).
- **Dark Mode**: Managed via `ThemeContext.jsx` by toggling `.dark` class on `document.documentElement`.
