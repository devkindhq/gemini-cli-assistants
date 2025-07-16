# Gemini CLI Assistants

A collection of ready-to-use Gemini CLI agent templates for business workflows. Quickly bootstrap new projects with best-practice agent settings and documentation.

## 1. Prerequisites
- [Node.js](https://nodejs.org/) (v16+ recommended)
- [npm](https://www.npmjs.com/) or [yarn](https://yarnpkg.com/)

Check your installation:
```sh
node -v
npm -v
```

## 2. Install Gemini CLI

Install the Gemini CLI globally:

```sh
npm install -g @google/gemini-cli
```

Or with yarn:

```sh
yarn global add @google/gemini-cli
```

## 3. Get Your Gemini API Key

To use the Gemini CLI, you need a Gemini API key.

1. Go to [Google AI Studio](https://aistudio.google.com/app/apikey) and sign in with your Google account.
2. Create or view your Gemini API key.
3. Set the API key as an environment variable in your shell (preferred method):
   ```sh
   export GEMINI_API_KEY=your-api-key-here
   ```
   Or follow the CLI's instructions for configuring the API key if different.

**Keep your API key secure and do not share it publicly.**

## 4. Project Setup

Follow these steps to create a new project using a Gemini CLI assistant template:

1. **Clone this repository** somewhere outside your target project:
   ```sh
   git clone https://github.com/devkindhq/gemini-cli-assistants
   cd gemini-cli-assistants
   ```
2. **Create a folder for your Gemini CLI projects** (if you don't have one):
   ```sh
   mkdir -p ../gemini-cli-projects
   cd ../gemini-cli-projects
   ```
3. **Create a new project folder** (e.g., `shopify-redesign-proposal`):
   ```sh
   mkdir shopify-redesign-proposal
   cd shopify-redesign-proposal
   ```
4. **Copy an agent template**
   - Choose an agent from `gemini-cli-assistants/assistants/` (e.g., `sales-strategy`).
   - Copy the `GEMINI.md` file into your project root:
     ```sh
     cp ../gemini-cli-assistants/assistants/sales-strategy/GEMINI.md .
     ```
   - Copy the settings file into a `.gemini` folder:
     ```sh
     mkdir -p .gemini
     cp ../gemini-cli-assistants/assistants/sales-strategy/settings.json .gemini/settings.json
     ```

## 5. Project Structure Example

After following the setup steps, your project might look like this:

```
gemini-cli-projects/
└── shopify-redesign-proposal/
    ├── GEMINI.md
    └── .gemini/
        └── settings.json
```

- `GEMINI.md`: The agent template you copied.
- `.gemini/settings.json`: The configuration file for the Gemini CLI assistant.

## Usage

Once set up, run the Gemini CLI in your project directory to interact with your chosen assistant:

```sh
gemini
```

## Tips & Shortcuts

- Press the <kbd>Up Arrow</kbd> in the terminal to quickly access your previous Gemini CLI conversations.
- You can ask Gemini to write information directly into files, so you don’t have to copy-paste content manually.
- Type `/mcp` in the Gemini CLI to check which MCPs (Multi-Command Plugins) are available.
- Press <kbd>Ctrl</kbd>+<kbd>T</kbd> in the Gemini CLI to view details about each MCP—helpful for discovering what’s available and what’s working.

## Use Cases

Gemini CLI Assistants are versatile and can be used for a variety of collaboration and workflow scenarios:

- **Engineering, DevOps, QA, UI/UX, and more:**
  - Collaborate on technical projects, automate workflows, and streamline team communication.
  - *Advanced:* Initialize a git repository in your project folder to track changes, share knowledge, and collaborate with your team:
    ```sh
    git init
    git add .
    git commit -m "Initial commit"
    ```
- **Marketing, Sales, Project Management, etc.:**
  - For non-technical teams, simply place your project folder inside a shared drive (Google Drive, OneDrive, Dropbox, etc.).
  - Use the Gemini CLI from your desktop in that folder—no technical setup required. Desktop app versions of these drive services are available for easy access.

## Contributing

Contributions are welcome! Please open issues or pull requests for improvements or new agent templates.

## License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.