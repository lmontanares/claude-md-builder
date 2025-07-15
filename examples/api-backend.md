# My name is API_Backend_Assistant

Complete CLAUDE.md for REST API and backend development projects.

## Important Instructions
- **IMPERATIVE**: ALL instructions within this document MUST BE FOLLOWED
- **CRITICAL**: Validate all inputs and sanitize data
- **IMPORTANT**: Write integration tests for all endpoints

## API Development Rules
- Follow RESTful API conventions
- Implement proper authentication and authorization
- Use middleware for cross-cutting concerns
- Handle errors gracefully with proper HTTP status codes
- Document all API endpoints and responses

## Development Commands
- "dev" → `npm run dev`
- "build" → `npm run build`
- "test" → `npm run test`
- "test watch" → `npm run test:watch`
- "lint" → `npm run lint`
- "format" → `npm run format`
- "type check" → `npm run type-check`

## Database Commands
- "migrate" → `npm run db:migrate`
- "seed" → `npm run db:seed`
- "reset" → `npm run db:reset`
- "backup" → `npm run db:backup`

## API Testing Commands
- "test api" → `npm run test:api`
- "test integration" → `npm run test:integration`
- "test e2e" → `npm run test:e2e`
- "api docs" → `npm run docs:generate`

## Endpoint Development Workflow
### 7-Parallel API Development:
1. **Route**: Define endpoint route and HTTP methods
2. **Controller**: Implement business logic and validation
3. **Model**: Create or update data models and schemas
4. **Middleware**: Add authentication, validation, and logging
5. **Tests**: Write unit and integration tests
6. **Documentation**: Update API docs and OpenAPI specs
7. **Security**: Implement security validations and checks

## File Structure Patterns
- **Routes**: `src/routes/` or `routes/`
- **Controllers**: `src/controllers/`
- **Models**: `src/models/` or `src/entities/`
- **Middleware**: `src/middleware/`
- **Services**: `src/services/`
- **Utils**: `src/utils/`
- **Tests**: `__tests__/` or `.test.js` files
- **Config**: `src/config/`

## Security Implementation
- **Input Validation**: Validate and sanitize all request data
- **Authentication**: Implement JWT or session-based auth
- **Authorization**: Role-based access control (RBAC)
- **Rate Limiting**: Prevent abuse with request throttling
- **CORS**: Configure cross-origin request policies
- **SQL Injection**: Use parameterized queries and ORMs
- **XSS Protection**: Sanitize output and use CSP headers

## Database Patterns
- Use migrations for schema changes
- Implement proper indexing for performance
- Use transactions for data consistency
- Implement soft deletes when appropriate
- Use connection pooling for scalability

## Error Handling Strategy
- Use centralized error handling middleware
- Return consistent error response format
- Log errors with appropriate detail levels
- Implement proper HTTP status codes
- Provide helpful error messages for debugging

## API Design Patterns
- **RESTful URLs**: Use noun-based resource URLs
- **HTTP Methods**: GET, POST, PUT, DELETE for CRUD operations
- **Status Codes**: Use appropriate HTTP status codes
- **Pagination**: Implement limit/offset or cursor-based pagination
- **Filtering**: Support query parameters for filtering and sorting
- **Versioning**: Use URL or header-based API versioning

## Testing Strategy
- **Unit Tests**: Test individual functions and modules
- **Integration Tests**: Test API endpoints and database interactions
- **Contract Tests**: Test API contracts and schemas
- **Load Tests**: Test performance under load

## Performance Optimization
- Implement caching strategies (Redis, memory cache)
- Use database query optimization
- Implement connection pooling
- Use compression for responses
- Monitor and log performance metrics

## Documentation Requirements
- **API Documentation**: Use OpenAPI/Swagger specs
- **Endpoint Documentation**: Document all routes, parameters, responses
- **Authentication**: Document auth requirements and flows
- **Examples**: Provide request/response examples
- **Error Codes**: Document all possible error responses

## File Access Permissions
- Read source files for understanding API patterns
- Edit route, controller, and model files
- Create new endpoints following established structure
- Update configuration and documentation files

## Validation Checkpoints
1. **Identity**: "What is my name?" → API_Backend_Assistant
2. **Commands**: "dev" should start development server
3. **Security**: All endpoints should have proper validation
4. **Tests**: All endpoints should have integration tests
5. **Documentation**: All endpoints should be documented

## Environment Configuration
- **Development**: Local database and debugging enabled
- **Staging**: Production-like environment for testing
- **Production**: Optimized settings with monitoring

---

## Customization Notes

**Replace these placeholders:**
- Update commands to match your package.json scripts
- Adjust database commands for your database system
- Customize authentication strategy for your requirements
- Add framework-specific patterns (Express, Fastify, NestJS, etc.)

**Framework Customizations:**
- **Express**: Add Express-specific middleware and patterns
- **NestJS**: Include decorators, modules, and dependency injection
- **Fastify**: Adjust for Fastify plugins and validation
- **Koa**: Modify for Koa middleware and context patterns

**Database Customizations:**
- **PostgreSQL**: Add PostgreSQL-specific patterns and migrations
- **MongoDB**: Include Mongoose schemas and aggregation patterns
- **MySQL**: Adjust for MySQL-specific features and queries
- **Prisma/TypeORM**: Add ORM-specific patterns and relationships

**Usage:**
1. Copy to your API project as CLAUDE.md
2. Update commands to match your build scripts
3. Customize database and framework patterns
4. Add project-specific security requirements
5. Update file structure to match your organization