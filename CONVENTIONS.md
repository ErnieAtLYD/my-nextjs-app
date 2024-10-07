# Conventions for Next.js Project

This document outlines the conventions to follow when developing with Next.js in this project. Adhering to these guidelines will help maintain consistency and improve collaboration among team members.

## Project Structure

/project-root
|-- /public # Static files like images and icons
|-- /src # Main source code
| |-- /components # Reusable React components
| |-- /pages # Next.js pages
| |-- /styles # Global styles and component-specific styles
| |-- /hooks # Custom hooks  
| |-- /utils # Utility functions
| |-- /contexts # React contexts
| |-- /services # API services
| -- /tests # Tests
|-- /tests # End-to-end tests and other test configurations
|-- /types # TypeScript types (if using TypeScript)
|-- .env # Environment variables
|-- next.config.js # Next.js configuration
|-- package.json # Project dependencies and scripts
-- README.md # Project overview and setup instructions

# Conventions for Next.js TypeScript Project

This document outlines the conventions to follow when developing with Next.js and TypeScript in this project. Adhering to these guidelines will help maintain consistency and improve collaboration among team members.

## Project Structure

/project-root |-- /public # Static files like images and icons |-- /src # Main source code | |-- /components # Reusable React components | |-- /pages # Next.js pages | |-- /styles # Global styles and component-specific styles | |-- /hooks # Custom hooks | |-- /utils # Utility functions | |-- /contexts # React contexts | |-- /services # API services | |-- /types # TypeScript types and interfaces | -- /tests # Tests |-- /tests # End-to-end tests and other test configurations |-- .env # Environment variables |-- next-env.d.ts # Next.js environment types |-- next.config.js # Next.js configuration |-- tsconfig.json # TypeScript configuration |-- package.json # Project dependencies and scripts -- README.md # Project overview and setup instructions

## Naming Conventions

### File and Folder Names

- Use `PascalCase` for components and hooks (e.g., `MyComponent.tsx`, `useCustomHook.ts`).
- Use `kebab-case` for directories (e.g., `my-directory`).
- Keep file names descriptive and relevant to their content.

### Components

- Component files should be named after the component (e.g., `Button.tsx` for a Button component).
- Each component should reside in its own folder, with styles and tests located there as well.

/src/components/Button/ |-- Button.tsx |-- Button.module.css `-- Button.test.tsx

### Pages

- Each page file should correspond to a route and be named using `kebab-case` (e.g., `about.js` for the `/about` route).
- Use dynamic routes for pages that need them (e.g., `[id].js` for a dynamic item).

## Coding Style

### Pages

- Each page file should correspond to a route and be named using `kebab-case` (e.g., `about.tsx` for the `/about` route).
- Use dynamic routes for pages that need them (e.g., `[id].tsx` for a dynamic item).

## TypeScript Conventions

### Types and Interfaces

- Define types and interfaces in the `/types` directory.
- Use `interface` for objects and `type` for union types or function signatures.
- Prefer explicit typing over `any` and avoid using `unknown` unless necessary.

### Props and State

- Always type props and state in components:

  ```tsx
  interface ButtonProps {
    label: string
    onClick: () => void
  }

  const Button: React.FC<ButtonProps> = ({ label, onClick }) => {
    return <button onClick={onClick}>{label}</button>
  }
  ```

### JavaScript/TypeScript

- Follow the [Airbnb JavaScript Style Guide](https://github.com/airbnb/javascript) or configure ESLint to enforce style.
- Use `const` and `let` instead of `var`.
- Prefer arrow functions for functional components.

### JSX

- Use self-closing tags for empty elements.
- Keep JSX indentation consistent (2 spaces).
- Use destructuring for props in components.

## State Management

- Use React’s built-in state and context for local state management.
- For more complex state, consider using libraries like Zustand or Recoil.

## API Calls

- Organize API calls in the `/services` directory.
- Use `async/await` for handling asynchronous operations.
- Keep API endpoints in a single configuration file or service.

## Testing

- Use Jest and React Testing Library for unit and integration tests.
- Organize tests alongside the components they test, following the naming convention mentioned above.

## Environment Variables

- Define environment variables in the `.env` file.
- Use `NEXT_PUBLIC_` prefix for variables that need to be exposed to the browser.

## Documentation

- Document complex components, hooks, and utilities with comments.
- Maintain a `README.md` with setup instructions and project details.

## Git Conventions

- Use meaningful commit messages, following the format: `type(scope): subject`.
- Types: `feat`, `fix`, `docs`, `style`, `refactor`, `test`, `chore`.

## Branching Strategy

- Use `main` for production-ready code.
- Use feature branches prefixed with `feature/` for new features and `bugfix/` for bug fixes.
