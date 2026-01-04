# Contributing to IDM Activation Script (Tuanwara Edition)

Thank you for your interest in contributing to the **Tuanwara Edition** of the IDM Activation Script! This project aims to provide a stylish, futuristic, and error-free activation tool with a distinct Cyber Neon aesthetic.

This document provides guidelines and instructions for contributing to this specific repository.

## Table of Contents

- [Code of Conduct](#code-of-conduct)
- [How Can I Contribute?](#how-can-i-contribute)
- [Development Setup](#development-setup)
- [Coding Standards](#coding-standards)
- [Pull Request Process](#pull-request-process)
- [Reporting Bugs](#reporting-bugs)
- [Suggesting Enhancements](#suggesting-enhancements)

## Code of Conduct

This project follows a simple code of conduct:

- Be respectful and constructive
- Focus on what is best for the community
- Show empathy towards other community members
- Accept constructive criticism gracefully

## How Can I Contribute?

### Reporting Bugs

Before creating bug reports, please check existing issues to avoid duplicates. When creating a bug report, include:

- **Clear title** describing the issue
- **Detailed description** of the problem
- **Steps to reproduce** the behavior
- **Expected behavior** vs actual behavior
- **Environment details**:
  - Windows version and build number
  - System architecture (x86/x64/ARM64)
  - PowerShell version

**Example Bug Report:**

```markdown
## Bug: Script fails on Windows 11 ARM64

### Description
The script fails during registry scanning on Windows 11 ARM64 devices.

### Steps to Reproduce
1. Run IAS_Tuanwara.cmd as administrator
2. Select option [1] Activate IDM
3. Script crashes during registry scan

### Expected Behavior
Script should complete activation successfully with the Tuanwara UI intact.

### Environment
- Windows 11 Pro 23H2 (Build 22631.2861)
- ARM64 architecture
- PowerShell 7.4.0
```

### Suggesting Enhancements

Enhancement suggestions are welcome! Please provide:

- **Clear title** summarizing the enhancement
- **Detailed description** of the feature
- **Use case** explaining why it's useful
- **Implementation ideas** if you have any

### Code Contributions

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Make your changes
4. Test thoroughly on multiple Windows versions
5. Commit your changes (`git commit -m 'Add AmazingFeature'`)
6. Push to the branch (`git push origin feature/AmazingFeature`)
7. Open a Pull Request

## Development Setup

### Prerequisites

- Testing on Windows 10/11 recommended
- Text editor (VS Code, Notepad++, etc.)
- Important: Ensure your editor saves files with CRLF line endings (Windows format), not LF. The script contains checks that may fail if saved in UNIX format.

### Testing Your Changes

Before submitting, test on:

1. **Visual Check**: Ensure the ASCII logo and Neon colors display correctly without breaking lines.
2. **Functionality**: Test Activation, Freeze, and Reset options.
3. **Admin Rights**: Ensure the script correctly asks for Administrator privileges if run normally.

## Coding Standards

### 1. ASCII Art & Special Characters (Crucial)

To prevent syntax errors with special characters like `|`, `<`, `>`, please assign ASCII art to variables first and use **Delayed Expansion**. Do not `echo` them directly.

### ❌ Do NOT do this:
```batch
echo   | \ |  (This will crash the script because | is a pipe command)
```
### ✅ DO this instead:
```batch
set "L1=  | \ | "
call :_ascii %_Green% L1
```
### 2. Tuanwara Color Palette

Please use the pre-defined color variables to maintain the **Cyber Neon** theme consistency:

- `%_Cyan%` : Used for main borders and section headers.
- `%_Green%` : Used for the main ASCII logo and success messages.
- `%_Yellow%` : Used for menu options and interaction prompts.
- `%_Magenta%`: Used specifically for author branding (Tuanwara).
- `%_White%` : Used for standard description text.
- `%Red%` : Used for critical error messages.

### 3. Batch Script Style

```batch
:: Use clear, descriptive variable names
set "descriptive_name=value"

:: Comment complex sections
:: This section handles registry backup
call :backup_function

:: Group related operations with section markers
::========================================================================================================================================
```

### Pull Request Process

1. **Test Thoroughly**: Ensure all functionality works.
2. **Clear Description**: Explain what you changed and why.
3. **Small PRs**: Keep changes focused and manageable.

### Brief description of changes

```batch
## Type of Change
- [ ] Bug fix
- [ ] New feature (UI update, new option)
- [ ] Documentation update
- [ ] Code refactoring

## Checklist
- [ ] Code follows Tuanwara theme guidelines (Neon colors)
- [ ] ASCII art uses variable expansion method (no direct special chars)
- [ ] Tested on Windows 10/11
- [ ] No breaking changes
```

## Version Numbering

This project uses [Semantic Versioning](https://semver.org/).

Update version in:
- `IAS_Tuanwara.cmd` (line 1: `@set iasver=3.8`)
- `README.md` (Version History section)

## License

By contributing, you agree that your contributions will be licensed under the MIT License.

---

Thank you for contributing to **Tuanwara Edition! 🚀
