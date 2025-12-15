## Common Instructions
- Use Korean when conversing with users. However, write code and comments in English.
- When writing Markdown documents such as README.md, use the language specified by the user; if content already exists, follow that language.
- When the user explicitly requests a language, use that language.
- Tab size follows the setting for each language.
- When installing packages that require a specific version, use the latest stable version unless the user explicitly requests otherwise.
- Use the latest syntax and features for code whenever possible.
- Do not write all code in a single file. Split files and directories appropriately.

## Language-Specific Instructions

### Typescript / Yarn
- Use Yarn as the package manager.
- Directly editing package.json is strictly prohibited; install/remove packages only through yarn add/remove commands.
- Direct edits are allowed only for non-sensitive tasks such as adding run scripts or setting name, version, or author.
- Run code in the form yarn <script>.
- Set tab size to 4.
- Use alias imports mapped to the src/ root with `@/`.
    - E.g., `@/modules/...`, `@/common/...`, `@/config/...`
- Use alias imports when referencing across module boundaries (different modules/layers).
    - E.g., `@/modules/user/user.module`
- Allow relative paths for referencing files within the same module (or feature directory).
    - E.g., `./dto/create-user.dto`, `../entities/user.entity`
- Avoid excessive use of `index.ts` barrel exports with alias imports.
    - Use them sparingly when necessary; prefer explicit imports by default.
- When mixing alias imports and relative paths, follow these guidelines:
    - External (between modules/layers): Alias
    - Internal (within the same module/feature): Relative paths
- Module dependencies should be explicit and avoid circular references.

### Python / UV
- Use uv as the package manager.
- Do not use pip commands or directly edit requirements.py or pyproject.toml.
- Use uv add, remove, etc. to add or remove packages.
- Run code with uv run.
- Set tab size to 4.

### Terraform
- Set tab size to 2.
- The default structure uses envs/, keypairs/, modules/.
- Use locals to minimize duplicate code and improve reusability.

### JSON
- Set tab size to 4.

## Framework-Specific Instructions

### React / Next
- Always use yarn.
- Use vanilla-extract for CSS.
- Do not use Tailwind CSS.
- Use <> as the design system and optionally use <> additionally.
- Perform SEO optimization and include OG, etc.
- When requested by the user, develop to support multiple languages using i18n, next-intl, etc.
- By default, manage server components separately under lib/.
- Write tests with vitest and run them.

### NestJS
- Use <MySQL or PostgreSQL> as the DBMS and Sequelize as the ORM.
- Use Redis for caching.
- Use NestJS + Typescript as the server framework.
- Always write tests and run them.
- Validate all DTOs with class-validator and also use class-transformer when needed.
- Manage the cors value in the env file.
- Enable health checks through @nestjs/terminus.

### FastAPI
- Use <MySQL or PostgreSQL> as the DBMS and Tortoise as the ORM.
- Use Redis for caching.
- Use FastAPI + Python + UV as the server framework.
- Always write tests and run them.
- Validate DTOs through Pydantic models.
- Manage the cors value in the env file.
- In prod environments, use gunicorn with the worker count set to CPU cores * 2 + 1.

### AWS CloudFormation (in progress)
- Set tab size to 2.
- Version/template rules: include AWSTemplateFormatVersion, Description, Metadata by default; specify parameter types and constraints, minimize defaults, and actively use Mappings/Conditions.
- Stack policy: creation and update policies are required; prevent resource destruction with UpdateReplacePolicy/DeletionPolicy (especially DB/EFS/S3). Allow only change set–based deployments.
- Parameters/secrets: reference secret values from SSM Parameter/Secrets Manager; use NoEcho parameters and define parameter store hierarchy rules.
- Default to modularization and actively use a nested stack structure.

## Part-Specific Instructions

### Frontend part
- Install Sentry and enable error logging.
- Do not hardcode values; manage them as constants. Prefer managing constants via .env, but use defaults when .env lacks values.

### Backend part
- Install Sentry and enable error logging.
- Develop to minimize code duplication.
- Design with scalability, maintainability, and testability in mind.
- Use a modular structure.
- Log all events thoroughly by including timestamp, level, msg, service, env, requestId, userId, method, path, status, latency_ms, ip, userAgent, stack (optional), etc.
- Output logs to stdout.
- Never hardcode values; prioritize managing them through .env.
- Implement health check, liveness probe, and readiness probe endpoints.

### Cloud part (in progress)
- Use snake_case by default, preferring _ over -.
- Separate dev/staging/prod environments.

## Agent Behavior Rules

- Always follow the user's instructions first.
- If there are unclear requirements, do not implement based on assumptions; instead, document clear assumptions or ask questions.
- When the user requests code changes, always provide only the modified parts unless otherwise specified.
- Respect the user's existing coding style and design.
- Do not propose unnecessarily large changes at once.
- Write code that is maintainable by humans, even if it is auto-generated.