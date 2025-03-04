# Bash AI Tools Collection

A collection of powerful bash scripts that leverage AI capabilities for various tasks. These scripts are designed to work together through Unix pipes, allowing for complex AI-powered workflows.

## Installation

1. Clone this repository
2. Add the `bin` directory to your PATH
3. Set up required environment variables:
   - `TARGON_API_KEY`: Your Targon API key for AI operations

## Available Scripts

### targon
The core AI interaction script that communicates with the Targon API.

```bash
targon [OPTIONS] [PROMPT]
```

Options:
- `-M, --model MODEL`: Specify model (default: deepseek-ai/DeepSeek-V3)
- `-T, --temp TEMP`: Set temperature (0.0-1.0, default: 0.7)
- `-F, --file FILE`: Read prompt from file
- `-O, --out-file FILE`: Write output to file
- `-W, --wipe`: Wipe output file before writing
- `-I, --include-prompt`: Include prompt in output
- `--max_tokens NUM`: Set maximum tokens (default: 256)
- `--top_p VALUE`: Set top_p value (default: 0.1)
- `--show`: Show prompt before response

### gitdiff
Analyzes git differences and provides AI-powered insights about the changes.

```bash
gitdiff [-s]
```

Options:
- `-s`: Save output to gitdiff.txt

### gitinit
Initializes a git repository with a comprehensive .gitignore file and creates an initial commit.

```bash
gitinit [commit message]
```

Features:
- Creates a comprehensive .gitignore file with common exclusions
- Initializes a git repository if one doesn't exist
- Adds all files and creates an initial commit
- Uses "initial commit" as the default message if none provided

### pyadd
Automates Python package installation and requirements.txt management.

```bash
pyadd <package_name>
```

Features:
- Installs the specified Python package using pip
- Updates requirements.txt with the exact installed version
- Removes any existing entries for the package before adding the new version
- Provides clear error messages if installation fails

### pyinit
Sets up a new Python project environment with all necessary components.

```bash
pyinit [filename]
```

Features:
- Creates a virtual environment (.venv) for isolated dependencies
- Generates an activation script (activate.sh) for easy environment activation
- Creates a main Python file (defaults to index.py if no filename provided)
- Creates an empty requirements.txt file for dependency management
- Provides clear instructions for next steps

### twitchchatdebate
Simulates Twitch chat reactions and discussions based on input content.

```bash
twitchchatdebate
```

Features:
- Processes input content and generates realistic Twitch chat-style discussions
- Uses predefined prompt templates for consistent output formatting
- Renders chat messages with appropriate formatting and structure
- Can be piped with other commands for complex workflows

### debate
Creates an AI-powered debate between two agents on any topic.

```bash
debate [EXCHANGES] [TOPIC] [OPTIONS]
```

Options:
- `-F1, --file1`: Custom prompt file for Agent 1
- `-F2, --file2`: Custom prompt file for Agent 2
- `-O1, --output1`: Output file for Agent 1's responses
- `-O2, --output2`: Output file for Agent 2's responses
- `-W, --wipe`: Wipe output files before starting
- `-I, --include-prompt`: Include prompts in both output files
- `-I1, --include-prompt1`: Include prompt in Agent 1's output
- `-I2, --include-prompt2`: Include prompt in Agent 2's output

### chatty
An interactive chat interface for AI interactions with persistent conversation history.

```bash
chatty
```

Features:
- Interactive command-line chat interface
- Maintains conversation history
- Supports system messages with `/system` prefix
- Color-coded output for better readability
- Exit with `quit`, `exit`, or `q`

### summarize
A sophisticated debate summarizer that extracts key insights and tracks discussion progression.

```bash
summarize
```

Features:
- Tracks debate rounds and provides per-round summaries
- Focuses on philosophical insights and practical implications
- Identifies main arguments and concepts
- Highlights areas of agreement/disagreement
- Real-time summary generation as the debate progresses

### nostream
Utility script for non-streaming AI responses.

### checkin
A utility script for checking in code changes with AI-assisted commit messages.

```bash
checkin
```

## Command Chaining Examples

These scripts can be chained together using Unix pipes for powerful workflows:

1. Analyze git changes and debate the implications:
```bash
gitdiff | debate 5 "these code changes"
```

2. Summarize a file and get AI insights:
```bash
cat file.txt | summarize | targon "What are the key insights?"
```

3. Generate content and analyze it:
```bash
targon "Write a story about AI" | summarize > summary.txt
```

4. Create a debate and get round-by-round summaries:
```bash
debate 3 "artificial intelligence ethics" | summarize > debate_summary.txt
```

5. Interactive chat with summary generation:
```bash
chatty | summarize > chat_insights.txt
```

6. Initialize a Python project and add dependencies:
```bash
pyinit app.py && pyadd requests
```

7. Generate Twitch-style chat reactions to content:
```bash
cat content.txt | twitchchatdebate
```

## Best Practices

1. Use `-W` when writing to files to avoid appending to existing content
2. Set appropriate temperature values for different tasks:
   - Lower (0.1-0.3) for analytical tasks
   - Higher (0.7-0.9) for creative tasks
3. Use the `--show` flag when debugging prompts
4. Chain commands with pipes for complex workflows
5. Use color-coded output for better readability in interactive sessions
6. Leverage system messages in chatty for context control

## Contributing

Feel free to contribute by:
1. Opening issues for bugs or feature requests
2. Submitting pull requests with improvements
3. Adding documentation or examples
4. Sharing interesting command chain combinations

## License

MIT License - See LICENSE file for details