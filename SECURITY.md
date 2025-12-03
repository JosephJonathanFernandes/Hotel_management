# Security Policy

## Supported Versions

We take security seriously and are committed to ensuring the safety of this project. The following versions are currently being supported with security updates:

| Version | Supported          |
| ------- | ------------------ |
| main    | :white_check_mark: |
| < 1.0   | :x:                |

## Security Best Practices

This project implements the following security measures:

### Input Validation
- Buffer overflow protection with bounded string inputs
- Validation of user input before processing
- Safe use of `scanf` with field width specifiers

### File Handling
- Secure file operations with proper error checking
- Validation of file existence before operations
- Protection against path traversal attacks

### Memory Management
- Proper allocation and deallocation of dynamic memory
- NULL pointer checks before dereferencing
- Prevention of memory leaks

### Data Protection
- No hardcoded credentials or sensitive data
- Secure storage of customer information
- File-based data storage with appropriate permissions

## Known Security Considerations

### Current Limitations

1. **File System Security**: Customer data is stored in plain text files
   - Consider implementing encryption for sensitive data in production
   - Ensure proper file system permissions

2. **Input Sanitization**: While basic input validation is implemented
   - Additional sanitization may be needed for production use
   - Consider implementing more robust input validation

3. **Access Control**: No authentication mechanism
   - Suitable for single-user local systems
   - Consider adding user authentication for multi-user environments

## Reporting a Vulnerability

**Please do not report security vulnerabilities through public GitHub issues.**

If you discover a security vulnerability, please follow these steps:

### 1. Contact

Send a detailed report to the project maintainer via:
- GitHub: Create a [Security Advisory](https://github.com/JosephJonathanFernandes/Hotel_management/security/advisories/new)
- Email: Contact via GitHub profile

### 2. Information to Include

Please include as much of the following information as possible:

- Type of vulnerability
- Full paths of source file(s) related to the vulnerability
- Location of the affected source code (tag/branch/commit or direct URL)
- Step-by-step instructions to reproduce the issue
- Proof-of-concept or exploit code (if possible)
- Impact of the vulnerability, including how an attacker might exploit it
- Any potential solutions you've identified

### 3. Response Timeline

- **Initial Response**: Within 48 hours of report submission
- **Status Update**: Within 7 days with assessment of the vulnerability
- **Resolution**: Security patches will be prioritized
  - Critical: Within 7 days
  - High: Within 30 days
  - Medium: Within 60 days
  - Low: Within 90 days

### 4. Disclosure Policy

- We request that you do not publicly disclose the vulnerability until we've had a chance to address it
- We will acknowledge your contribution in the security advisory and release notes
- We follow responsible disclosure practices

## Security Update Process

When a security vulnerability is identified:

1. **Assessment**: Severity and impact analysis
2. **Development**: Create and test a fix
3. **Testing**: Thorough testing of the security patch
4. **Release**: Deploy the fix and notify users
5. **Disclosure**: Publish security advisory with details

## Security Checklist for Contributors

When contributing to this project, please ensure:

- [ ] No hardcoded credentials or API keys
- [ ] Input validation is implemented
- [ ] Buffer sizes are checked
- [ ] File operations include error handling
- [ ] Memory is properly allocated and freed
- [ ] No SQL injection vulnerabilities (if database is added)
- [ ] No command injection vulnerabilities
- [ ] Sensitive data is not logged
- [ ] Dependencies are up to date (if any)

## GitGuardian Compliance

This project follows GitGuardian best practices:

### Secrets Detection
- No API keys, tokens, or credentials in code
- No database passwords in source files
- No private keys committed to repository

### Code Security
- Regular security audits of dependencies
- Automated scanning for vulnerabilities
- Clean commit history without sensitive data

### Best Practices
- `.gitignore` properly configured to exclude sensitive files
- Environment variables used for configuration (when applicable)
- Secure coding standards followed

## Security Tools

We recommend using the following tools:

- **GitGuardian**: For secrets detection
- **Valgrind**: For memory leak detection
- **Static Analysis**: Tools like `cppcheck` for code analysis
- **Compiler Warnings**: Always compile with `-Wall -Wextra`

## Security Resources

- [OWASP C/C++ Security Guidelines](https://owasp.org/)
- [CWE - Common Weakness Enumeration](https://cwe.mitre.org/)
- [CERT C Coding Standard](https://wiki.sei.cmu.edu/confluence/display/c)

## Acknowledgments

We appreciate the security research community's efforts in responsibly disclosing vulnerabilities. Contributors who report valid security issues will be acknowledged in:

- Security advisories
- Release notes
- Project documentation

## Questions

For questions about this security policy, please open a discussion on GitHub or contact the maintainer.

---

**Last Updated**: December 3, 2025
