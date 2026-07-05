# 🎨 Frontend Capabilities

> Load this module for UI/frontend development tasks.
> Load trigger: Code Mode or Architect Mode with frontend-related request.

## Core Stack
**React**: Next.js (App Router), Vite, Create React App, Remix
**Vue**: Nuxt 3, Vite, Pinia
**TypeScript**: Strict mode, generics, discriminated unions, utility types
**CSS**: Tailwind CSS v4, CSS Modules, Styled Components, PostCSS

## Component Architecture
- Atomic Design (Atoms → Molecules → Organisms → Templates → Pages)
- Compound Components pattern
- Render Props vs Hooks
- Controlled vs Uncontrolled components
- Error Boundaries + Suspense boundaries
- React Server Components (RSC) — when to use client vs server

## State Management
- **Local**: useState + useReducer (for component state)
- **Server**: TanStack Query / React Query (caching, refetching, optimistic updates)
- **Global**: Zustand (simple), Redux Toolkit (complex), Jotai (atomic)
- **URL**: next/navigation, react-router search params
- **Form**: React Hook Form + Zod validation

## Performance
- Code splitting (dynamic imports, lazy loading)
- Image optimization (next/image, responsive srcset)
- Bundle analysis (webpack-bundle-analyzer, vite visualizer)
- Memoization (useMemo, useCallback, React.memo)
- Virtual scrolling (react-window, tanstack-virtual)

## API Integration
- Fetch/Axios wrappers (interceptors, error handling, retries)
- tRPC (end-to-end typesafe APIs)
- GraphQL clients (Apollo, Urql, Relay)
- Server-Sent Events / WebSockets for real-time

## UI/UX Patterns
- Responsive design (mobile-first, container queries)
- Dark mode (CSS variables, system preference detection)
- Accessibility (WCAG 2.1 AA+, aria attributes, keyboard navigation)
- Skeleton loading, optimistic UI, optimistic updates
- Toast notifications, modals, drawers — portal-based

## Testing
- Component: React Testing Library, Vitest
- E2E: Playwright, Cypress
- Visual: Storybook + Chromatic, Percy
- A11y: axe-core, Lighthouse CI
