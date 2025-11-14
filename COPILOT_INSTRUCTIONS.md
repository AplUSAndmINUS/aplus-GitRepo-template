# COPILOT_INSTRUCTIONS.md

## Purpose

This repository follows strict development, architectural, and coding guidelines for maintainability, consistency, and scalability.

---

## General Development Guidelines

### Package Management

- **Use the `yarn` package manager exclusively** for all dependency management and scripts
  - Do not use `npm` for installs, scripts, or lockfiles
  - Current Node.js requirement: **>= 20.0.0** (specified in `package.json`)
  - Ensure all packages are kept up to date with security patches and compatibility
  - If a version upgrade is required for any packages, do so under a separate feature branch request for full testing

### Node & Environment

- The project uses **Node.js >= 20.0.0**
- `.nvmrc` file should be maintained if Node version needs to be pinned for consistency
- Environment variables should be configured appropriately (`.env.local`, `.env.example`)
- Development server: `yarn start`
- Production build: `yarn build`

### Styling Architecture

- **Prefer Tailwind CSS for component styling** over SCSS modules
  - Use utility-first approach for faster development and better maintainability
  - Leverage Tailwind's design system for consistent spacing, colors, and typography
  - Only use SCSS modules (`*.module.scss`) when Tailwind cannot achieve the desired result
- **SCSS modules as fallback**:
  - Maintain consistent naming conventions and organization
  - Avoid excessive nesting and minimize the use of `!important`
  - Auto-generated SCSS type definitions (`*.module.scss.d.ts`) should be ignored in git
  - Follow BEM naming conventions for CSS classes
  - Use CSS custom properties for dynamic values

### Component Architecture

- **Favor reusing existing components** and maintain consistency across the codebase
- **Do not alter underlying design and layout patterns unless approved**
- Use component generators when available: `yarn generate:component ComponentName`
- Follow established component organization and naming conventions

### State & Data Handling

- **Use consistent state management patterns** throughout the application
- Organize state stores logically in dedicated directories
- Provide **mock data with complete schema** for new features to aid development
- Document data shapes and API integration requirements clearly
- Separate concerns between local component state and global application state

### Content Management

- Organize content systematically using established patterns
- **Use relative URLs for internal routes** and maintain consistent routing structure
- Static content should be organized in appropriate directories
- Dynamic content should follow established loading and rendering patterns

### API Integration

- **Include complete schemas and payload shapes** for all API interactions
- Use environment variables for all configuration:
  - API base URLs and endpoints
  - Authentication keys and tokens
  - Environment-specific settings
- Follow consistent error handling and data transformation patterns
- Mock APIs should follow production-compatible standards

---

## Coding Best Practices

### TypeScript

- Maintain **strict TypeScript typing** throughout the codebase
- No implicit `any` types - define proper interfaces and types
- Type definitions for external libraries should be kept up to date
- Use meaningful type names and organize types logically
- Leverage TypeScript's advanced features for better code safety

### Component Development

- Use **functional components and hooks** as the primary pattern
- Follow modern framework best practices
- Prefer composition over inheritance
- Keep components focused and single-responsibility
- Implement proper error boundaries and error handling

### Tailwind CSS Best Practices

- **Use utility-first approach** as the primary styling method:
  - Compose styles using Tailwind's utility classes
  - Use responsive prefixes (`sm:`, `md:`, `lg:`, `xl:`, `2xl:`) for responsive design
  - Leverage state variants (`hover:`, `focus:`, `active:`, `disabled:`) for interactions
  - Use arbitrary values sparingly: `w-[123px]` only when design system values don't suffice
- **Organize classes systematically**:
  - Group related utilities: layout → spacing → typography → colors → effects
  - Use `@apply` directive in CSS files for complex component patterns
  - Create custom components with `@layer components` for repeated patterns
- **Configuration and customization**:
  - Extend the default theme in `tailwind.config.js` for project-specific values
  - Use CSS custom properties with Tailwind for dynamic theming
  - Purge unused styles in production builds
- **Component composition**:
  - Use `clsx` or `classnames` for conditional class application
  - Create reusable class name constants for common patterns
  - Avoid overly long class strings by extracting to CSS components when necessary

### SASS/SCSS Standards (Fallback Only)

- Use SCSS only when Tailwind cannot achieve the desired styling
- Adhere to SASS coding standards when needed:
  - Use nesting appropriately (max 3 levels deep)
  - Avoid `!important` whenever possible
  - Use CSS custom properties for dynamic values
  - Follow BEM naming conventions for SCSS classes
  - Organize SCSS files with consistent structure and imports
  - Use mixins and functions for reusable styles

### Accessibility & Responsiveness

- Follow **WCAG 2.1 AA accessibility guidelines**
- Ensure keyboard navigation works throughout
- Provide appropriate ARIA labels and roles
- Test with screen readers when implementing interactive components
- Use responsive design patterns and breakpoints consistently
- Support common device sizes and orientations

