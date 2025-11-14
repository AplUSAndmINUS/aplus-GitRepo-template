# Development Starter Template

A modern, production-ready development template with TypeScript, Tailwind CSS, and comprehensive tooling configuration.

## 🚀 Quick Start

```bash
# Clone this template (or use it as a GitHub template)
git clone <your-repo-url>
cd <your-project>

# Install dependencies
yarn install

# Start development server
yarn start
```

## 📋 What's Included

This template provides a complete development environment with:

- **TypeScript 5.8+** - Strict typing with modern configuration
- **Tailwind CSS** - Utility-first CSS framework for rapid UI development
- **Yarn** - Fast, reliable package management
- **Prettier** - Code formatting with custom rules
- **Git** - Optimized configuration with useful aliases
- **Development Guidelines** - Comprehensive coding standards and best practices

## 🛠 Pre-configured Files

### Core Configuration

| File | Purpose |
|------|---------|
| `tsconfig.json` | Modern TypeScript configuration with strict typing |
| `.prettierrc` | Code formatting rules with file-specific overrides |
| `.gitconfig` | Git configuration with helpful aliases and modern defaults |
| `COPILOT_INSTRUCTIONS.md` | Development guidelines and coding standards |

### Key Features

- **Modern TypeScript Setup**: ES2020 target, strict typing, enhanced type safety
- **Tailwind-First Styling**: Utility-first approach with SCSS fallback
- **Git Workflow Optimization**: Automatic rebasing, pruning, and helpful aliases
- **Code Quality**: Prettier formatting with consistent rules across file types
- **Path Mapping**: Organized imports with `@/` aliases

## 📁 Recommended Project Structure

```
/src
├── /api              # API client layer and types
├── /assets           # Static assets (images, fonts, etc.)
├── /components       # Reusable UI components
├── /config           # Configuration files
├── /hooks            # Custom hooks
├── /pages            # Page-level components
├── /store            # State management
├── /styles           # Global styles and utilities
├── /types            # TypeScript type definitions
├── /utils            # Utility functions
└── /theme            # Theme system and design tokens
```

## 🔧 Development Workflow

### Getting Started

1. **Install dependencies**: `yarn install`
2. **Start development**: `yarn start`
3. **Build for production**: `yarn build`
4. **Run tests**: `yarn test`

### Styling Approach

**Priority Order**: Tailwind CSS → SCSS Modules → Custom CSS

- Use **Tailwind utilities** for most styling needs
- Fall back to **SCSS modules** for complex components
- Follow utility-first principles and responsive design patterns

### TypeScript Standards

- **Strict typing** - No implicit `any` types
- **Proper interfaces** - Well-defined type contracts
- **Path mapping** - Use `@/` aliases for clean imports
- **Advanced features** - Leverage TypeScript's type safety features

### Git Workflow

Pre-configured aliases for efficient development:

```bash
git st          # Status with branch info
git lo          # Pretty log with graph
git cm "msg"    # Quick commit
git sw branch   # Switch branches
git last        # View last commit
```

## 📝 Code Quality Standards

### Formatting & Linting

- **Prettier** handles all code formatting automatically
- **File-specific rules** for Markdown, JSON, and YAML
- **Consistent styling** across the entire codebase
- **Pre-commit hooks** ensure quality before commits

### Testing Strategy

- **Unit tests** for business logic and utilities
- **Component tests** for UI functionality
- **Integration tests** for API interactions
- **Accessibility testing** for WCAG 2.1 AA compliance

### Documentation Requirements

- **JSDoc comments** for public functions and components
- **README updates** for new features
- **Type definitions** for all data structures
- **Code comments** for complex business logic

## 🎨 Styling Guidelines

### Tailwind CSS Best Practices

```jsx
// ✅ Good: Organized utility classes
<div className="flex items-center justify-between p-4 bg-white rounded-lg shadow-sm hover:shadow-md transition-shadow">

// ✅ Good: Responsive design
<div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-4">

// ✅ Good: Conditional classes with clsx
<button className={clsx(
  'px-4 py-2 rounded font-medium transition-colors',
  isActive ? 'bg-blue-500 text-white' : 'bg-gray-200 text-gray-700'
)}>
```

### When to Use SCSS

- Complex animations beyond Tailwind's capabilities
- Component-specific styles that would create overly long class strings
- Integration with third-party components requiring custom CSS
- Advanced CSS features not covered by Tailwind utilities

## 🔒 Environment Setup

### Required Tools

- **Node.js >= 20.0.0** - Use `.nvmrc` for version consistency
- **Yarn** - Package manager (do not use npm)
- **Git** - Version control with pre-configured aliases
- **VS Code** - Recommended editor with TypeScript support

### Environment Variables

Create `.env.local` for local development:

```env
# API Configuration
NEXT_PUBLIC_API_BASE_URL=your-api-url
NEXT_PUBLIC_CDN_BASE_URL=your-cdn-url
NEXT_PUBLIC_API_KEY=your-api-key
NEXT_PUBLIC_ENVIRONMENT=development
```

## 🚦 Branching Strategy

- **Feature branches**: `feature/add-new-component`
- **Bug fixes**: `fix/resolve-styling-issue`
- **Chores**: `chore/update-dependencies`
- **Docs**: `docs/update-readme`

### Pull Request Checklist

- [ ] Uses Yarn for dependency management
- [ ] TypeScript types properly defined
- [ ] Tailwind CSS utility-first approach
- [ ] Responsive design implemented
- [ ] Accessibility standards met (WCAG 2.1 AA)
- [ ] Documentation updated
- [ ] Tests pass: `yarn test`
- [ ] Build succeeds: `yarn build`
- [ ] No console errors in development

## 🤝 Contributing

1. Read `COPILOT_INSTRUCTIONS.md` for detailed development guidelines
2. Follow the established coding standards and patterns
3. Write tests for new functionality
4. Update documentation as needed
5. Ensure all checks pass before submitting PRs

## 📚 Additional Resources

- [TypeScript Handbook](https://www.typescriptlang.org/docs/)
- [Tailwind CSS Documentation](https://tailwindcss.com/docs)
- [Prettier Configuration](https://prettier.io/docs/en/configuration.html)
- [Git Aliases Guide](https://git-scm.com/book/en/v2/Git-Basics-Git-Aliases)

## 🐛 Troubleshooting

### Common Issues

**TypeScript errors**: Check `tsconfig.json` path mappings and type definitions

**Styling conflicts**: Ensure Tailwind classes have proper specificity over custom CSS

**Git workflow**: Use provided aliases and check `.gitconfig` for available commands

**Build failures**: Verify Node.js version matches requirements in `package.json`

---

## 📄 License

[Specify your license here]

## 🏷 Version

**Template Version**: 1.0.0  
**Last Updated**: November 14, 2025

---

**Ready to build something amazing? Start coding! 🚀**
