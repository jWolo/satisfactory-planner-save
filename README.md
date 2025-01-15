# Satisfactory Planner Save Tool

CLI tool for managing save files for the [Satisfactory Planner](https://satisfactory-planner.vercel.app/).

## Prerequisites

- Python 3.8 or higher
- Google Chrome browser
- Selenium - Chrome WebDriver (automatically managed)

## Installation

```bash
pip install .
```

## Usage

```bash
planner [OPTIONS]
```

NOTE: For the best results Chrome should be closed when using this tool!

The easiest way to use the tool on a single computer is to just use the --load and --save commands. These commands will save the files for you. You will see an interactive menu when loading files. 

Here are some examples:
```pwsh
PS C:\Dev\satisfactory-planner-save> planner --save
Enter filename to save (without .json extension): iron

DevTools listening on ws://127.0.0.1:53248/devtools/browser/bca25877-529e-47b2-8431-5fc9ec0b0595
Saved to C:\Users\jwolo\.planner\iron.json

//Clearing the plan
PS C:\Dev\WoloBotTools\satisfactory-planner-save> planner --clear

PS C:\Dev\satisfactory-planner-save> planner --save
Enter filename to save (without .json extension): iron

DevTools listening on ws://127.0.0.1:53248/devtools/browser/bca25877-529e-47b2-8431-5fc9ec0b0595
Saved to C:\Users\jwolo\.planner\iron.json

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

1. If Chrome fails to launch:
   - Ensure Chrome is installed
   - Check user data directory permissions
   - Verify profile directory exists

2. If saves fail:
   - Check write permissions
   - Ensure target directory exists

## License

Apache 2.0

## Author

jWolo (jwoose at gmail)
