# Robust TypeScript Template for Discord.js Bot Development

This is a template for building robust and scalable Discord bots using TypeScript and Discord.js.  
It is fully compatible with VSCode, allowing you to run and debug your bot with ease.  
The project includes ESLint and Prettier for enforcing code quality, and uses Husky to ensure clean commits.  
It also features a modular slash command system and optional Prisma integration for database access.

## 🚀 Features

- **Discord.js Interaction Command System**  
  Define slash commands as individual files inside the `src/commands` directory.  
  Easy to read and maintain — each command is self-contained.

- **Prisma-ready**  
  Includes setup for using [Prisma](https://www.prisma.io/) as your ORM with SQL databases.  
  If you don’t need it, see [Removing Prisma](#removing-prisma) below.

- **VSCode Ready**  
  Comes with launch configurations for debugging directly in VSCode using `F5`.

- **ESLint & Prettier**  
  Enforces strict code style and formatting.
  - Auto-fix on save for common issues.
  - Requires return types and JSDoc for better maintainability.

- **Husky & lint-staged**  
  Runs lint and formatting checks before each commit for consistent code quality.

- **Modern ESM Support**  
  Uses ESM syntax (`import/export`) out of the box.

## 📦 Getting Started

1. Clone the repository:
   ```bash
   git clone https://github.com/Kamesuta/discordjs-typescript-template.git
   cd discordjs-typescript-template
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Run the bot:
   ```bash
   npm run start
   ```

4. Lint and format:
   ```bash
   npm run lint
   npm run prettier
   ```

## 📁 Project Structure

```
prisma/                # Prisma schema and client
src/
├── commands/          # 1 file = 1 slash command
├── utils/               # Utilities (e.g., logging, config)
└── index.ts           # Bot entry point
```

## 🗑 Removing Prisma

If you don’t need a database:

1. Delete the `prisma/` folder.
2. Remove `import { PrismaClient }` and `new PrismaClient()` lines  from `src/index.ts`.
3. Remove `heroku-postbuild` line from `package.json`.
4. Uninstall the Prisma packages:
   ```bash
   npm uninstall prisma @prisma/client
   ```
