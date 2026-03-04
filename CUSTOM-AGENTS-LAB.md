# 🤖 Custom Agents Hands-On Lab

A hands-on lab to get experience building and using custom agents with GitHub Copilot.

## Overview

Custom agents let you encode specialized prompts, personas, and workflows into reusable `.md` files that live in your repository's `.github/agents/` directory. Once created, you can invoke them by name (e.g., `@test-agent`) in Copilot Chat or the Copilot CLI.

In this lab you will build **five custom agents** using your own code. Bring a repository you work on and use Copilot to help generate `agent.md` files for each of the agents below. We've included example descriptions and boundaries for each — adjust them to match your project.

---

## Getting Started

### Example Prompt

Use a prompt like this in Copilot Chat or the Copilot CLI to generate a complete agent definition:

```
Create a test agent for this repository. It should:
- Have the persona of a QA software engineer
- Write tests for this codebase
- Run tests and analyze results
- Write to "/tests/" directory only
- Never modify source code or remove failing tests
- Include specific examples of good test structure
```

Copilot will generate a complete `agent.md` file with persona, commands, and boundaries based on your codebase. Review it, add in YAML frontmatter, adjust the commands for your project, and you're ready to use `@test-agent`.

> [!TIP]
> Alternatively, feel free to explore, install, and modify an existing custom agent that works for you: [awesome-copilot agents](https://github.github.com/awesome-copilot/agents/)

---

## Five Agents Worth Building

### 1. `@docs-agent`

One of your early agents should write documentation. It reads your code and generates API docs, function references, and tutorials. Give it commands like `npm run docs:build` and `markdownlint docs/` so it can validate its own work. Tell it to write to `docs/` and never touch `src/`.

- **What it does:** Turns code comments and function signatures into Markdown documentation
- **Example commands:** `npm run docs:build`, `markdownlint docs/`
- **Example boundaries:** Write to `docs/`, never modify source code

### 2. `@test-agent`

This one writes tests. Point it at your test framework (Jest, PyTest, Playwright) and give it the command to run tests. The boundary here is critical: it can write to tests but should never remove a test because it is failing and cannot be fixed by the agent.

- **What it does:** Writes unit tests, integration tests, and edge case coverage
- **Example commands:** `npm test`, `pytest -v`, `cargo test --coverage`
- **Example boundaries:** Write to `tests/`, never remove failing tests unless authorized by user

### 3. `@lint-agent`

A fairly safe agent to create early on. It fixes code style and formatting but shouldn't change logic. Give it commands that let it auto-fix style issues. This one's low-risk because linters are designed to be safe.

- **What it does:** Formats code, fixes import order, enforces naming conventions
- **Example commands:** `npm run lint --fix`, `prettier --write`
- **Example boundaries:** Only fix style, never change code logic

### 4. `@api-agent`

This agent builds API endpoints. It needs to know your framework (Express, FastAPI, Rails) and where routes live. Give it commands to start the dev server and test endpoints. The key boundary: it can modify API routes but must ask before touching database schemas.

- **What it does:** Creates REST endpoints, GraphQL resolvers, error handlers
- **Example commands:** `npm run dev`, `curl localhost:3000/api`, `pytest tests/api/`
- **Example boundaries:** Modify routes, ask before schema changes

### 5. `@dev-deploy-agent`

Handles builds and deployments to your local dev environment. Keep it locked down: only deploy to dev environments and require explicit approval. Give it build commands and deployment tools but make the boundaries very clear.

- **What it does:** Runs local or dev builds, creates Docker images
- **Example commands:** `npm run build`, `docker build .`, `npm run deploy:dev`
- **Example boundaries:** Only deploy to dev, require user approval for anything with risk

---

## Next Steps

- Review each generated agent file and customize the commands and boundaries for your project
- Place your agent files in `.github/agents/` in your repository
- Invoke agents by name in Copilot Chat or the Copilot CLI (e.g., `@test-agent`)
- Browse more agents at [awesome-copilot agents](https://github.github.com/awesome-copilot/agents/)
- Learn more about custom agents in the [GitHub Copilot documentation](https://docs.github.com/en/copilot)

---

&copy; 2025 GitHub &bull; [MIT License](https://gh.io/mit)
