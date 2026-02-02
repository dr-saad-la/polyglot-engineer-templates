# Security Policy

## Reporting a Vulnerability

The security and integrity of this repository is important. If you discover a security vulnerability, please follow these guidelines:

### Please Do

✅ **Report privately** - Email security concerns to: dr.saad.laouadi@gmail.com

✅ **Provide details** - Include: 

- Description of the vulnerability
- Steps to reproduce
- Potential impact
- Suggested fix (if any)

✅ **Allow time for fix** - Give us reasonable time to address the issue before public disclosure

### Please Don't

❌ **Create public issues** - Don't open public GitHub issues for security vulnerabilities

❌ **Exploit the vulnerability** - Don't attempt to exploit the vulnerability beyond validating it exists

❌ **Disclose publicly** - Don't publicly disclose the vulnerability until we've had time to address it

## Supported Versions

We provide security updates for the following:

| Version | Supported          |
| ------- | ------------------ |
| 1.x.x   | :white_check_mark: |
| < 1.0   | :x:                |

## Response Timeline

- **Initial Response:** Within 48 hours
- **Status Update:** Within 7 days
- **Fix Timeline:** Depends on severity
  - Critical: Within 7 days
  - High: Within 14 days
  - Medium: Within 30 days
  - Low: Next release cycle

## Security Best Practices

When using templates from this repository:

### For Template Users

1. **Review before use** - Always review template contents before using in production
2. **Update regularly** - Keep templates updated to the latest version
3. **Secure credentials** - Never commit secrets, passwords, or API keys
4. **Validate inputs** - Validate and sanitize all user inputs
5. **Follow guidelines** - Follow security best practices for your specific technology stack

### For Contributors

1. **No hardcoded secrets** - Never include credentials in templates or examples
2. **Use placeholders** - Use placeholder values like `YOUR_API_KEY_HERE`
3. **Document security** - Document any security considerations in template README
4. **Safe defaults** - Ensure templates use secure defaults
5. **Dependency updates** - Keep dependencies in examples up to date

## Known Security Considerations

### Justfile Templates

- **Command injection** - Be careful when using variables in shell commands
- **Path traversal** - Validate paths when working with files
- **Execution** - Review recipes before running in production environments

**Example of safe variable usage:**
```bash
# Safe - variable is controlled
install:
    uv sync

# Potentially unsafe - external input
run INPUT:
    uv run python process.py {{INPUT}}  # Validate INPUT first!
```

### Docker Templates (Future)

- Always use specific version tags, not `latest`
- Run containers with least privilege
- Don't expose unnecessary ports
- Use multi-stage builds to minimize attack surface

### CI/CD Templates (Future)

- Use secrets management for credentials
- Limit permissions to minimum required
- Validate external inputs
- Use trusted actions/images only

## Scope

This security policy applies to:

- All templates in this repository
- Documentation and examples
- GitHub Actions workflows
- Scripts and automation

This policy does NOT cover:

- Third-party dependencies (report to respective projects)
- User implementations using these templates
- Forks of this repository

## Recognition

We appreciate responsible disclosure and will acknowledge security researchers who report valid vulnerabilities (with their permission).

## Questions?

If you have questions about this security policy, contact:
- **Email:** dr.saad.laouadi@gmail.com
- **GitHub:** [@dr-saad-la](https://github.com/dr-saad-la)

---

**Last Updated:** February 2024  
**Repository:** polyglot-engineer-templates