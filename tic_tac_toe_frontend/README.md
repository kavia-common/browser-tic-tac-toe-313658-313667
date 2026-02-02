# Tic Tac Toe Frontend (React)

This repository contains a React frontend intended to host a browser-based Tic Tac Toe game with a 3x3 grid, two-player (X/O) turn-based gameplay, and endgame detection (win or draw).

At the moment, the checked-in UI is a lightweight React template that demonstrates theming (light/dark toggle). The sections below describe the intended Tic Tac Toe behavior for this project and how to run and configure the frontend.

## Project overview

The intended application is a simple Tic Tac Toe game playable in the browser:

A player clicks an empty square to place their mark (X then O alternating). After each move, the game detects whether a player has won (three in a row horizontally, vertically, or diagonally) or whether the game is a draw (all squares filled with no winner).

## Tech stack

The frontend is built with React (Create React App via `react-scripts`).

## Getting started

### Prerequisites

You need Node.js and npm.

### Install dependencies

From the frontend directory:

```bash
cd tic_tac_toe_frontend
npm install
```

### Run the development server (port 3000)

```bash
npm start
```

By default, Create React App serves the app on http://localhost:3000. In this project, the preview system also exposes the frontend on port 3000.

### Build for production

```bash
npm run build
```

This creates an optimized production build in the `build/` folder.

## Available scripts

The following scripts are defined in `package.json`:

### `npm start`

Runs the app in development mode via `react-scripts start` (typically on port 3000).

### `npm test`

Runs the test runner via `react-scripts test`.

### `npm run build`

Builds the app for production via `react-scripts build` into the `build/` directory.

### `npm run eject`

Ejects the Create React App configuration (one-way operation).

## Environment variables

This frontend uses Create React App conventions: only variables prefixed with `REACT_APP_` are exposed to the browser build.

The following variables are currently defined in `tic_tac_toe_frontend/.env`:

- `REACT_APP_API_BASE`: Base URL for API requests. Typically the backend HTTP origin.
- `REACT_APP_BACKEND_URL`: Backend base URL (often the same as `REACT_APP_API_BASE`).
- `REACT_APP_FRONTEND_URL`: Public URL where the frontend is served (useful for links, redirects, and absolute URL construction).
- `REACT_APP_WS_URL`: WebSocket endpoint URL (for example, `ws://.../ws`) if the frontend uses WebSockets.
- `REACT_APP_NODE_ENV`: Environment label used by the app (for example, `development`).
- `REACT_APP_NEXT_TELEMETRY_DISABLED`: Telemetry disable flag (commonly set to `1` to disable telemetry in some toolchains).
- `REACT_APP_ENABLE_SOURCE_MAPS`: Whether source maps should be enabled in builds (commonly `true`/`false`).
- `REACT_APP_PORT`: The port the frontend expects to run on (this project uses `3000`).
- `REACT_APP_TRUST_PROXY`: Whether the app should trust proxy headers when deployed behind a proxy (commonly `true`/`false`).
- `REACT_APP_LOG_LEVEL`: Logging verbosity level (for example, `info`).
- `REACT_APP_HEALTHCHECK_PATH`: Healthcheck endpoint path (for example, `/healthz`) if used by tooling or monitoring.
- `REACT_APP_FEATURE_FLAGS`: Feature flags configuration payload (currently set to `{}` in `.env`).
- `REACT_APP_EXPERIMENTS_ENABLED`: Toggle for experimental features (commonly `true`/`false`).

If you change `.env`, restart `npm start` so the development server picks up updated environment variables.

## How to play

When the Tic Tac Toe gameplay UI is present:

You play by clicking on an empty square in the 3x3 grid. Players alternate turns placing X and O. The status display indicates whose turn it is, and the game ends immediately when a player achieves three in a row or when all squares are filled (draw). Use the Reset/New Game button (if present) to start a new match.

## Preview environment note (important)

This project is run through an automated preview system that serves the frontend on port 3000. Use the provided preview URL to view the app. Do not manually start or manage preview services outside the expected workflow; `npm start` is intended for local development only.

## Styling and theme notes

The target visual style is a minimalist "Pure White" theme with:

- A clean white surface/background.
- Primary accent: `#374151`.
- Success/accent (for highlights such as winning states): `#10B981`.

The current CSS includes theme variables in `src/App.css` and a light/dark theme toggle. When implementing the Tic Tac Toe board UI, keep the layout centered with a status display above and a reset button below, and apply the Pure White palette (using `#374151` and `#10B981` as the primary accents).

## Learn more

To learn more about React, see the official documentation: https://reactjs.org/.

Create React App documentation (useful troubleshooting and production guidance):

- Code Splitting: https://facebook.github.io/create-react-app/docs/code-splitting
- Analyzing Bundle Size: https://facebook.github.io/create-react-app/docs/analyzing-the-bundle-size
- Progressive Web App: https://facebook.github.io/create-react-app/docs/making-a-progressive-web-app
- Advanced Configuration: https://facebook.github.io/create-react-app/docs/advanced-configuration
- Deployment: https://facebook.github.io/create-react-app/docs/deployment
- Build minification troubleshooting: https://facebook.github.io/create-react-app/docs/troubleshooting#npm-run-build-fails-to-minify
