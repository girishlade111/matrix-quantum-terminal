# Matrix Quantum Terminal

A Matrix-themed interactive terminal UI that simulates a quantum computing console. Type commands, watch a Matrix-style digital rain effect, and visualize quantum states and circuits — all rendered in a neon-green cyber aesthetic.

## What it does

- **Interactive quantum terminal** — a fake-but-fun command-line interface with commands like `help`, `matrix`, `quantum`, `run`, `clear`, and `exit`
- **Matrix rain effect** — canvas-based falling glyph animation toggled from the terminal
- **Quantum circuit visualization** — animated circuit diagram showing gates and qubit states (|0⟩, |1⟩, |+⟩, |-⟩, Bell states)
- **Simulated quantum operations** — "run" executes a fake quantum job with loading animation and state output
- Fully client-side; no backend, no API keys, no data leaves the browser

## Features

- Retro terminal UI with blinking cursor, command history, and syntax-styled output
- Matrix digital-rain canvas overlay
- Quantum circuit SVG/canvas visualization with animated gates
- shadcn/ui components (Radix) for polished dialogs and controls
- Dark-mode friendly; responsive layout
- Static-site friendly — builds to plain HTML/CSS/JS (`output: 'export'`)

## Tech stack

- **Next.js 15** (App Router, static export)
- **React 19**, **TypeScript 5**
- **Tailwind CSS 3** + `tailwindcss-animate`
- **shadcn/ui** (Radix primitives), `lucide-react` icons
- **Recharts** (visualization helper)
- pnpm (lockfile included; npm works too)

## Quick start

```bash
# install dependencies
npm install          # or: pnpm install

# run the dev server
npm run dev          # open http://localhost:3000

# production build (static export to ./out)
npm run build
```

Serve the static export with any static host:

```bash
npx serve out
```

## Project structure

```
app/                 # Next.js App Router (layout, page, global styles)
components/
  quantum-terminal.tsx   # main terminal component + command engine
  matrix-rain.tsx        # Matrix digital-rain canvas effect
  quantum-circuit.tsx    # quantum circuit visualization
  theme-provider.tsx     # next-themes provider
  ui/                    # shadcn/ui primitives (button, etc.)
lib/utils.ts         # cn() class helper
public/              # static assets
styles/              # additional styles
next.config.mjs      # output: 'export', unoptimized images
```

## Environment variables

None — the app is 100% client-side and needs no secrets.

## Deployment notes

- The app is statically exported (`out/`), so it can be hosted on **GitHub Pages**, **Vercel**, **Netlify**, or any static file host.
- `next.config.mjs` sets `basePath: '/matrix-quantum-terminal'` for the GitHub Pages subpath deployment. If you deploy to a domain root (Vercel/custom domain), remove the `basePath` line and rebuild.

## Commands reference

| Command   | Effect                                      |
| --------- | ------------------------------------------- |
| `help`    | list available commands                     |
| `matrix`  | toggle the Matrix digital-rain overlay       |
| `quantum` | show the quantum circuit visualization      |
| `run`     | simulate a quantum job with loading sequence|
| `clear`   | clear the terminal                          |
| `exit`    | show the exit message                       |

---

Built by Girish Lade — [ladestack.in](https://ladestack.in)
