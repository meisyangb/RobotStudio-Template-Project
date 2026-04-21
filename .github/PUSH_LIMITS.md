# Push Limits and Restrictions

This document defines the push limits, restrictions, and policies for the RobotStudio Template Project repository.

## Push Size Limits

### Maximum File Sizes

| File Type | Maximum Size | Notes |
|-----------|--------------|-------|
| RobotStudio Station (.rsstn) | 100 MB | Large station files should be compressed |
| Library Files (.rslib) | 50 MB | Split large libraries if necessary |
| RAPID Modules (.mod) | 1 MB | Split large modules |
| Configuration Files (.cfg) | 10 MB | Optimize configuration data |
| Images/Videos | 25 MB | Use external storage for large media |
| Other Files | 10 MB | General limit for other file types |

### Repository Size Limits

- **Single Push**: Maximum 500 MB per push
- **Total Repository**: Recommended under 1 GB
- **History Depth**: Keep commit history under 1000 commits

## Push Frequency Limits

### Rate Limiting

- **Normal Pushes**: No limit for standard development
- **Large File Pushes**: Maximum 5 large file pushes per hour
- **Force Pushes**: Maximum 3 force pushes per day (requires justification)

### Automated Pushes

- **CI/CD Pushes**: Must use dedicated service account
- **Scheduled Pushes**: Maximum 1 per hour
- **Bulk Updates**: Must be approved by maintainer

## Branch Protection Rules

### Protected Branches

#### `main` Branch

The following restrictions apply to the `main` branch:

- ✅ **Require pull request reviews**: At least 1 approval required
- ✅ **Require status checks**: All CI checks must pass
- ✅ **Require up-to-date branches**: Branches must be up to date before merging
- ✅ **Require linear history**: No merge commits allowed
- ✅ **Include administrators**: Rules apply to admins too
- ❌ **Allow force pushes**: Disabled
- ❌ **Allow deletions**: Disabled

#### `develop` Branch

- ✅ **Require pull request reviews**: At least 1 approval required
- ✅ **Require status checks**: CI checks must pass
- ❌ **Require up-to-date branches**: Recommended but not enforced
- ❌ **Require linear history**: Merge commits allowed
- ❌ **Include administrators**: Rules don't apply to admins
- ❌ **Allow force pushes**: Disabled
- ❌ **Allow deletions**: Disabled

## Commit Restrictions

### Commit Message Validation

All commits must follow the conventional commit format:

```
<type>(<scope>): <subject>

<body>

<footer>
```

#### Allowed Types

- `feat` - New features
- `fix` - Bug fixes
- `docs` - Documentation
- `style` - Code style
- `refactor` - Refactoring
- `perf` - Performance
- `test` - Tests
- `chore` - Maintenance

#### Commit Message Length

- **Subject Line**: Maximum 50 characters
- **Body Lines**: Maximum 72 characters
- **Total Message**: Maximum 1000 characters

### Commit Content Restrictions

#### Prohibited Content

- ❌ Binary files without justification
- ❌ Sensitive data (passwords, keys, tokens)
- ❌ Personal information
- ❌ Copyrighted material without permission
- ❌ Malicious code
- ❌ Large generated files

#### Required Content

- ✅ Meaningful commit messages
- ✅ Reference to related issues (if applicable)
- ✅ Signed commits (recommended)

## File Type Restrictions

### Allowed File Types

#### RobotStudio Files

- `.rsstn` - Station files
- `.rssln` - Solution files
- `.rslib` - Library files
- `.mod` - RAPID modules
- `.cfg` - Configuration files
- `.sys` - System files
- `.txt` - Text files

#### Documentation Files

- `.md` - Markdown files
- `.pdf` - PDF documents
- `.docx` - Word documents (limited)

#### Code Files

- `.py` - Python scripts
- `.cs` - C# files
- `.json` - JSON files
- `.xml` - XML files
- `.yaml`, `.yml` - YAML files

### Restricted File Types

#### Blocked Extensions

- `.exe` - Executables
- `.dll` - Libraries
- `.bat` - Batch files (security risk)
- `.sh` - Shell scripts (review required)
- `.zip`, `.rar`, `.7z` - Archives (use Git LFS)
- `.iso`, `.img` - Disk images

#### Review Required

- `.ps1` - PowerShell scripts
- `.js` - JavaScript files
- `.html`, `.htm` - HTML files
- Any file > 10 MB

## User Permission Levels

### Access Control

| Role | Push to Main | Push to Develop | Create Branches | Merge PRs | Admin |
|------|--------------|-----------------|-----------------|-----------|-------|
| Owner | ❌ (PR only) | ✅ | ✅ | ✅ | ✅ |
| Maintainer | ❌ (PR only) | ✅ | ✅ | ✅ | ❌ |
| Developer | ❌ | ✅ | ✅ | ❌ | ❌ |
| Contributor | ❌ | ❌ | ✅ (fork) | ❌ | ❌ |
| Viewer | ❌ | ❌ | ❌ | ❌ | ❌ |

### Branch Permissions

- **Main Branch**: Pull request only, 2 reviews required
- **Develop Branch**: Pull request only, 1 review required
- **Feature Branches**: Free push access for assigned developers
- **Hotfix Branches**: Maintainer access only

## Push Validation

### Pre-Push Checks

The following checks run before allowing a push:

1. **File Size Check**: Reject files > 100 MB
2. **File Type Check**: Reject blocked file types
3. **Secret Scanning**: Detect potential secrets
4. **Vulnerability Scan**: Check for known vulnerabilities
5. **Code Quality**: Lint and format checks
6. **Commit Message**: Validate commit message format

### Post-Push Actions

After a successful push:

1. **CI/CD Pipeline**: Trigger automated tests
2. **Code Analysis**: Run static analysis
3. **Notification**: Notify relevant team members
4. **Documentation**: Update documentation if needed

## Enforcement

### Automatic Enforcement

- Push restrictions are enforced by GitHub settings
- Pre-commit hooks validate commit messages
- CI/CD pipeline validates code quality
- Automated tools scan for prohibited content

### Manual Review

The following require manual review:

- Force pushes to protected branches
- Large file additions (> 50 MB)
- Changes to protected files
- Modifications to CI/CD configuration
- Security-related changes

## Violations

### Consequences

| Violation | First Offense | Second Offense | Third Offense |
|-----------|---------------|----------------|---------------|
| Invalid commit message | Warning | Push block | Temporary ban |
| Large file push | Warning + Rejection | Push block | Temporary ban |
| Force push to protected | Reversal + Warning | Temporary ban | Permanent ban |
| Security violation | Immediate ban | - | - |

### Reporting

Report push policy violations by:

1. Creating an issue with label `policy-violation`
2. Contacting repository maintainers
3. Using the security reporting process for security issues

## Exceptions

### Emergency Procedures

In case of emergencies:

1. Contact repository owner directly
2. Provide justification for exception
3. Exception will be reviewed within 24 hours
4. All exceptions are logged

### Maintenance Windows

- Scheduled maintenance: Announced 48 hours in advance
- Temporary relaxed restrictions during maintenance
- Emergency maintenance: Immediate notification

## Updates

This policy is reviewed quarterly. Updates will be:

1. Discussed in team meetings
2. Documented in this file
3. Announced via repository notifications
4. Versioned with date stamps

---

**Last Updated**: 2026-04-21
**Version**: 1.0
**Next Review**: 2026-07-21

For questions about push limits, please contact the repository maintainers.
