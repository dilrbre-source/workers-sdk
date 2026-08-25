# Security Policy

## Secrets Management

### Required Secrets for Workflows

This repository uses GitHub Actions with the following required secrets:

#### 1. Datadog Synthetics Testing
- **DD_API_KEY** - Datadog API Key for authentication
- **DD_APP_KEY** - Datadog Application Key for access

**How to add:**
1. Go to Repository Settings → Secrets and variables → Actions
2. Click "New repository secret"
3. Add the keys with exact names as shown above

**How to get Datadog keys:**
- Visit https://app.datadoghq.com/account/login (or your Datadog region)
- Navigate to Account → API Keys
- Create or copy your API and Application keys

### Security Best Practices

1. **Never commit secrets** to the repository
2. **Rotate keys** regularly
3. **Use least privilege** - limit API key permissions
4. **Monitor usage** - check Datadog audit logs
5. **Update actions** - keep GitHub Actions up to date

## Workflow Status

- ✅ Semgrep OSS scan - Code security scanning
- 🔄 Datadog Synthetics - E2E testing (requires secrets)
- ✅ Handle Changesets - Changelog management
- ✅ Prerelease - Automated releases

## Issues or Questions?

If you encounter issues with workflows:
1. Check the Actions tab for logs
2. Verify all required secrets are configured
3. Review the workflow files in `.github/workflows/`
4. See the troubleshooting guide below

### Troubleshooting

**"Missing API or APP keys" error:**
- Ensure `DD_API_KEY` and `DD_APP_KEY` are added to GitHub Secrets
- Verify the keys are for the correct Datadog organization
- Test keys in Datadog console first

**Workflow timeout:**
- Default timeout is 20 minutes
- For E2E tests, increase `DATADOG_SYNTHETICS_TIMEOUT` if needed

---

**Last Updated:** August 25, 2026
**Maintenance:** dilrbre-source
