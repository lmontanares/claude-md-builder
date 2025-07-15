# My name is WebApp_Frontend_Assistant

Complete CLAUDE.md for React/Vue/Angular web development projects.

## Important Instructions
- **IMPERATIVE**: ALL instructions within this document MUST BE FOLLOWED
- **CRITICAL**: Follow React/Vue/Angular best practices
- **IMPORTANT**: Write component tests for all new components

## Web Development Rules
- Use TypeScript for type safety
- Follow component-based architecture
- Implement responsive design patterns
- Write accessible HTML and ARIA attributes
- Optimize for performance and SEO

## Development Commands
- "dev" → `npm run dev`
- "build" → `npm run build`
- "test" → `npm run test`
- "test watch" → `npm run test:watch`
- "lint" → `npm run lint`
- "format" → `npm run format`
- "type check" → `npm run type-check`

## Deployment Commands
- "build prod" → `npm run build:prod`
- "preview" → `npm run preview`
- "deploy staging" → `npm run deploy:staging`
- "deploy prod" → `npm run deploy:prod`

## Component Development Workflow
### 6-Parallel Component Creation:
1. **Component**: Create main component file with props and state
2. **Styles**: Create component-specific CSS/SCSS styles
3. **Tests**: Write comprehensive component tests
4. **Types**: Define TypeScript interfaces and prop types
5. **Stories**: Create Storybook stories for documentation
6. **Integration**: Add to app routing and component exports

## File Structure Patterns
- **Components**: `src/components/[ComponentName]/`
- **Pages**: `src/pages/` or `src/views/`
- **Hooks**: `src/hooks/`
- **Utils**: `src/utils/`
- **Types**: `src/types/` or `src/@types/`
- **Styles**: `src/styles/` or component-level CSS
- **Tests**: `__tests__/` or `.test.tsx` files

## Code Quality Standards
- Use ESLint with React/Vue/Angular rules
- Format code with Prettier
- Maintain 80%+ test coverage
- Use semantic HTML elements
- Follow accessibility guidelines (WCAG)

## Component Patterns
- Use functional components with hooks
- Implement proper prop validation
- Follow component composition patterns
- Use custom hooks for shared logic
- Implement proper error boundaries

## State Management Rules
- Use local state for component-specific data
- Use context for shared state across components
- Use Redux/Vuex/NgRx for complex global state
- Avoid prop drilling with proper state architecture

## Performance Optimization
- Implement code splitting and lazy loading
- Use React.memo/Vue computed/Angular OnPush for optimization
- Optimize images and assets
- Implement proper caching strategies
- Monitor bundle size and performance metrics

## Testing Strategy
- **Unit Tests**: Test individual components and functions
- **Integration Tests**: Test component interactions
- **E2E Tests**: Test complete user workflows
- **Visual Tests**: Use Storybook for visual regression testing

## File Access Permissions
- Read any source files for understanding patterns
- Edit component, style, and test files
- Create new components following established structure
- Update routing and configuration files as needed

## Validation Checkpoints
1. **Identity**: "What is my name?" → WebApp_Frontend_Assistant
2. **Commands**: "dev" should start development server
3. **Patterns**: New components should follow established structure
4. **Tests**: All new components should have corresponding tests

---

## Customization Notes

**Replace these placeholders:**
- `WebApp` → Your actual project name
- Update commands to match your package.json scripts
- Adjust framework-specific patterns (React/Vue/Angular)
- Add project-specific component libraries or tools

**Framework Customizations:**
- **React**: Update for React patterns, hooks, and testing
- **Vue**: Adjust for Vue composition API and testing patterns
- **Angular**: Modify for Angular services, modules, and testing

**Usage:**
1. Copy to your project as CLAUDE.md
2. Replace "WebApp" with your project name
3. Update commands to match your build scripts
4. Customize framework-specific patterns
5. Add project-specific component library rules