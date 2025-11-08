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
gem_echo_success "Hello, World!"
gem_echo_error "Something went wrong"
```

### Quick Examples

```bash
# Colored output
gem_echo_green "Success message"
gem_echo_red "Error message"
gem_echo_yellow "Warning message"

# String manipulation
gem_string_lower "HELLO WORLD"
echo $ZEN_FUNC_RESULT  # Output: hello world

# Random generation
gem_random_alphanumeric 8
echo $ZEN_FUNC_RESULT  # Output: aB3kX9mP

# File operations
gem_file_tmp_name
echo $ZEN_FUNC_RESULT  # Output: /tmp/gem-abc123.tmp

# Network operations
gem_net_download_url "https://example.com/file.txt" "./downloaded.txt"
```

## Function Reference

### Echo Functions (`gem_echo`)
- `gem_echo_red()`, `gem_echo_green()`, `gem_echo_yellow()`, `gem_echo_blue()`, `gem_echo_magenta()`, `gem_echo_cyan()` - Colored text output
- `gem_echo_h1()`, `gem_echo_h2()`, `gem_echo_h3()` - Header formatting
- `gem_echo_success()`, `gem_echo_error()`, `gem_echo_warning()` - Status messages
- `gem_echo_panic()` - Error message with exit
- `gem_echo_repeat()` - Repeat string multiple times

### String Functions (`gem_string`)
- `gem_string_beginswith()` - Check if string starts with prefix
- `gem_string_explode()` - Split string by delimiter
- `gem_string_lower()` - Convert to lowercase
- `gem_string_upper()` - Convert to uppercase
- `gem_string_replace_all()` - Replace all occurrences in string

### Random Functions (`gem_random`)
- `gem_random_int30()` - Generate random 30-bit integer
- `gem_random_string()` - Generate random string from character set
- `gem_random_alphanumeric()` - Generate alphanumeric string
- `gem_random_lowercase_alphanumeric()` - Generate lowercase alphanumeric
- `gem_random_uppercase_alphanumeric()` - Generate uppercase alphanumeric
- `gem_random_lowercase_alpha()` - Generate lowercase alphabetic
- `gem_random_uppercase_alpha()` - Generate uppercase alphabetic

### File Functions (`gem_file`)
- `gem_file_tmp_name()` - Generate unique temporary file name
- `gem_file_replace_string()` - Replace string in file
- `gem_file_read_content()` - Read file content safely
- `gem_file_setup_path_tmp()` - Setup temporary directory

### Assert Functions (`gem_assert`)
- `gem_assert_file_exist()` - Assert file exists
- `gem_assert_directory_exist()` - Assert directory exists

### Network Functions (`gem_net`)
- `gem_net_download_url()` - Download file with curl/wget fallback
- `gem_net_download_url_if_file_not_found()` - Conditional download

### Command Functions (`gem_command`)
- `gem_command_exist()` - Check if command exists

### Environment Functions (`gem_environment`)
- `gem_environment_detect()` - Auto-detect OS and distribution
- `gem_environment_display()` - Display environment information

### Update Functions (`gem_update`)
- `gem_update_from_github()` - Manual update from repository
- `gem_update_check_on_load()` - Automatic update check

### Erlang Functions (`gem_erlang`)
- `gem_erlang_random_short_node_name()` - Generate Erlang node name

## Configuration

### Environment Variables

- `ZEN_AUTO_UPDATE`: Enable automatic updates (`true` or `1`)
- `ZEN_PATH_TMP_PREFIX`: Prefix for temporary files (default: `gem`)
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
