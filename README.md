# Task Master

### By [@eyaltoledano](https://x.com/eyaltoledano) & [@RalphEcom](https://x.com/RalphEcom)

\
A task management system for AI-driven development with Claude, designed to work seamlessly with Cursor AI.

## Requirements

- Anthropic API key (Claude API)
- OpenAI SDK (for Perplexity API integration, optional)

## Quick Start

### Option 1 | MCP (Recommended):

MCP (Model Control Protocol) provides the easiest way to get started with Task Master directly in your editor.

1. **Add the MCP config to your editor** (Cursor recommended, but it works with other text editors):

```json
{
	"mcpServers": {
		"taskmaster-ai": {
			"command": "npx",
			"args": ["-y", "--package", "task-master-ai", "task-master-mcp"],
			"env": {
				"ANTHROPIC_API_KEY": "YOUR_ANTHROPIC_API_KEY_HERE",
				"PERPLEXITY_API_KEY": "YOUR_PERPLEXITY_API_KEY_HERE",
				"MODEL": "claude-3-7-sonnet-20250219",
				"PERPLEXITY_MODEL": "sonar-pro",
				"MAX_TOKENS": 128000,
				"TEMPERATURE": 0.2,
				"DEFAULT_SUBTASKS": 5,
				"DEFAULT_PRIORITY": "medium"
			}
		}
	}
}
```

1. **Enable the MCP** in your editor
2. **Prompt the AI** to initialize Task Master:

```
Can you please initialize taskmaster-ai into my project?
```

1. **Use common commands** directly through your AI assistant:

```txt
Can you parse my PRD at scripts/prd.txt?
What's the next task I should work on?
Can you help me implement task 3?
Can you help me expand task 4?
```

### Option 2: Using Command Line

#### Installation

```bash
# Install globally
npm install -g task-master-ai

# OR install locally within your project
npm install task-master-ai
```

#### Initialize a new project

```bash
# If installed globally
task-master init

# If installed locally
npx task-master-init
```

This will prompt you for project details and set up a new project with the necessary files and structure.

#### Common Commands

```bash
# Initialize a new project
task-master init

# Parse a PRD and generate tasks
task-master parse-prd your-prd.txt

# List all tasks
task-master list

# Show the next task to work on
task-master next

# Generate task files
task-master generate
```

## Documentation

For more detailed information, check out the documentation in the `docs` directory:

- [Configuration Guide](docs/configuration.md) - Set up environment variables and customize Task Master
- [Tutorial](docs/tutorial.md) - Step-by-step guide to getting started with Task Master
- [Command Reference](docs/command-reference.md) - Complete list of all available commands
- [Task Structure](docs/task-structure.md) - Understanding the task format and features
- [Example Interactions](docs/examples.md) - Common Cursor AI interaction examples

## Troubleshooting

### If `task-master init` doesn't respond:

Try running it with Node directly:

```bash
node node_modules/claude-task-master/scripts/init.js
```

Or clone the repository and run:

```bash
git clone https://github.com/eyaltoledano/claude-task-master.git
cd claude-task-master
node scripts/init.js
```

## Licensing

Task Master is licensed under the MIT License with Commons Clause. This means you can:

✅ **Allowed**:

- Use Task Master for any purpose (personal, commercial, academic)
- Modify the code
- Distribute copies
- Create and sell products built using Task Master

❌ **Not Allowed**:

- Sell Task Master itself
- Offer Task Master as a hosted service
- Create competing products based on Task Master

See the [LICENSE](LICENSE) file for the complete license text and [licensing details](docs/licensing.md) for more information.