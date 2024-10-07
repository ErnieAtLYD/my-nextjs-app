# Next.js 14 Template with TypeScript and Tailwind CSS

This is a modern, feature-rich template for building web applications using Next.js 14, TypeScript, and Tailwind CSS. Unlike the usual code base, this project attempts to optimize a workflow where they're coding along with an LLM such as Sonnet but also adding TTD as they go along.I already went through the trouble of stabbing my eyes with a dull spoon dealing with jest working with TypeScript (as a newbie)

It includes a variety of pre-configured tools and best practices to help you get started quickly and efficiently.

## Features

- **Next.js 14**: Utilizing the latest features including the App Router and Server Components
- **TypeScript**: For type-safe code and improved developer experience
- **Tailwind CSS**: For rapid and responsive UI development
- **ESLint**: Configured for Next.js and TypeScript projects
- **Prettier**: For consistent code formatting
- **Jest**: Set up for unit and integration testing
- **React Testing Library**: For component testing
- **Husky**: For pre-commit hooks
- **lint-staged**: To run linters on git staged files
- **pnpm**: Fast, disk space efficient package manager
- **biome**: Versatile code formatting, linting, and analysis tool

## Package Management with pnpm

This project uses pnpm as the package manager. pnpm is faster and more efficient than npm or Yarn, offering better disk space usage and improved monorepo support.

To use pnpm:

1. Install pnpm globally (if not already installed):

   ```
   npm install -g pnpm
   ```

2. Install dependencies:

   ```
   pnpm install
   ```

3. Add new packages:

   ```
   pnpm add [package-name]
   ```

4. Run scripts:
   ```
   pnpm run [script-name]
   ```

Note: Make sure to use `pnpm` instead of `npm` or `yarn` for all package management tasks in this project.

## Getting Started

1. Clone the repository:

   ```
   git clone https://github.com/ErnieAtLYD/my-nextjs-app.git
   ```

2. Install dependencies:

   ```
   pnpm install
   ```

3. Run the development server:

   ```
   pnpm run dev
   ```

4. Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

## Scripts

- `pnpm run dev`: Starts the development server
- `pnpm run build`: Builds the app for production
- `pnpm start`: Runs the built app in production mode
- `pnpm run lint`: Runs ESLint
- `pnpm run format`: Formats code with Prettier
- `pnpm run test`: Runs Jest tests

## Project Structure

- `app/`: Contains the application routes and pages
- `components/`: Reusable React components
- `lib/`: Utility functions and custom hooks
- `public/`: Static assets
- `styles/`: Global styles and Tailwind CSS configuration
- `__tests__/`: Test files

## Best Practices

- Use Server Components by default, and Client Components when necessary
- Implement efficient data fetching using server components and the `fetch` API
- Utilize Next.js Image component for optimized image loading
- Employ proper SEO practices using Next.js built-in metadata API
- Follow accessibility guidelines and use semantic HTML

## Testing and Test-Driven Development (TDD)

This template comes with Jest and React Testing Library pre-configured, allowing you to start writing tests immediately. We encourage the use of Test-Driven Development (TDD) to ensure code quality and maintainability.

### Running Tests

Tests should work out of the box. To run your tests:

```
pnpm run test
```

### TDD Best Practices with Next.js, TypeScript, and React Testing Library

1. **Write tests first**: Before implementing a feature, write a failing test that describes the expected behavior.

2. **Keep tests simple and focused**: Each test should verify a single piece of functionality.

3. **Use descriptive test names**: Your test names should clearly describe what is being tested.

4. **Leverage TypeScript**: Use TypeScript to ensure type safety in your tests and implementation.

5. **Test components in isolation**: Use React Testing Library to test components in isolation, focusing on user interactions and rendered output.

6. **Mock external dependencies**: Use Jest's mocking capabilities to isolate the code being tested.

7. **Test both Server and Client Components**: Ensure you're testing both Server and Client Components appropriately.

8. **Use `@testing-library/user-event`**: For testing user interactions, prefer `@testing-library/user-event` over `fireEvent` for more realistic event simulation.

9. **Implement accessibility testing**: Use `@testing-library/jest-dom` for additional DOM assertions, including accessibility checks.

10. **Organize tests alongside source code**: Keep test files close to the components or functions they're testing for easier maintenance.

Example test structure:

```typescript:
import { render, screen } from '@testing-library/react'
import userEvent from '@testing-library/user-event'
import Button from '@/components/Button'

describe('Button', () => {
   it('renders with correct text', () => {
      render(<Button>Click me</Button>)
      expect(screen.getByRole('button', { name: /click me/i })).toBeInTheDocument()
   })
   it('calls onClick when clicked', async () => {
      const handleClick = jest.fn()
      render(<Button onClick={handleClick}>Click me</Button>)
      await userEvent.click(screen.getByRole('button', { name: /click me/i }))
      expect(handleClick).toHaveBeenCalledTimes(1)
   })
})
```

Remember to adjust your testing approach based on whether you're testing Server or Client Components, as they have different constraints and capabilities in Next.js 14.

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details.
