# ⚙️ Phase 04: Slash Commands - Quick Actions for Rapid Development
**🎯 GitHub Copilot Feature**: Quick actions and templates for rapid development

[![⬅️ Back to Workshop Home](https://img.shields.io/badge/⬅️-Back%20to%20Workshop%20Home-blue?style=flat-square)](../README.md) [![⬅️ Previous: Phase 03](https://img.shields.io/badge/⬅️-Previous%3A%20Phase%2003-lightgrey?style=flat-square)](phase03-inline-chat.md)


## 🎯 Objective

Master GitHub Copilot's slash commands to rapidly generate service layers, interfaces, and complex code structures. Learn to use specialized commands for different development tasks and boost your productivity.

## 📖 About Slash Commands

Slash Commands provide:
- **Quick templates** for common code patterns
- **Specialized generators** for different file types
- **Rapid scaffolding** of project structures
- **Context-aware suggestions** based on command type
- **Time-saving shortcuts** for repetitive tasks

**Documentation**: [GitHub Copilot Slash Commands](https://docs.github.com/en/copilot/using-github-copilot/getting-code-suggestions-in-your-ide-with-github-copilot#using-github-copilot-chat-in-your-ide)

## 🏗️ What We'll Build

In this phase, we'll create:
- Service layer implementations
- Repository implementations
- API controllers (simulated)
- Utility functions and helpers
- Type definitions and interfaces
- Factory patterns and builders

## 📋 Step-by-Step Instructions

### Step 1: Available Slash Commands

**Open Copilot Chat** and explore available commands by typing `/`:

Common slash commands:
- `/explain` - Explain selected code
- `/fix` - Fix problems in selected code
- `/doc` - Generate documentation
- `/tests` - Generate test cases
- `/new` - Create new files
- `/newNotebook` - Create Jupyter notebooks

### Step 2: Generate Service Layer with /new

1. **In Copilot Chat**, use the `/new` command:
   ```
   /new Create a TaskService class in TypeScript that implements the TaskService interface from Phase 2. Include methods for CRUD operations, task assignment, status updates, and business logic validation.
   ```

2. **Follow up with specific requirements**:
   ```
   /new The TaskService should use dependency injection for TaskRepository and include proper error handling, logging, and validation.
   ```

3. **Create the file** `src/services/TaskService.ts` with the generated code

4. **Generate UserService**:
   ```
   /new Create UserService class with authentication methods, profile management, permission checking, and user analytics.
   ```

5. **Generate ProjectService**:
   ```
   /new Create ProjectService class with project lifecycle management, member management, and project analytics.
   ```

### Step 3: Create Repository Implementations with /new

1. **Generate in-memory TaskRepository**:
   ```
   /new Create TaskRepository implementation using in-memory storage with Map collections. Include all CRUD operations, searching, filtering, and sorting capabilities.
   ```

2. **Save as** `src/repositories/InMemoryTaskRepository.ts`

3. **Generate UserRepository**:
   ```
   /new Create UserRepository implementation with user management, authentication data, and query methods for user analytics.
   ```

4. **Generate ProjectRepository**:
   ```
   /new Create ProjectRepository implementation with project data management, member tracking, and project analytics queries.
   ```

### Step 4: Generate Utility Functions with /new

1. **Create validation utilities**:
   ```
   /new Create validation utility functions for email, password strength, date validation, and common business rules. Include TypeScript types and error details.
   ```

2. **Save as** `src/utils/validation.ts`

3. **Create date utilities**:
   ```
   /new Create date utility functions for task management: calculating due dates, business days, time remaining, and date formatting.
   ```

4. **Save as** `src/utils/dateUtils.ts`

5. **Create formatting utilities**:
   ```
   /new Create formatting utilities for displaying task data, user names, project status, and data export functions.
   ```

### Step 5: Generate API Controllers with /new

1. **Create TaskController**:
   ```
   /new Create TaskController class for REST API endpoints. Include GET, POST, PUT, DELETE routes for task management with proper HTTP status codes and error handling.
   ```

2. **Save as** `src/controllers/TaskController.ts`

3. **Create UserController**:
   ```
   /new Create UserController with authentication endpoints, profile management, and user administration routes.
   ```

4. **Create ProjectController**:
   ```
   /new Create ProjectController with project CRUD operations, member management endpoints, and project analytics routes.
   ```

### Step 6: Use /doc for Documentation

1. **Select your TaskService class** and use:
   ```
   /doc Generate comprehensive JSDoc documentation for this service class including parameter types, return values, and usage examples.
   ```

2. **Document the interfaces**:
   ```
   /doc Add TypeScript documentation for all repository interfaces with clear descriptions and examples.
   ```

3. **Document utility functions**:
   ```
   /doc Generate documentation for utility functions with parameter descriptions and usage examples.
   ```

### Step 7: Generate Tests with /tests

1. **Select TaskService** and use:
   ```
   /tests Generate comprehensive unit tests for TaskService using Jest. Include happy path, error cases, edge cases, and mock dependencies.
   ```

2. **Save as** `src/tests/TaskService.test.ts`

3. **Generate repository tests**:
   ```
   /tests Create unit tests for TaskRepository with data validation, query testing, and error scenarios.
   ```

4. **Generate utility tests**:
   ```
   /tests Create tests for validation utilities covering all validation rules and edge cases.
   ```

### Step 8: Use /fix for Code Improvements

1. **If you have any TypeScript errors**, select the problematic code:
   ```
   /fix Fix TypeScript compilation errors and improve type safety.
   ```

2. **Improve code quality**:
   ```
   /fix Optimize this code for better performance and maintainability.
   ```

3. **Fix potential bugs**:
   ```
   /fix Review and fix potential runtime errors and edge cases.
   ```

### Step 9: Use /explain for Understanding

1. **Select complex code sections**:
   ```
   /explain Explain how this dependency injection pattern works and its benefits.
   ```

2. **Understand design patterns**:
   ```
   /explain Explain the repository pattern implementation and how it promotes testability.
   ```

3. **Learn about generated code**:
   ```
   /explain Explain the error handling strategy used in this service layer.
   ```

## 🎯 Specific Slash Command Prompts

### /new Commands:
```
/new Create a factory class for creating different types of tasks with validation
```

```
/new Generate a builder pattern implementation for complex Project creation
```

```
/new Create middleware functions for request validation and error handling
```

### /doc Commands:
```
/doc Add comprehensive API documentation with request/response examples
```

```
/doc Generate README documentation for the service layer architecture
```

### /tests Commands:
```
/tests Create integration tests for the complete task management workflow
```

```
/tests Generate performance tests for repository operations
```

### /fix Commands:
```
/fix Improve error handling and add missing null checks
```

```
/fix Optimize memory usage and add input validation
```

## ✅ Expected Results

After completing this phase, you should have:

### Service Layer Structure:
```typescript
// TaskService with full implementation
export class TaskService implements ITaskService {
  constructor(
    private taskRepository: TaskRepository,
    private userService: UserService,
    private logger: Logger
  ) {}
  
  async createTask(taskData: CreateTaskDTO): Promise<Task> {
    // Comprehensive implementation with validation
  }
  
  async assignTask(taskId: string, userId: string): Promise<void> {
    // Business logic with permission checking
  }
  
  // All CRUD and business operations
}
```

### Repository Implementation:
```typescript
export class InMemoryTaskRepository implements TaskRepository {
  private tasks = new Map<string, Task>();
  private readonly logger: Logger;
  
  async findById(id: string): Promise<Task | null> {
    // Efficient lookup with logging
  }
  
  async findByUserId(userId: string): Promise<Task[]> {
    // Filtered queries with performance optimization
  }
  
  // Complete CRUD implementation
}
```

### Utility Functions:
```typescript
export const ValidationUtils = {
  validateEmail: (email: string): ValidationResult => {
    // Comprehensive email validation
  },
  
  validatePassword: (password: string): PasswordStrengthResult => {
    // Password strength checking
  },
  
  // All validation utilities
};
```

### API Controllers:
```typescript
export class TaskController {
  constructor(private taskService: TaskService) {}
  
  @GET('/tasks')
  async getTasks(req: Request, res: Response): Promise<void> {
    // HTTP endpoint with proper error handling
  }
  
  @POST('/tasks')
  async createTask(req: Request, res: Response): Promise<void> {
    // Task creation with validation
  }
  
  // All REST endpoints
}
```

## 💡 Slash Command Best Practices

1. **Be specific** in your /new commands about requirements
2. **Use /doc consistently** to maintain good documentation
3. **Run /tests** for all critical functionality
4. **Use /fix** proactively for code quality
5. **Combine commands** for comprehensive development workflow
6. **Use /explain** to understand generated patterns

## 🧪 Advanced Slash Command Exercises

1. **Create complex factories**:
   ```
   /new Create an abstract factory for creating different task types (Story, Bug, Epic) with specific validation rules for each type.
   ```

2. **Generate middleware**:
   ```
   /new Create authentication and authorization middleware for the API controllers with role-based access control.
   ```

3. **Build event system**:
   ```
   /new Create an event-driven system for task status changes with publisher/subscriber pattern and event logging.
   ```

4. **Create data migration**:
   ```
   /new Generate data migration utilities for converting between different data formats and versions.
   ```

## 🔍 Slash Command Workflow

### Development Workflow:
1. **Plan** with regular Chat
2. **Generate** with `/new`
3. **Document** with `/doc`
4. **Test** with `/tests`
5. **Fix** with `/fix`
6. **Understand** with `/explain`

### Quality Assurance:
- Use `/fix` regularly during development
- Generate comprehensive tests with `/tests`
- Document everything with `/doc`
- Explain complex patterns with `/explain`

## 📚 What You've Learned

- ✅ Using slash commands for rapid code generation
- ✅ Creating complete service layers with `/new`
- ✅ Generating comprehensive documentation with `/doc`
- ✅ Building test suites with `/tests`
- ✅ Fixing issues proactively with `/fix`
- ✅ Understanding complex code with `/explain`
- ✅ Combining commands for efficient workflows

## 🎯 Slash Commands Summary

| Command | Purpose | Best Used For |
|---------|---------|---------------|
| `/new` | Generate new code/files | Creating services, classes, utilities |
| `/doc` | Generate documentation | JSDoc, README, API docs |
| `/tests` | Create test cases | Unit tests, integration tests |
| `/fix` | Fix code issues | Bugs, performance, type errors |
| `/explain` | Explain code | Understanding patterns, learning |


**💡 Pro Tip**: Slash commands are your productivity boosters! Type `/` in Copilot Chat to see all available commands. Each command is designed for specific tasks - use `/new` for code generation, `/tests` for testing, and `/doc` for documentation. Combine them in your workflow for maximum efficiency!

## ➡️ Next Phase

Ready to learn about selection-based code improvements?

[![➡️ Next: Phase 05 - Code Brushes](https://img.shields.io/badge/➡️-Next%3A%20Phase%2005%20Code%20Brushes-green?style=flat-square)](phase05-code-brushes.md)

---

[🏠 Back to Main README](../README.md)
