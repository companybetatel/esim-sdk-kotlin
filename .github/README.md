# GitHub Actions & Release Documentation

This directory contains GitHub Actions workflows and documentation for automated building, testing, and publishing of the Betatel eSIM Kotlin SDK.

## Files Overview

### Workflows

#### 📋 `workflows/build.yml`
**Purpose**: Continuous Integration - builds and tests on every push and PR

**Triggers**:
- Push to `master`, `main`, or `develop` branches
- Pull requests to `master`, `main`, or `develop` branches
- Manual workflow dispatch

**What it does**:
1. Builds the project with Gradle
2. Runs all unit tests (175 tests)
3. Generates Javadoc documentation
4. Verifies artifacts are created correctly
5. Uploads build artifacts and test reports

**Status Badge** (add to main README.md):
```markdown
![Build Status](https://github.com/betatel/esim-sdk-kotlin/actions/workflows/build.yml/badge.svg)
```

---

#### 🚀 `workflows/publish.yml`
**Purpose**: Automated Publishing - publishes to Maven Central when you create a version tag

**Triggers**:
- Push tags matching `v*.*.*` (e.g., `v1.0.0`, `v1.0.1`, `v2.0.0`)
- Manual workflow dispatch

**What it does**:
1. Extracts version from git tag
2. Updates version in build.gradle
3. Builds and tests the project
4. Signs artifacts with GPG
5. Publishes to Maven Central (Sonatype OSSRH)
6. Creates a GitHub Release with:
   - Release notes
   - All JAR files
   - Installation instructions

**Required Secrets**: See [SECRETS_SETUP.md](./SECRETS_SETUP.md)

---

### Documentation

#### 📖 `RELEASE.md`
**Comprehensive release process guide** covering:
- Prerequisites for releasing
- Step-by-step release instructions
- Version numbering guidelines
- Troubleshooting common issues
- Manual release procedures
- Post-release checklist

👉 **Read this before your first release!**

---

#### 🔐 `SECRETS_SETUP.md`
**Detailed guide for setting up GitHub Secrets** including:
- How to get Sonatype OSSRH credentials
- How to generate and export GPG keys
- Where to add secrets in GitHub
- Verification checklist
- Troubleshooting secrets issues
- Security best practices

👉 **Complete this setup before attempting to publish!**

---

## Quick Start

### For Contributors (CI/CD)

No setup needed! The build workflow runs automatically on every push and PR.

### For Maintainers (Publishing)

1. **First time setup** (once):
   - Follow [SECRETS_SETUP.md](./SECRETS_SETUP.md) to configure GitHub Secrets
   - Verify secrets are added in: `Settings → Secrets and variables → Actions`

2. **To release a new version**:
   ```bash
   # Update version in build.gradle
   version '1.0.2'

   # Commit and push
   git add build.gradle
   git commit -m "Prepare release v1.0.2"
   git push origin master

   # Create and push tag
   git tag -a v1.0.2 -m "Release version 1.0.2"
   git push origin v1.0.2
   ```

3. **Monitor the release**:
   - Go to the **Actions** tab in GitHub
   - Watch the "Publish to Maven Central" workflow
   - Check GitHub Releases page after completion
   - Wait 15-30 minutes for Maven Central sync

---

## Required GitHub Secrets

Before publishing, configure these 4 secrets:

| Secret Name | Description |
|-------------|-------------|
| `OSSRH_USERNAME` | Your Sonatype OSSRH username |
| `OSSRH_PASSWORD` | Your Sonatype OSSRH password or token |
| `SIGNING_KEY` | Your GPG private key (ASCII-armored) |
| `SIGNING_PASSWORD` | Your GPG key passphrase |

See [SECRETS_SETUP.md](./SECRETS_SETUP.md) for detailed instructions.

---

## Workflow Diagram

```
┌─────────────────────────────────────────────────────────────┐
│                    Developer Workflow                        │
└─────────────────────────────────────────────────────────────┘

   Code Changes
        │
        ├─────────── Push to branch ──────────┐
        │                                      │
        │                                      ▼
        │                            ┌──────────────────┐
        │                            │   build.yml      │
        │                            │  (Build & Test)  │
        │                            └──────────────────┘
        │                                      │
        │                                      ├─── Build
        │                                      ├─── Test
        │                                      └─── Report
        │
        └─────────── Create Tag (v1.0.x) ────┐
                                              │
                                              ▼
                                    ┌──────────────────┐
                                    │   publish.yml    │
                                    │ (Publish Release)│
                                    └──────────────────┘
                                              │
                                              ├─── Build & Test
                                              ├─── Sign Artifacts
                                              ├─── Publish to Maven Central
                                              └─── Create GitHub Release

                                              │
                                              ▼
                                    Available on Maven Central
                                    🎉 Ready for users!
```

---

## Troubleshooting

### Build workflow fails
1. Check the Actions tab for error logs
2. Verify tests pass locally: `./gradlew test`
3. Check if dependencies are available

### Publish workflow fails
1. **"No configured signatory"**: Verify all 4 secrets are set in GitHub
2. **"401 Unauthorized"**: Check OSSRH credentials
3. **"Bad passphrase"**: Verify SIGNING_PASSWORD is correct
4. See [RELEASE.md](./RELEASE.md) Troubleshooting section for more

### Release not appearing in Maven Central
- Wait 15-30 minutes for sync
- Check Sonatype staging: https://s01.oss.sonatype.org/
- Verify namespace is approved

---

## Additional Resources

- **Maven Central**: https://central.sonatype.com/artifact/com.betatel.esim/esim-sdk-kotlin
- **Sonatype OSSRH**: https://s01.oss.sonatype.org/
- **GitHub Actions Docs**: https://docs.github.com/en/actions
- **Semantic Versioning**: https://semver.org/

---

## Support

If you encounter issues:
1. Check the troubleshooting sections in [RELEASE.md](./RELEASE.md)
2. Review [SECRETS_SETUP.md](./SECRETS_SETUP.md) for secrets issues
3. Check workflow logs in the Actions tab
4. Open an issue with error details (without exposing secrets)
