# Project Context

## Purpose
Petsgram API is a backend service built with NestJS to provide RESTful API endpoints for a pet social media application. The API handles core functionalities for pet profiles, posts, and social interactions.

## Tech Stack
- **Framework**: NestJS v11 (Node.js framework)
- **Language**: TypeScript 5.7
- **Runtime**: Node.js (ES2023 target)
- **Package Manager**: npm
- **Testing**: Jest (unit tests) + Supertest (e2e tests)
- **Code Quality**: ESLint + Prettier
- **Architecture**: Module-based (NestJS modules pattern)

## Project Conventions

### Code Style
- **Formatting**: Prettier with auto end-of-line
- **Linting**: ESLint with TypeScript ESLint plugin and recommended type-checked rules
- **Naming Conventions**:
  - Classes: PascalCase (e.g., `AppController`, `AppService`)
  - Files: kebab-case (e.g., `app.controller.ts`, `app.service.ts`)
  - Decorators: PascalCase from NestJS (e.g., `@Module`, `@Controller`)
- **Module Resolution**: Node16/NodeNext with package.json exports resolution
- **Decorators**: Enabled with `experimentalDecorators` and `emitDecoratorMetadata`
- **Type Safety**: Partial strict mode (strict null checks enabled, but `noImplicitAny` is off)

### Architecture Patterns
- **Modular Architecture**: NestJS module-based organization
- **Dependency Injection**: Built-in NestJS DI container
- **Controller-Service Pattern**: Controllers handle HTTP requests, services contain business logic
- **Decorators**: Heavy use of TypeScript decorators for metadata and dependency injection
- **File Structure**:
  - Source code in `src/`
  - Tests colocated with source (`.spec.ts` files)
  - E2E tests in `test/` directory
  - Build output in `dist/`

### Testing Strategy
- **Unit Tests**: Jest with ts-jest transformer
- **Test Location**: Colocated with source files (`.spec.ts`)
- **E2E Tests**: Separate `test/` directory with `jest-e2e.json` config
- **Coverage**: Available via `npm run test:cov`
- **Test Commands**:
  - `npm test` - Run unit tests
  - `npm run test:watch` - Watch mode
  - `npm run test:e2e` - End-to-end tests
  - `npm run test:debug` - Debug mode

### Git Workflow
- **Branching**: (To be defined based on team workflow)
- **Commit Conventions**: (To be defined - consider Conventional Commits)
- **Code Review**: (To be defined)

## Domain Context
This is a pet-focused social media platform API where:
- Users can create profiles for their pets
- Pets can have posts with photos and updates
- Social interactions include likes, comments, and follows
- The "gram" suffix indicates Instagram-like functionality for pets

## Important Constraints
- **TypeScript Configuration**: Uses `nodenext` module resolution
- **Loose Type Checking**: `noImplicitAny` is disabled - prefer fixing this gradually
- **Port Configuration**: Defaults to port 3000, configurable via `PORT` environment variable
- **Build Output**: Compiled to `dist/` directory
- **Node Environment**: Designed for Node.js runtime with CommonJS compatibility

## External Dependencies
Currently minimal external dependencies:
- **Core NestJS**: @nestjs/common, @nestjs/core, @nestjs/platform-express
- **RxJS**: For reactive programming support
- **Express**: Default HTTP platform adapter
- **Reflect Metadata**: For decorator metadata reflection

Future considerations:
- Database ORM (TypeORM, Prisma, or Mongoose)
- Authentication/Authorization (Passport.js, JWT)
- File upload handling (for pet photos)
- Validation library (@nestjs/class-validator)
- API documentation (Swagger/OpenAPI)
