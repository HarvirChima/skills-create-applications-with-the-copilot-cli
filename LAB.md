# 🧪 Copilot CLI Lab: Build a Calculator from the Terminal

A hands-on lab to learn the standalone GitHub Copilot CLI by building a Node.js calculator app — entirely from your terminal.

## Prerequisites

- Node.js 22+ and npm 10+
- An active GitHub Copilot subscription (Pro, Pro+, Business, or Enterprise)
- A terminal (macOS, Linux, or WSL on Windows)

---

## Step 1 — Install & Explore Copilot CLI

### 📖 Theory: GitHub Copilot CLI - A Standalone Terminal Application

#### What is GitHub Copilot CLI?

GitHub Copilot CLI is a **standalone terminal application** that brings the power of GitHub Copilot directly to your command line. It is installed via npm and provides a rich interactive experience for developers.

<img width="60%" height="60%" alt="CopilotCLI" src="https://github.com/HarvirChima/skills-create-applications-with-the-copilot-cli/blob/main/.github/images/copilot-cli.png?raw=true" />

#### Key capabilities include:

- Providing intelligent command suggestions powered by the latest AI models from OpenAI and Google
- Generating code snippets and scripts directly in your terminal
- Assisting with Git operations
- Supporting image inputs via paste and drag-and-drop for visual context
- Depending on your Copilot CLI configuration (for example, if you don't use the `--allow-all` option), you may be prompted to enable certain features during the session. Respond **yes** to these prompts.
- `/session`: Shows details about your current chat session
- `/context`: Provides a visual overview of your current token usage
- `/usage`: Lets you view your session statistics, including:
  - The amount of premium requests used in the current session
  - The session duration
  - The total lines of code edited
  - A breakdown of token usage per model
- `/share [file|gist] [path]`: Save your session to a markdown file or GitHub gist
- Creating **custom agents** to encode specialized prompts and workflows

#### Global shortcuts

```text
@             mention files, include contents in context
Esc           cancel the current operation
!             execute command in your local shell (bypass Copilot)
ctrl+c        cancel operation / clear input / exit
ctrl+d        shutdown
ctrl+l        clear the screen
shift+tab     switch between plan mode and regular interactive mode
```

#### References

- [Installing GitHub Copilot CLI](https://docs.github.com/en/copilot/how-tos/set-up/install-copilot-cli)
- [Using GitHub Copilot CLI](https://docs.github.com/en/copilot/how-tos/use-copilot-agents/use-copilot-cli)
- [GitHub Copilot CLI 101](https://github.blog/ai-and-ml/github-copilot-cli-101-how-to-use-github-copilot-from-the-command-line/)

### ⌨️ Activity 1: Install the Standalone Copilot CLI

1. Open your terminal and install the standalone GitHub Copilot CLI:

   > ![Static Badge](https://img.shields.io/badge/Terminal-text?logo=gnometerminal&labelColor=0969da&color=ddf4ff)

   > ```bash
   > npm install -g @github/copilot
   > ```

2. Verify the installation by running:

   > ![Static Badge](https://img.shields.io/badge/Terminal-text?logo=gnometerminal&labelColor=0969da&color=ddf4ff)

   > ```bash
   > copilot --version
   > ```

> [!TIP]
> After installation, you can use the `copilot` command anywhere in your terminal to start an interactive session!

### ⌨️ Activity 2: Explore Copilot CLI

1. Start an interactive Copilot CLI session:

   > ![Static Badge](https://img.shields.io/badge/Terminal-text?logo=gnometerminal&labelColor=0969da&color=ddf4ff)
   >
   > ```bash
   > copilot
   > ```

> [!NOTE]
> When starting Copilot CLI, you may be prompted to add this folder to the trusted folder list and to key bindings. Respond **yes** to both prompts to continue.

<img width="60%" height="60%" alt="CopilotCLIAddDir" src="https://github.com/HarvirChima/skills-create-applications-with-the-copilot-cli/blob/main/.github/images/copilot-cli-add-directory.png?raw=true" />
<br />
<img width="60%" height="60%" alt="CopilotCLITerminalBindings" src="https://github.com/HarvirChima/skills-create-applications-with-the-copilot-cli/blob/main/.github/images/copilot-cli-terminal-bindings.png?raw=true" />

2. Authorize with GitHub (if not already authenticated):

   > ![Static Badge](https://img.shields.io/badge/CLI-Prompt-text?style=flat-square&logo=github-copilot&labelColor=8250df&color=fbefff)
   >
   > ```prompt
   > /login
   > ```

3. Explore useful slash commands:
   - View your current session information:

     > ![Static Badge](https://img.shields.io/badge/CLI-Prompt-text?style=flat-square&logo=github-copilot&labelColor=8250df&color=fbefff)
     >
     > ```prompt
     > /session
     > ```

   - View your current context information:

     > ![Static Badge](https://img.shields.io/badge/CLI-Prompt-text?style=flat-square&logo=github-copilot&labelColor=8250df&color=fbefff)
     >
     > ```prompt
     > /context
     > ```

   - View your current usage information:

     > ![Static Badge](https://img.shields.io/badge/CLI-Prompt-text?style=flat-square&logo=github-copilot&labelColor=8250df&color=fbefff)
     >
     > ```prompt
     > /usage
     > ```

> [!NOTE]
>
> - `/session`: Shows details about your current chat session
> - `/context`: Provides a visual overview of your current token usage
> - `/usage`: Lets you view your session statistics including premium requests used, session duration, lines of code edited, and token usage per model

✅ **Checkpoint:** You should see Copilot's version number and be able to start an interactive session. The `/session`, `/context`, and `/usage` commands should all return information about your session.

<details>
<summary>Having trouble? 🤷</summary><br/>

- Make sure you have Node.js 22+ installed: `node --version`
- If npm install fails, try: `sudo npm install -g @github/copilot`
- Make sure you have GitHub Copilot access enabled for your account
- If authentication fails, run `copilot` and then `/login`

</details>

---

## Step 2 — Generate a Calculator App

### 📖 Theory: Collaborative Development with Copilot CLI

#### Interactive Development with Copilot CLI

The standalone Copilot CLI provides a rich interactive experience for development:

- Start a session by simply running `copilot` in your terminal
- Have natural conversations about your code and get intelligent suggestions
- Generate boilerplate code based on your requirements
- Use the latest AI models for cutting-edge responses
- Use the `@` symbol to reference files and images directly in your prompts

> [!NOTE]
> References:
>
> - [Using GitHub Copilot CLI](https://docs.github.com/en/copilot/how-tos/use-copilot-agents/use-copilot-cli)

> [!IMPORTANT]
> If you have restarted your terminal you may need to run `copilot --allow-all` and then authenticate with GitHub again using `/login` in the Copilot CLI session.

### ⌨️ Activity: Generate Calculator Code with Copilot CLI

1. Start an interactive Copilot CLI session (if not already in one):

   > ![Static Badge](https://img.shields.io/badge/Terminal-text?logo=gnometerminal&labelColor=0969da&color=ddf4ff)
   >
   > ```bash
   > copilot --allow-all
   > ```

> [!NOTE]
> The `--allow-all` option enables all permissions at once: it is equivalent to `--allow-all-tools`, `--allow-all-paths`, and `--allow-all-urls`.
> This allows the CLI to access any file path, use any tool, and access any URL without prompting for confirmation.
> Use with caution, as it grants the CLI full access and automation capabilities.

2. Ask Copilot CLI to create the calculator functions based on the image:

   > ![Static Badge](https://img.shields.io/badge/CLI-Prompt-text?style=flat-square&logo=github-copilot&labelColor=8250df&color=fbefff)
   >
   > ```prompt
   > @images/js-calculator.png help me create a Node.js CLI calculator app
   > based only on the four basic math operations in this image.
   > Create the code and put it in the 'src' directory.
   > Make sure the calculator is commented with the operations it supports.
   > ```

   Alternatively, use headless mode with a prompt:

   > ![Static Badge](https://img.shields.io/badge/Terminal-text?logo=gnometerminal&labelColor=0969da&color=ddf4ff)
   >
   > ```bash
   > copilot -p "@images/js-calculator.png help me create a Node.js CLI calculator app based only on the four basic math operations in this image. Create the code and put it in the 'src' directory. Make sure the calculator is commented with the operations it supports."
   > ```

> [!NOTE]
> This example uses an image of a web JavaScript calculator to demonstrate how you can use images with the Copilot CLI to provide visual context for your requests.

3. Run and test your calculator functions:

   > ![Static Badge](https://img.shields.io/badge/CLI-Prompt-text?style=flat-square&logo=github-copilot&labelColor=8250df&color=fbefff)
   >
   > ```prompt
   > Run and test the calculator functions with some example operations
   > shown in the image @images/calc-basic-operations.png.
   > ```

4. Create comprehensive tests for the calculator functions:

   > ![Static Badge](https://img.shields.io/badge/CLI-Prompt-text?style=flat-square&logo=github-copilot&labelColor=8250df&color=fbefff)
   >
   > ```prompt
   > Create comprehensive unit tests for all the calculator functions:
   > - Expand tests based on the following example:
   >   - @images/calc-basic-operations.png
   > - Add these tests to a src/tests/calculator.tests.js file
   > - Use a popular Node.js testing framework if one isn't installed
   > - addition, subtraction, multiplication, and division
   > - test edge cases like division by zero
   > - Make sure all tests run and pass
   > ```

> [!NOTE]
> Hit ctrl+o to see output of the passed tests that Copilot CLI ran for you!

5. Save your work locally:

   > ![Static Badge](https://img.shields.io/badge/CLI-Prompt-text?style=flat-square&logo=github-copilot&labelColor=8250df&color=fbefff)
   >
   > ```prompt
   > Add all calculator and test files to git.
   > Commit with message "Implement basic calculator operations and tests:
   > addition, subtraction, multiplication, division"
   > ```

> [!TIP]
> You can paste or drag-and-drop images into Copilot CLI to provide visual context for your questions!

✅ **Checkpoint:** `node src/calculator.js` runs without errors, and your tests pass.

<details>
<summary>Having trouble? 🤷</summary><br/>

- Make sure you're in the repository directory when running commands
- The `copilot` command requires Node.js 22+ to be installed
- If authentication fails, run `copilot` and follow the login prompts
- You can also create the calculator.js file manually based on Copilot's suggestions
- Remember to export your functions using `module.exports`

</details>

---

## Step 3 — Expand Calculator Functionality

### 📖 Theory: Iterative Development with Copilot CLI

#### Maintaining Momentum with Copilot CLI

The standalone Copilot CLI helps maintain development momentum by:

- Quickly generating code for new features using the latest AI models
- Suggesting best practices and patterns
- Helping debug and test new functionality
- Reducing context switching by keeping you in the terminal
- Handling long-running shell commands more efficiently
- Supporting improved automation with the headless `-p` mode

#### Testing and Improvement Workflows

As you add features, Copilot CLI can help you:

- Generate test cases for new operations
- Suggest edge cases to consider
- Create documentation
- Refactor code for better maintainability
- Save and share your development sessions using `/share`

> [!IMPORTANT]
> If you have restarted your terminal you may need to run `copilot --allow-all` and then authenticate with GitHub again using `/login` from within the Copilot CLI session.

### ⌨️ Activity: Add More Operations to the Calculator

1. Start an interactive Copilot CLI session (if not already in one):

   > ![Static Badge](https://img.shields.io/badge/Terminal-text?logo=gnometerminal&labelColor=0969da&color=ddf4ff)
   >
   > ```bash
   > copilot --allow-all
   > ```

2. Ask Copilot CLI to implement the new operations:

   > ![Static Badge](https://img.shields.io/badge/CLI-Prompt-text?style=flat-square&logo=github-copilot&labelColor=8250df&color=fbefff)
   >
   > ```prompt
   > Add these functions to my existing calculator.js:
   > 1. modulo(a, b) - returns the remainder of a divided by b
   > 2. power(base, exponent) - returns base raised to the exponent
   > 3. squareRoot(n) - returns the square root of n with error handling for negative numbers
   > ```

   Alternatively, use headless mode:

   > ![Static Badge](https://img.shields.io/badge/Terminal-text?logo=gnometerminal&labelColor=0969da&color=ddf4ff)
   >
   > ```bash
   > copilot -p "Add these functions to my existing calculator.js: 1. modulo(a, b) - returns the remainder of a divided by b; 2. power(base, exponent) - returns base raised to the exponent; 3. squareRoot(n) - returns the square root of n with error handling for negative numbers"
   > ```

3. Add tests for the new operations:

   > ![Static Badge](https://img.shields.io/badge/CLI-Prompt-text?style=flat-square&logo=github-copilot&labelColor=8250df&color=fbefff)
   >
   > ```prompt
   > Add tests for the new calculator operations:
   > - Expand tests based on the following example:
   >   - @images/calc-extended-operations.png
   > - Add new tests for the new operations to the existing src/tests/calculator.tests.js file
   > - Use a popular Node.js testing framework if one isn't installed
   > - Make sure to include edge case tests like square root of negative numbers
   > - Make sure all tests run and pass
   > ```

4. Save your work locally:

   > ![Static Badge](https://img.shields.io/badge/CLI-Prompt-text?style=flat-square&logo=github-copilot&labelColor=8250df&color=fbefff)
   >
   > ```prompt
   > Add all calculator and test files to git.
   > Commit with message "Implement additional calculator operations and tests:
   > modulo, power, square root"
   > ```

> [!TIP]
> Use `/share gist` in your Copilot CLI session to save your session as a GitHub gist for future reference!

✅ **Checkpoint:** All tests pass including modulo, power, and squareRoot edge cases.

<details>
<summary>Having trouble? 🤷</summary><br/>

- The calculator.js file should export functions that can be required/imported
- You can test operations manually using Node.js REPL: `node` then type your code
- For square root of negative numbers, consider returning `NaN` or throwing an error
- Use `copilot --help` to see all available command options

</details>

---

## Step 4 — Refactor & Document with Copilot CLI

### 📖 Theory: Code Quality and Documentation

Good code is not just about functionality — it should also be readable, maintainable, and well-documented. Copilot CLI can help you improve code quality by:

- Adding JSDoc comments to document function signatures and behavior
- Creating README files and usage guides
- Refactoring for better error handling and readability
- Generating example scripts that demonstrate how to use your code

### ⌨️ Activity: Improve Code Quality with Copilot CLI

1. Start an interactive Copilot CLI session (if not already in one):

   > ![Static Badge](https://img.shields.io/badge/Terminal-text?logo=gnometerminal&labelColor=0969da&color=ddf4ff)
   >
   > ```bash
   > copilot --allow-all
   > ```

2. Ask Copilot CLI to add JSDoc comments to all functions:

   > ![Static Badge](https://img.shields.io/badge/CLI-Prompt-text?style=flat-square&logo=github-copilot&labelColor=8250df&color=fbefff)
   >
   > ```prompt
   > Add JSDoc comments to all functions in src/calculator.js,
   > documenting parameters, return values, and any thrown errors.
   > ```

3. Ask Copilot CLI to create a README for the `src/` directory:

   > ![Static Badge](https://img.shields.io/badge/CLI-Prompt-text?style=flat-square&logo=github-copilot&labelColor=8250df&color=fbefff)
   >
   > ```prompt
   > Create a README.md in the src/ directory that describes the calculator,
   > lists all available functions with their signatures, and shows usage examples.
   > ```

4. Ask Copilot CLI to improve error handling:

   > ![Static Badge](https://img.shields.io/badge/CLI-Prompt-text?style=flat-square&logo=github-copilot&labelColor=8250df&color=fbefff)
   >
   > ```prompt
   > Refactor the calculator code for better error handling:
   > - Validate that inputs are numbers
   > - Return meaningful error messages
   > - Make sure all existing tests still pass after the refactor
   > ```

5. Ask Copilot CLI to generate a usage example script:

   > ![Static Badge](https://img.shields.io/badge/CLI-Prompt-text?style=flat-square&logo=github-copilot&labelColor=8250df&color=fbefff)
   >
   > ```prompt
   > Generate a usage example script at src/examples.js that demonstrates
   > all available calculator functions with sample inputs and expected outputs.
   > ```

6. Save your work locally:

   > ![Static Badge](https://img.shields.io/badge/CLI-Prompt-text?style=flat-square&logo=github-copilot&labelColor=8250df&color=fbefff)
   >
   > ```prompt
   > Add all updated files to git.
   > Commit with message "Add JSDoc comments, README, improved error handling, and usage examples"
   > ```

✅ **Checkpoint:** Your functions have JSDoc comments, a `src/README.md` exists, and the refactored code still passes all tests.

<details>
<summary>Having trouble? 🤷</summary><br/>

- Run your tests after refactoring to make sure nothing broke: `npm test` or the command Copilot used to run your tests
- If JSDoc syntax is new to you, ask Copilot: "Show me what a JSDoc comment looks like"
- You can view the generated README at any time with `!cat src/README.md`

</details>

---

## Step 5 — Explore Advanced Features

### 📖 Theory: Getting More from Copilot CLI

Now that you've built a working calculator app, let's explore some advanced Copilot CLI features that can help in real-world development workflows.

### ⌨️ Activity: Advanced Copilot CLI Features

1. Try switching models with `/model`:

   > ![Static Badge](https://img.shields.io/badge/CLI-Prompt-text?style=flat-square&logo=github-copilot&labelColor=8250df&color=fbefff)
   >
   > ```prompt
   > /model
   > ```

   Select a different model and ask a question to compare responses.

2. Try headless mode — run Copilot without an interactive session:

   > ![Static Badge](https://img.shields.io/badge/Terminal-text?logo=gnometerminal&labelColor=0969da&color=ddf4ff)
   >
   > ```bash
   > copilot -p "Explain what my calculator does by reading @src/calculator.js"
   > ```

3. Save your session history with `/share`:

   > ![Static Badge](https://img.shields.io/badge/CLI-Prompt-text?style=flat-square&logo=github-copilot&labelColor=8250df&color=fbefff)
   >
   > ```prompt
   > /share file session.md
   > ```

   This saves your current session to a `session.md` file you can review later.

4. Try `/compact` to summarize and compress the conversation history:

   > ![Static Badge](https://img.shields.io/badge/CLI-Prompt-text?style=flat-square&logo=github-copilot&labelColor=8250df&color=fbefff)
   >
   > ```prompt
   > /compact
   > ```

5. Check your final session stats:

   > ![Static Badge](https://img.shields.io/badge/CLI-Prompt-text?style=flat-square&logo=github-copilot&labelColor=8250df&color=fbefff)
   >
   > ```prompt
   > /usage
   > ```

✅ **Checkpoint:** You've explored at least 3 advanced features and saved your session.

---

## 🎉 Review & Completion

_Congratulations, you've completed the Copilot CLI Lab and learned a lot about building apps from the terminal!_

<img src="https://octodex.github.com/images/jetpacktocat.png" alt="celebrate" width=200 align=right>

Here's a recap of your accomplishments:

- ✅ Installed the Copilot CLI and explored session commands
- ✅ Generated a Node.js CLI calculator app using image context
- ✅ Expanded calculator functionality with modulo, power, and squareRoot
- ✅ Added JSDoc comments, a README, improved error handling, and usage examples
- ✅ Explored advanced features: model switching, headless mode, session sharing

### Explore More Copilot CLI Features

Now that you've learned the basics, explore these additional capabilities:

**Core Features:**

- **Latest AI models**: Access cutting-edge models from OpenAI and Google using `/model` command
- **Image support**: Paste or drag-and-drop images for visual context in your queries
- **`/share` command**: Save your chat sessions as Markdown files or GitHub gists
- **Headless mode (`-p`)**: Use Copilot CLI in automation scripts and pipelines
- **MCP server support**: Integrate with Model Context Protocol tools for extended functionality

**Advanced Features:**

- **Custom agents**: Create specialized agent personas in `.github/agents/` for domain-specific workflows
- **`/delegate` command**: Assign tasks to Copilot coding agent for autonomous work

### What's next?

- [GitHub Copilot Documentation](https://docs.github.com/en/copilot) - Learn more about all Copilot features
- [Using the Copilot CLI](https://docs.github.com/en/copilot/how-tos/use-copilot-agents/use-copilot-cli) - Official Copilot CLI guide
- [Copilot CLI 101](https://github.blog/ai-and-ml/github-copilot-cli-101-how-to-use-github-copilot-from-the-command-line/) - Comprehensive tutorial
- [More GitHub Skills](https://learn.github.com/skills) - Continue learning with other exercises
- Try using Copilot CLI in your own projects to boost productivity!

---

## 🎯 Bonus Lab Ideas

Want to keep practicing? Here are some additional labs you can tackle using only the Copilot CLI:

### 1. Lab: Build a REST API

Use Copilot CLI to scaffold an Express.js REST API with CRUD endpoints, middleware, and error handling. Test it with `curl` commands generated by Copilot.

**Starting prompt:**
```prompt
Help me create an Express.js REST API with CRUD endpoints for a simple todo list.
Include middleware for request logging and error handling.
```

### 2. Lab: Debug a Broken App

Create a file with intentional bugs and use Copilot CLI to identify and fix them interactively.

**Starting prompt:**
```prompt
I have a broken JavaScript file. Help me identify and fix all the bugs: @src/buggy-app.js
```

### 3. Lab: Write a Bash Automation Script

Use Copilot CLI to generate a bash script that automates common dev tasks such as setting up a project, running linters, or generating changelogs.

**Starting prompt:**
```prompt
Help me write a bash script that: sets up a new Node.js project, installs common dependencies,
initializes git, and creates a basic project structure.
```

### 4. Lab: Convert JavaScript to TypeScript

Use Copilot CLI to convert the calculator from JavaScript to TypeScript, adding type annotations, interfaces, and a `tsconfig.json`.

**Starting prompt:**
```prompt
Convert my calculator from JavaScript to TypeScript.
Add proper type annotations, interfaces for the function signatures, and a tsconfig.json.
```

### 5. Lab: Create a CLI Tool with Commander.js

Use Copilot CLI to build a proper CLI tool using `commander` or `yargs`, with flags, help text, and subcommands.

**Starting prompt:**
```prompt
Help me turn my calculator into a proper CLI tool using commander.js,
with flags like --operation and --numbers, plus a --help flag.
```

### 6. Lab: Explore Custom Agents

Create a `.github/agents/` directory with custom agent definitions and explore how to invoke them with `/agent`.

**Starting prompt:**
```prompt
Help me create a custom agent definition in .github/agents/ for a "code reviewer" agent
that specializes in reviewing JavaScript code for best practices.
```

### 7. Lab: Multi-language Challenge

Rewrite the calculator in Python, Go, or Rust using only Copilot CLI, comparing how it handles different languages.

**Starting prompt:**
```prompt
Rewrite my JavaScript calculator in Python.
Include the same functions: add, subtract, multiply, divide, modulo, power, squareRoot.
Add unit tests using pytest.
```

---

&copy; 2025 GitHub &bull; [MIT License](https://gh.io/mit)
