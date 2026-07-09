# Setup DeepSeek V4 Pro with Visual Studio Code

This guide walks through configuring DeepSeek V4 Pro as your AI model in VS Code using CommandCode (`cmdc`).

## Prerequisites

- Visual Studio Code installed
- CommandCode extension installed in VS Code
- Node.js installed (for `cmdc` CLI)
- DeepSeek API key

## Step 1: Install CommandCode CLI (if not already installed)

```bash
npm install -g command-code
```

## Step 2: Set up the DeepSeek V4 Pro model globally

Set DeepSeek V4 Pro as the default model for all `cmdc` sessions:

```bash
cmdc --model deepseek-v4-pro
```

> **Note:** This command must be run directly in your terminal, not through scripts or pipes.

Alternatively, set the model via environment variable:

```bash
# Windows (CMD)
set CMDC_DEFAULT_MODEL=deepseek-v4-pro

# Windows (PowerShell)
$env:CMDC_DEFAULT_MODEL = "deepseek-v4-pro"
```

## Step 3: Configure API Key

Set your DeepSeek API key as an environment variable:

```bash
# Windows (CMD)
set DEEPSEEK_API_KEY=your-api-key-here

# Windows (PowerShell)
$env:DEEPSEEK_API_KEY = "your-api-key-here"
```

For persistent configuration, add the API key to your system environment variables via:
1. Open **System Properties** → **Advanced** → **Environment Variables**
2. Add a new **User Variable**:
   - Variable name: `DEEPSEEK_API_KEY`
   - Variable value: `your-api-key-here`

## Step 4: Configure VS Code Settings

Open VS Code settings (`Ctrl + ,`) and configure the CommandCode extension:

```json
{
  "commandcode.model": "deepseek-v4-pro",
  "commandcode.apiKey": "your-api-key-here"
}
```

Or set it per-project in `.vscode/settings.json`:

```json
{
  "commandcode.model": "deepseek-v4-pro"
}
```

## Step 5: Set Taste Preference (Optional)

To persist the model preference for a project, CommandCode learns from usage. You can also set it in `.commandcode/taste/taste.md`:

```markdown
# cli
- Use deepseek-v4-pro as the default model for cmdc sessions. Confidence: 0.90
```

## Step 6: Verify Setup

Open a terminal in VS Code and run:

```bash
cmdc --help
```

Then start a session:

```bash
cmdc
```

If everything is configured correctly, `cmdc` will use DeepSeek V4 Pro for all AI interactions within VS Code.

## Troubleshooting

| Issue | Solution |
|-------|----------|
| `cmdc` not found | Ensure `command-code` is installed globally or use `npx command-code` |
| Model not available | Check that your API key has access to `deepseek-v4-pro` |
| Config not applying | Restart VS Code or reload the window (`Ctrl + Shift + P` → `Developer: Reload Window`) |
