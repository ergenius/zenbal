# zenbal
**ZEN BAsh Library** - A comprehensive Bash utility library

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Bash](https://img.shields.io/badge/Bash-4.0%2B-brightgreen.svg)](https://www.gnu.org/software/bash/)

The ZEN BAsh Library (zenbal) is a feature-rich bash script that acts as a utility library for other bash scripts. It provides a comprehensive set of functions that make shell scripting more efficient, readable, and maintainable.

## Features

- **Colored Output**: Beautiful colored terminal output with various formatting options
- **String Manipulation**: Comprehensive string processing utilities
- **Random Generation**: Generate random numbers, strings, and identifiers
- **File Operations**: Safe file handling and manipulation functions
- **Network Utilities**: Download files with automatic fallback (curl/wget)
- **Environment Detection**: Automatic OS and distribution detection
- **Auto-Update**: Automatic library updates from GitHub repository
- **Assert Functions**: File and directory validation utilities
- **Erlang Support**: Specialized functions for Erlang development

## Installation

### Manual Installation

Download zenbal directly from the repository:

```bash
# Download the latest version
curl -O https://raw.githubusercontent.com/ergenius/zenbal/main/zenbal

# Make it executable
chmod +x zenbal
```

### Auto-Update Feature

Enable automatic updates by setting the environment variable:

```bash
export ZEN_AUTO_UPDATE=true
# or
export ZEN_AUTO_UPDATE=1
```

## Usage

### Basic Usage

Include zenbal in your bash script:

```bash
#!/bin/bash

# Source the zenbal library
source ./zenbal

# Now you can use zenbal functions
zen_echo_success "Hello, World!"
zen_echo_error "Something went wrong"
```

### Quick Examples

```bash
# Colored output
zen_echo_green "Success message"
zen_echo_red "Error message"
zen_echo_yellow "Warning message"

# String manipulation
zen_string_lower "HELLO WORLD"
echo $ZEN_FUNC_RESULT  # Output: hello world

# Random generation
zen_random_alphanumeric 8
echo $ZEN_FUNC_RESULT  # Output: aB3kX9mP

# File operations
zen_file_tmp_name
echo $ZEN_FUNC_RESULT  # Output: /tmp/zen-abc123.tmp

# Network operations
zen_net_download_url "https://example.com/file.txt" "./downloaded.txt"
```

## Function Reference

### Echo Functions (`zen_echo`)
- `zen_echo_red()`, `zen_echo_green()`, `zen_echo_yellow()`, `zen_echo_blue()`, `zen_echo_magenta()`, `zen_echo_cyan()` - Colored text output
- `zen_echo_h1()`, `zen_echo_h2()`, `zen_echo_h3()` - Header formatting
- `zen_echo_success()`, `zen_echo_error()`, `zen_echo_warning()` - Status messages
- `zen_echo_panic()` - Error message with exit
- `zen_echo_repeat()` - Repeat string multiple times

### String Functions (`zen_string`)
- `zen_string_beginswith()` - Check if string starts with prefix
- `zen_string_explode()` - Split string by delimiter
- `zen_string_lower()` - Convert to lowercase
- `zen_string_upper()` - Convert to uppercase
- `zen_string_replace_all()` - Replace all occurrences in string

### Random Functions (`zen_random`)
- `zen_random_int30()` - Generate random 30-bit integer
- `zen_random_string()` - Generate random string from character set
- `zen_random_alphanumeric()` - Generate alphanumeric string
- `zen_random_lowercase_alphanumeric()` - Generate lowercase alphanumeric
- `zen_random_uppercase_alphanumeric()` - Generate uppercase alphanumeric
- `zen_random_lowercase_alpha()` - Generate lowercase alphabetic
- `zen_random_uppercase_alpha()` - Generate uppercase alphabetic

### File Functions (`zen_file`)
- `zen_file_tmp_name()` - Generate unique temporary file name
- `zen_file_replace_string()` - Replace string in file
- `zen_file_read_content()` - Read file content safely
- `zen_file_setup_path_tmp()` - Setup temporary directory

### Assert Functions (`zen_assert`)
- `zen_assert_file_exist()` - Assert file exists
- `zen_assert_directory_exist()` - Assert directory exists

### Network Functions (`zen_net`)
- `zen_net_download_url()` - Download file with curl/wget fallback
- `zen_net_download_url_if_file_not_found()` - Conditional download

### Command Functions (`zen_command`)
- `zen_command_exist()` - Check if command exists

### Environment Functions (`zen_environment`)
- `zen_environment_detect()` - Auto-detect OS and distribution
- `zen_environment_display()` - Display environment information

### Update Functions (`zen_update`)
- `zen_update_from_github()` - Manual update from repository
- `zen_update_check_on_load()` - Automatic update check

### Erlang Functions (`zen_erlang`)
- `zen_erlang_random_short_node_name()` - Generate Erlang node name

## Configuration

### Environment Variables

- `ZEN_AUTO_UPDATE`: Enable automatic updates (`true` or `1`)
- `ZEN_PATH_TMP_PREFIX`: Prefix for temporary files (default: `zen`)
- `ZEN_PATH_TMP`: Custom temporary directory path

### Return Values

Many functions return their results in the global variable `ZEN_FUNC_RESULT`. Always check this variable after calling functions that return values.

## Supported Platforms

- Linux (Red Hat, Debian, SUSE, Mandrake)
- macOS
- Other Unix-like systems (with limited support)

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## Support

If you encounter any issues or have questions, please [open an issue](https://github.com/ergenius/zenbal/issues) on GitHub.
