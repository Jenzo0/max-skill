# 🎨 Frontend & UI Capabilities

> Load trigger: Code/Architect mode with frontend-related request.

## Core Stack

| Framework | State | Styling |
|---|---|---|
| React (Next.js, Vite, Remix) | TanStack Query, Zustand, Redux Toolkit | Tailwind CSS v4, CSS Modules |
| Vue (Nuxt 3, Vite) | Pinia, Vue Query | UnoCSS, SCSS |
| Svelte (SvelteKit) | Svelte stores, runes | Vanilla CSS, Tailwind |
| Solid (SolidStart) | Signals, stores | Tailwind, vanilla extract |
| TypeScript | Strict mode, discriminated unions, utility types | — |

## Component Architecture

| Pattern | Use |
|---|---|
| Atomic Design | Atoms → Molecules → Organisms → Templates → Pages |
| Compound Components | `<Select>`, `<Select.Option>`, `<Select.Label>` |
| Render Props vs Hooks | Hooks preferred for logic sharing; render props for inversion of control |
| Controlled vs Uncontrolled | Controlled for form state management; uncontrolled for simple inputs |
| Error Boundaries | Per-feature error isolation with fallback UI |
| RSC (React Server Components) | Server for data fetching + initial render; Client for interactivity |

## Performance

| Technique | Tools |
|---|---|
| Code splitting | `dynamic(() => import(...))`, `React.lazy` |
| Image optimization | `next/image`, responsive `srcset`, lazy loading, WebP/AVIF |
| Bundle analysis | `webpack-bundle-analyzer`, `vite visualizer`, `source-map-explorer` |
| Memoization | `useMemo`, `useCallback`, `React.memo` — only for expensive computations |
| Virtual scrolling | `react-window`, `tanstack-virtual`, `@tanstack/react-virtual` |

## Accessibility (WCAG 2.1 AA+)

- Semantic HTML (`<nav>`, `<main>`, `<article>`, `<aside>`)
- ARIA attributes (`aria-label`, `aria-describedby`, `role`)
- Keyboard navigation (tab order, skip links, focus trapping in modals)
- Color contrast ratios (4.5:1 minimum)
- Screen reader testing (VoiceOver, NVDA, JAWS)
