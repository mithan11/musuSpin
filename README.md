# LuckySpin – Random Picker Wheel

React + TypeScript + Tailwind CSS (v4) + Vite. Fully client-side, no backend.

## Run

```bash
npm install
npm run dev        # http://localhost:5173
npm run build      # type-check + production build into dist/
npm test           # wheel-math unit tests
```

## Customize

- Brand name / limits / storage keys / default options: `src/config.ts`
- Theme colors and fonts: `@theme` block at the top of `src/index.css`
- Quick Ideas presets: `src/lib/presets.ts`
- SEO copy: `src/components/SeoSections.tsx` and `index.html`

## How the wheel stays honest

`src/lib/wheel.ts` – the wheel lands on a uniformly random final angle. The winner is
then *read from that angle* (`winnerIndex`), never chosen separately, so the pointer
and the result cannot disagree. Unit tests verify this geometrically.

## Storage (localStorage)

`luckyspin.current.v1`, `luckyspin.saved.v1`, `luckyspin.history.v1`, `luckyspin.prefs.v1`
