# 🧪 Copilot CLI Hands-On Lab

A hands-on lab to get familiar with the GitHub Copilot CLI by building a Node.js calculator app from your terminal.

## Prerequisites

- Node.js 22+ and npm 10+
- An active GitHub Copilot subscription (Pro, Pro+, Business, or Enterprise)
- A terminal (macOS, Linux, or WSL on Windows)

---

## Step 1 — Install & Authenticate

### Install the Copilot CLI

Follow the official installation guide:
[Installing GitHub Copilot CLI](https://docs.github.com/en/copilot/how-tos/copilot-cli/cli-getting-started)

Or install directly via npm:

```bash
npm install -g @github/copilot
```

### Start & Authenticate

1. Type `copilot` in your terminal to start the CLI.
2. Use `/login` to authenticate with your GitHub account.
3. Once authenticated, use `/help` to view all available commands.

> [!NOTE]
> When starting Copilot CLI, you may be prompted to add this folder to the trusted folder list and to enable key bindings. Respond **yes** to both prompts to continue.

---

## Step 2 — Explore Key Commands

Try out the following useful slash commands:

| Command | Description |
|---------|-------------|
| `/session` | Shows details about your current chat session |
| `/context` | Provides a visual overview of your current token usage |
| `/usage` | View session statistics: premium requests used, session duration, lines of code edited, and token usage per model |
| `/share` | Save your session to a markdown file or GitHub gist |

### Additional commands worth exploring

| Command | Description |
|---------|-------------|
| `/model` | Select a different AI model |
| `/compact` | Summarize and compress conversation history |
| `/help` | View all available commands |

### Global shortcuts

```text
@             mention files, include contents in context
Esc           cancel the current operation
!             execute command in your local shell (bypass Copilot)
ctrl+c        cancel operation / clear input / exit
ctrl+d        shutdown
ctrl+l        clear the screen
shift+tab     switch between plan mode and regular interactive mode
```

✅ **Checkpoint:** The `/session`, `/context`, and `/usage` commands should all return information about your current session.

---

## Step 3 — Generate a Calculator App

Now let's put the CLI to work. You'll use Copilot CLI to build a Node.js calculator app entirely from the terminal.

### Start a Copilot CLI session

```bash
copilot --allow-all
```

> [!NOTE]
> The `--allow-all` option enables all permissions at once (tools, file paths, and URLs) without prompting for confirmation.

### Create the calculator

Ask Copilot CLI to create the calculator functions based on the provided image:

> ![Static Badge](https://img.shields.io/badge/CLI-Prompt-text?style=flat-square&logo=github-copilot&labelColor=8250df&color=fbefff)
>
> ```prompt
> @images/js-calculator.png help me create a Node.js CLI calculator app
> based only on the four basic math operations in this image.
> Create the code and put it in the 'src' directory.
> Make sure the calculator is commented with the operations it supports.
> ```

### Run and test the calculator

> ![Static Badge](https://img.shields.io/badge/CLI-Prompt-text?style=flat-square&logo=github-copilot&labelColor=8250df&color=fbefff)
>
> ```prompt
> Run and test the calculator functions with some example operations
> shown in the image @images/calc-basic-operations.png.
> ```

### Create comprehensive tests

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

### Save your work

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

- Make sure you have Node.js 22+ installed: `node --version`
- If npm install fails, try: `sudo npm install -g @github/copilot`
- Make sure you have GitHub Copilot access enabled for your account
- If authentication fails, run `copilot` and then `/login`
- You can also create the calculator.js file manually based on Copilot's suggestions
- Remember to export your functions using `module.exports`

</details>

---

## 🎉 Completion

_Congratulations — you've completed the Copilot CLI Lab!_

<img src="https://octodex.github.com/images/jetpacktocat.png" alt="celebrate" width=200 align=right>

Here's a recap of what you learned:

- ✅ Installed the Copilot CLI and authenticated
- ✅ Explored session commands (`/session`, `/context`, `/usage`, `/share`)
- ✅ Generated a Node.js calculator app using image context
- ✅ Created and ran tests from the terminal

### References

- [GitHub Copilot Documentation](https://docs.github.com/en/copilot)
- [Using the Copilot CLI](https://docs.github.com/en/copilot/how-tos/use-copilot-agents/use-copilot-cli)
- [Copilot CLI 101](https://github.blog/ai-and-ml/github-copilot-cli-101-how-to-use-github-copilot-from-the-command-line/)

---

&copy; 2025 GitHub &bull; [MIT License](https://gh.io/mit)
