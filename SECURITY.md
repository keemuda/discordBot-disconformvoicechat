# Security Policy

## Supported Versions

This project is currently in active development. Security updates will be applied to the latest version.

| Version | Supported          |
| ------- | ------------------ |
| 1.0.x   | :white_check_mark: |

## Security Best Practices

### Environment Variables

This project uses environment variables to store sensitive information:
- `DISCORD_TOKEN` - Your Discord bot token
- `CLIENT_ID` - Your Discord application client ID

**Never commit these values to the repository.**

### Configuration Files

- ✅ `.env` is included in `.gitignore` to prevent accidental commits
- ✅ `.env.example` is provided as a template (contains no real secrets)
- ✅ All secrets are loaded via `dotenv` package

### Docker Security

When deploying with Docker:
- ✅ `.env` file is excluded in `.dockerignore`
- Use `--env-file .env` to pass environment variables at runtime
- Never build secrets into Docker images

### Token Management

1. **Rotate tokens immediately** if exposed
2. **Use different tokens** for development and production
3. **Store tokens securely** (use secret managers in production)
4. **Limit bot permissions** to only what's needed
5. **Monitor bot activity** regularly

## Reporting a Vulnerability

If you discover a security vulnerability in this project:

1. **DO NOT** open a public issue
2. Contact the repository owner directly
3. Provide detailed information about the vulnerability
4. Allow reasonable time for a fix before public disclosure

## Security Checklist for Contributors

Before committing code:
- [ ] No hardcoded tokens or API keys
- [ ] Environment variables used for all secrets
- [ ] No `.env` file committed
- [ ] `.env.example` updated if new variables added
- [ ] No sensitive data in logs or error messages
- [ ] Dependencies are up to date

## Audit Results

### Last Security Audit: 2026-02-07

✅ **No hardcoded secrets found**
✅ **No tokens in git history**
✅ **Proper use of environment variables**
✅ **`.env` properly ignored in git**
✅ **`.dockerignore` configured correctly**

This project follows security best practices for handling sensitive credentials.
