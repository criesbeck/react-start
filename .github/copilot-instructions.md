# CS394 Agile Software Engineering — Copilot Instructions

This is a React + TypeScript web application built with Vite, using Firebase for backend
services. The tech stack and conventions below are required for all code in this repo.

---

## Tech Stack

Use the latest versions of all dependencies unless a specific version is listed

- **Framework**: React with React Compiler enabled
- **Language**: TypeScript 6 (strict mode), ESLint 9, Prettier
- **Build**: Vite
- **Styling**: Tailwind CSS
- **Testing**: Vitest + React Testing Library
- **Backend**: Firebase Hosting, Authentication, Firestore

---

## Code Style

Formatting and linting are enforced by Prettier and ESLint — always ensure code passes
both before considering any task complete. Do not add inline style overrides.

Additional conventions:
- Use `const` by default; `let` only when reassignment is required
- Prefer async/await over promise chains
- Handle errors where meaningful recovery, user feedback, or logging occurs
- Avoid pass-through try/catch blocks that only rethrow errors- Use arrow functions for components and callbacks
- Use named exports for all components and utilities
- Colocate types with the code that owns them unless shared broadly
- Extract shared domain types into /src/types
- Prefer interface for extensible object shapes and type aliases for unions, mapped types, and utility types

---

## React Patterns

- All components are functional components using React hooks
- Export one primary component per file
- Small implementation details may remain in the same file if not reused elsewhere
- Lift state only as far as necessary
- Use React Context for app-wide concerns such as authentication, theme, or user preferences
- Prefer local component state when possible
- Use `PropsWithChildren` when a component accepts children
- Keep components small and focused on a single responsibility
- Prefer React patterns that are compatible with the configured compiler
- Avoid unnecessary memoization unless profiling demonstrates a need

---

## Data Fetching

- All backend access must occur through service modules
- Keep service functions independent of React
- Components display data; services retrieve data
- Prefer custom hooks for reusable data-fetching logic
- Handle loading, empty, and error states explicitly

---

## Error Handling

- Service layer returns typed results or throws typed errors
- Components never swallow errors
- Surface user-facing failures through consistent UI patterns
- Log unexpected failures in one place

---

## Accessibility

- Use semantic HTML whenever possible
- All interactive controls must be keyboard accessible
- Form elements require associated labels
- Images require meaningful alt text unless purely decorative
- Prefer accessible React Testing Library queries

---

## Project Structure
```
/src
  /components    # React components, one per file
  /hooks         # Custom React hooks
  /services      # Firebase and external API calls (never in components)
  /types         # TypeScript types and interfaces
  /utilities     # Shared pure functions and helpers
/docs            # API specs, user guides, architecture notes
```

All Firebase and network calls go in `/src/services/`. Components must not import
Firebase SDK directly.

---

## Firebase

- Use **Cloud Firestore** for persistent data storage
- Use **Firebase Authentication** with Google Sign-In for user auth
- Wrap Firestore calls in service modules with typed return values
- Handle loading and error states explicitly in any component that fetches data

---

## Testing

- Test files live alongside the component or module they test (`*.test.tsx` / `*.test.ts`)
- Use React Testing Library; query by role, label, or text — not by test ID unless necessary
- Mock all Firebase and network calls with `vi.mock()`
- Import all functions and types explicitly by name in test files
- Tests must pass before any task is considered complete
- Test behavior, not implementation details
- Avoid testing internal state
- Prefer user-centric interactions
- Mock network boundaries only
- Keep tests deterministic

---

## What to Avoid

- Do not use class components
- Do not call Firebase SDK directly inside React components
- Do not use `any` as a TypeScript type
- Do not use `useEffect` for data that can be derived from existing state
- Do not duplicate logic that belongs in a shared utility or hook

---
## Copilot Guidance

When generating code:
- Follow existing patterns before introducing new ones
- Prefer modifying existing files over creating new abstractions
- Do not introduce new dependencies unless explicitly requested
- Explain architectural changes before making them
- Keep solutions consistent with the current project structure
- Generate the minimum change necessary to satisfy requirements
