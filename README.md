# Satisfactory Planner Save Tool
CLI tool for managing save files for the [Satisfactory Planner](https://satisfactory-planner.vercel.app/).

First, I have no affiliation with the creator of https://satisfactory-planner.vercel.app/. I just made this tool for me. I really like laying out my big factories with this tool, but I got tired of not being able to save or load my layouts. Deleting all of the nodes became tedious. This is a hacky solution and is not ideal, but it works. I'm using selenium to modify browser localStorage. The tool currently only works in Chrome. If there is interest, I can add Firefox support Let me know what you think.

## Prerequisites

- Python 3.8 or higher
- Google Chrome browser
- Selenium - Chrome WebDriver (automatically managed)

## Installation

```bash
pip install satisfactory-planner-save
```

## Usage

```bash
planner [OPTIONS]
```

NOTE: For the best results Chrome should be closed when using this tool! The defaults are for Windows since Satisfactory is a Windows game. If you configure it correctly this should still work on Mac OS.

The easiest way to use the tool on a single computer is to just use the --load and --save commands. These commands will save the files for you. You will see an interactive menu when saving and loading files.

Here are some examples:
```pwsh
PS C:\Dev\satisfactory-planner-save> planner --save
Enter filename to save (without .json extension): iron

DevTools listening on ws://127.0.0.1:53248/devtools/browser/bca25877-529e-47b2-8431-5fc9ec0b0595
Saved to C:\Users\jwolo\.planner\iron.json

# Clearing the plan
PS C:\Dev\satisfactory-planner-save> planner --clear

PS C:\Dev\satisfactory-planner-save> planner --save
Enter filename to save (without .json extension): big_iron_plan

DevTools listening on ws://127.0.0.1:53248/devtools/browser/bca25877-529e-47b2-8431-5fc9ec0b0595
Saved to C:\Users\jwolo\.planner\big_iron_plans.json

PS C:\Dev\satisfactory-planner-save> planner --load

Available files:
1. big_iron_plan.json
2. iron.json

Choose a file number to load (or 0 to cancel): 2
```

### Options

- `--load`: Load a file from the `.planner` directory (interactive).
- `--load_file <path>`: Load a specific file from the given path.
- `--save`: Save the current planner to the `.planner` directory.
- `--save_file <path>`: Save the current planner to the specified path.
- `--clear`: Clear planner data.
- `--user-data-dir <path>`: Set Chrome user data directory.
- `--profile-directory <name>`: Set Chrome profile directory.

### Examples

Load a file interactively:
```bash
planner --load
```

Load a specific file:
```bash
planner --load_file /path/to/file.json
```

Save the current planner interactively:
```bash
planner --save
```

Save the current planner to a specific path:
```bash
planner --save_file /path/to/save.json
```

Clear planner data:
```bash
planner --clear
```

Set Chrome profile:
```bash
planner --user-data-dir "C:/Users/YourUser/AppData/Local/Google/Chrome/User Data" --profile-directory "Default"
```

## Configuration

The tool stores configuration in `~/.planner/config.json`. You can set:
- Chrome user data directory
- Chrome profile directory

## Troubleshooting

1. If you get an error message:
   - Make sure you close Chrome when using the tool.

## License

Apache 2.0

## Author

jWolo (jwoose at gmail)

## Note

Let me know if you need help. I'm happy to assist. I'll update this guide accordingly.