### Theming & Design Consistency

- Maintain consistent theming across all components
- Support multiple theme modes (dark, light, high-contrast)
- Use design tokens and CSS custom properties for consistent styling
- Ensure all visual elements support theme switching
- Follow established design system patterns and guidelines

### Documentation

- **Document all new features, data shapes, and key logic flows**:
  - Code comments for complex logic
  - JSDoc comments for public functions and components
  - Markdown documentation for features and patterns
  - Update README.md when adding major features
- If implementing mock data, document:
  - Complete schema definition
  - Expected data structure
  - Integration points and requirements

### Technical Debt & Quality

- **Actively remove technical debt found along the way**
  - Refactor outdated patterns when encountered
  - Test functionality after cleanup to ensure nothing breaks
- **Unit testing should be included when possible**:
  - Especially for API calls, data handlers, and business logic
  - Follow established testing patterns and conventions
- Run tests with `yarn test`
- Ensure linting passes before committing

---

## Core Technologies

### Language & Type Safety

- **TypeScript 5.8+** - Type safety and developer experience
- **Yarn** - Package manager for all dependency management

### Styling & Preprocessing

- **Tailwind CSS** - Utility-first CSS framework (primary styling approach)
- **PostCSS** - CSS processing for Tailwind and custom CSS
- **Sass/SCSS** - CSS preprocessing with modules support (fallback for complex styles)
- **typed-scss-modules** - Auto-generate TypeScript definitions for SCSS modules (if needed)

### Development Tools

- **Prettier** - Code formatting and consistency
- **ESLint** - Code quality and style enforcement
- **Jest** - Testing framework
- **Concurrently** - Run multiple development scripts simultaneously

---

## Project Structure Guidelines

### Recommended Directory Organization

```
/src
├── /api              # API client layer and types
├── /assets           # Static assets (images, fonts, etc.)
├── /components       # Reusable UI components
├── /config           # Configuration files
├── /hooks            # Custom hooks
├── /pages            # Page-level components
├── /store            # State management
├── /styles           # Global styles and SCSS utilities
├── /types            # TypeScript type definitions
├── /utils            # Utility functions
└── /theme            # Theme system and design tokens
```

### Important Configuration Files

- `package.json` - Dependencies and scripts (use yarn only)
- `tsconfig.json` - TypeScript configuration
- `tailwind.config.js` - Tailwind CSS configuration and theme customization
- `postcss.config.js` - PostCSS configuration for Tailwind processing
- `.gitignore` - Excludes build artifacts, node_modules, .env files, generated types
- `.prettierrc` - Code formatting configuration (should include Tailwind class sorting)
- `.eslintrc` - Linting configuration

---

## Development Workflow

### Starting Development

```bash
yarn install          # Install dependencies
yarn start            # Start development server
```

### Building for Production

```bash
yarn build            # Create optimized production build
```

### Running Tests

```bash
yarn test             # Run test suite
```

### Style Processing

```bash
yarn build:css         # Process Tailwind CSS (if separate build step needed)
yarn scss-types        # Generate TypeScript definitions for SCSS modules (if used)
yarn scss-types:watch  # Watch mode for continuous type generation (if used)
```

---

## Issue & Pull Request Instructions

### For New Issues and PRs

1. **Reference these guidelines** - Include relevant context in issue descriptions
2. **Tag related files** - Mention specific components or utilities affected
3. **Document requirements clearly**:
   - Data schemas and API requirements
   - Component and state management needs
   - Theming and accessibility requirements
4. **Specify technical details**:
   - TypeScript interface definitions
   - SASS/SCSS styling requirements  
   - Testing expectations

### Branching Strategy

- Create feature branches from main development branch
- Use descriptive branch names: `feature/add-new-component`, `fix/styling-issue`
- Ensure all linting and build checks pass before PR
- Include tests for new features when applicable

### Code Review Checklist

- [ ] Uses yarn (not npm) for dependency management
- [ ] TypeScript types are properly defined
- [ ] Uses Tailwind CSS utility-first approach with proper class organization
- [ ] SCSS used only when necessary and follows established conventions
- [ ] Responsive design implemented correctly
- [ ] Accessibility standards met (WCAG 2.1 AA)
- [ ] Documentation updated (code comments, README if needed)
- [ ] Build passes: `yarn build`
- [ ] Tests pass: `yarn test` (if tests exist)
- [ ] No console errors or warnings in development
- [ ] Follows established code formatting (Prettier/ESLint)

---

## Best Practices Summary

- **Always use Yarn** for package management
- **Maintain strict TypeScript typing** throughout
- **Prefer Tailwind CSS** utility-first approach for styling
- **Use SCSS only as fallback** when Tailwind cannot achieve the desired result
- **Document complex logic** and provide clear interfaces
- **Test critical functionality** with comprehensive test coverage
- **Ensure accessibility compliance** in all UI components
- **Keep dependencies up to date** with regular maintenance

---

### Last Updated: 2025-11-14
