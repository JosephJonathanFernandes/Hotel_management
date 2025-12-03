# Contributing to Hotel Management System

First off, thank you for considering contributing to the Hotel Management System! It's people like you that make this project better for everyone.

## Table of Contents

- [Code of Conduct](#code-of-conduct)
- [How Can I Contribute?](#how-can-i-contribute)
  - [Reporting Bugs](#reporting-bugs)
  - [Suggesting Enhancements](#suggesting-enhancements)
  - [Pull Requests](#pull-requests)
- [Development Setup](#development-setup)
- [Style Guidelines](#style-guidelines)
  - [Git Commit Messages](#git-commit-messages)
  - [C Coding Standards](#c-coding-standards)
- [Additional Notes](#additional-notes)

## Code of Conduct

This project and everyone participating in it is governed by our [Code of Conduct](CODE_OF_CONDUCT.md). By participating, you are expected to uphold this code.

## How Can I Contribute?

### Reporting Bugs

Before creating bug reports, please check the existing issues to avoid duplicates. When you create a bug report, include as many details as possible:

- **Use a clear and descriptive title**
- **Describe the exact steps to reproduce the problem**
- **Provide specific examples to demonstrate the steps**
- **Describe the behavior you observed and what behavior you expected**
- **Include screenshots if relevant**
- **Include your environment details** (OS, compiler version, etc.)

**Bug Report Template:**

```markdown
**Describe the bug**
A clear description of what the bug is.

**To Reproduce**
Steps to reproduce the behavior:
1. Go to '...'
2. Click on '...'
3. Enter '...'
4. See error

**Expected behavior**
A clear description of what you expected to happen.

**Screenshots**
If applicable, add screenshots.

**Environment:**
 - OS: [e.g., Windows 10, Ubuntu 22.04]
 - Compiler: [e.g., GCC 11.2.0]
 - Version: [e.g., commit hash]

**Additional context**
Add any other context about the problem.
```

### Suggesting Enhancements

Enhancement suggestions are tracked as GitHub issues. When creating an enhancement suggestion, include:

- **Use a clear and descriptive title**
- **Provide a detailed description of the suggested enhancement**
- **Explain why this enhancement would be useful**
- **List any alternatives you've considered**

**Enhancement Template:**

```markdown
**Is your feature request related to a problem?**
A clear description of the problem.

**Describe the solution you'd like**
A clear description of what you want to happen.

**Describe alternatives you've considered**
Alternative solutions or features you've considered.

**Additional context**
Any other context, screenshots, or mockups.
```

### Pull Requests

1. **Fork the repository** and create your branch from `main`
2. **Make your changes** following the style guidelines
3. **Test your changes** thoroughly
4. **Update documentation** if needed
5. **Commit your changes** with clear commit messages
6. **Push to your fork** and submit a pull request

**Pull Request Process:**

1. Ensure any install or build dependencies are removed
2. Update the README.md with details of changes if applicable
3. Increase version numbers in any examples files and README.md
4. Your PR will be merged once you have approval from maintainers

**Pull Request Template:**

```markdown
## Description
Brief description of changes

## Type of Change
- [ ] Bug fix (non-breaking change)
- [ ] New feature (non-breaking change)
- [ ] Breaking change (fix or feature that would cause existing functionality to change)
- [ ] Documentation update

## Testing
Describe the tests you ran and how to reproduce them

## Checklist
- [ ] My code follows the project's style guidelines
- [ ] I have performed a self-review of my code
- [ ] I have commented my code where necessary
- [ ] I have updated the documentation accordingly
- [ ] My changes generate no new warnings
- [ ] I have tested my changes thoroughly
```

## Development Setup

1. **Clone the repository**
   ```bash
   git clone https://github.com/JosephJonathanFernandes/Hotel_management.git
   cd Hotel_management
   ```

2. **Compile the project**
   ```bash
   gcc -o hotel_management HotelManagement.c -I.
   ```

3. **Run tests** (if applicable)
   ```bash
   ./hotel_management
   ```

## Style Guidelines

### Git Commit Messages

- Use the present tense ("Add feature" not "Added feature")
- Use the imperative mood ("Move cursor to..." not "Moves cursor to...")
- Limit the first line to 72 characters or less
- Reference issues and pull requests liberally after the first line
- Consider starting the commit message with an applicable emoji:
  - 🎨 `:art:` - Improving structure/format of the code
  - ⚡ `:zap:` - Improving performance
  - 🐛 `:bug:` - Fixing a bug
  - ✨ `:sparkles:` - Introducing new features
  - 📝 `:memo:` - Writing docs
  - 🔒 `:lock:` - Fixing security issues
  - ♻️ `:recycle:` - Refactoring code
  - ✅ `:white_check_mark:` - Adding tests
  - 🔧 `:wrench:` - Changing configuration files

**Example:**
```
✨ Add customer search functionality

- Implement search by customer ID
- Add search by customer name
- Update display function to show search results

Fixes #123
```

### C Coding Standards

1. **Indentation**: Use 4 spaces (no tabs)

2. **Naming Conventions**:
   - Functions: `camelCase` or `snake_case`
   - Variables: `camelCase` or `snake_case`
   - Constants: `UPPER_CASE`
   - Structs: `snake_case` or `PascalCase`

3. **Comments**:
   - Use `//` for single-line comments
   - Use `/* */` for multi-line comments
   - Document all functions with purpose, parameters, and return values

4. **Function Documentation**:
   ```c
   /**
    * Brief description of function
    * 
    * @param fp File pointer to customer data
    * @return 0 on success, -1 on failure
    */
   int functionName(FILE *fp) {
       // Implementation
   }
   ```

5. **Error Handling**:
   - Always check return values
   - Provide meaningful error messages
   - Clean up resources (free memory, close files)

6. **Memory Management**:
   - Always free dynamically allocated memory
   - Use `malloc`/`free` appropriately
   - Check for NULL pointers

7. **File Handling**:
   - Always check if file operations succeed
   - Close files after use
   - Use appropriate file modes

## Additional Notes

### Issue and Pull Request Labels

- `bug` - Something isn't working
- `enhancement` - New feature or request
- `documentation` - Improvements or additions to documentation
- `good first issue` - Good for newcomers
- `help wanted` - Extra attention is needed
- `question` - Further information is requested
- `wontfix` - This will not be worked on
- `duplicate` - This issue or PR already exists
- `invalid` - This doesn't seem right

### Security Issues

**Do not** open issues for security vulnerabilities. Instead, please see [SECURITY.md](SECURITY.md) for instructions on how to report security issues.

### Recognition

Contributors will be recognized in:
- The project README
- Release notes
- GitHub contributor graph

## Questions?

Feel free to open an issue with the `question` label if you have any questions about contributing!

---

Thank you for contributing to the Hotel Management System! 🎉
