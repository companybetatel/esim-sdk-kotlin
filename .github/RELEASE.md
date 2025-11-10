# Release Process

This document describes how to release a new version of the Betatel eSIM Kotlin SDK to Maven Central using GitHub Actions.

## Prerequisites

Before you can release, ensure you have:

1. **Maven Central (Sonatype OSSRH) Account**
   - Register at: https://central.sonatype.com/
   - Create a namespace for `com.betatel.esim`
   - Save your username and password

2. **GPG Key for Signing**
   - Generate a GPG key if you don't have one
   - Export your signing key
   - Save the key ID and passphrase

3. **GitHub Repository Secrets**
   - All four secrets must be configured in GitHub

## Setting Up GitHub Secrets

Go to your GitHub repository: **Settings → Secrets and variables → Actions**

Add the following secrets:

### 1. `OSSRH_USERNAME`
Your Sonatype OSSRH username (email or username you used to register)

### 2. `OSSRH_PASSWORD`
Your Sonatype OSSRH password or token

### 3. `SIGNING_KEY`
Your GPG private key in ASCII-armored format:

```bash
# Export your GPG key
gpg --armor --export-secret-keys YOUR_KEY_ID

# Copy the entire output including:
# -----BEGIN PGP PRIVATE KEY BLOCK-----
# ...
# -----END PGP PRIVATE KEY BLOCK-----
```

**Important**: Copy the entire key including headers and footers. Remove any line breaks within the key data.

### 4. `SIGNING_PASSWORD`
The passphrase you used when creating your GPG key

---

## Creating a Release

### Method 1: Using Git Tags (Recommended)

1. **Update the version in `build.gradle`**:
   ```gradle
   version '1.0.2'  // Update to new version
   ```

2. **Update the version in `gradle.properties`** (if present):
   ```properties
   VERSION_NAME=1.0.2
   ```

3. **Commit the changes**:
   ```bash
   git add build.gradle gradle.properties
   git commit -m "Prepare release v1.0.2"
   git push origin master
   ```

4. **Create and push a version tag**:
   ```bash
   git tag -a v1.0.2 -m "Release version 1.0.2"
   git push origin v1.0.2
   ```

5. **Monitor the workflow**:
   - Go to: **Actions** tab in your GitHub repository
   - Watch the "Publish to Maven Central" workflow
   - Check for any errors in the logs

6. **Verify the release**:
   - Check GitHub Releases page for the new release
   - Wait 15-30 minutes for Maven Central to sync
   - Verify at: https://central.sonatype.com/artifact/com.betatel.esim/esim-sdk-kotlin

### Method 2: Manual Workflow Trigger

1. Go to: **Actions → Publish to Maven Central → Run workflow**
2. Select the branch (usually `master`)
3. Click **Run workflow**

**Note**: This method requires you to manually update the version in `build.gradle` beforehand.

---

## Release Workflow Details

### What Happens Automatically

1. **Checkout code**: Pulls the latest code from the tagged commit
2. **Set up Java 21**: Configures the build environment
3. **Extract version**: Reads version from the git tag (e.g., `v1.0.2` → `1.0.2`)
4. **Update version**: Updates `build.gradle` with the tag version
5. **Build and test**: Runs full build and test suite
6. **Publish to Maven Central**: Uploads artifacts with signing
7. **Create GitHub Release**: Creates a GitHub release with:
   - Release notes
   - All JAR files attached
   - Installation instructions

### Artifacts Published

Three JAR files are published to Maven Central:

1. **Main JAR**: `esim-sdk-kotlin-{version}.jar` - Contains compiled classes
2. **Sources JAR**: `esim-sdk-kotlin-{version}-sources.jar` - Contains source code
3. **Javadoc JAR**: `esim-sdk-kotlin-{version}-javadoc.jar` - Contains API documentation

---

## Version Numbering

Follow [Semantic Versioning](https://semver.org/):

- **MAJOR.MINOR.PATCH** (e.g., `1.0.2`)
- **MAJOR**: Incompatible API changes
- **MINOR**: New functionality (backwards compatible)
- **PATCH**: Bug fixes (backwards compatible)

**Tag format**: Always prefix with `v` (e.g., `v1.0.2`, `v2.0.0`)

---

## Troubleshooting

### Error: "No configured signatory"
**Solution**: Verify all four GitHub secrets are set correctly:
- `OSSRH_USERNAME`
- `OSSRH_PASSWORD`
- `SIGNING_KEY`
- `SIGNING_PASSWORD`

### Error: "401 Unauthorized" from Sonatype
**Solution**:
1. Verify your OSSRH credentials are correct
2. Check if you need to create an authentication token instead of password
3. Ensure your namespace (`com.betatel.esim`) is approved

### Error: "Could not find or load main class"
**Solution**: Ensure Java 21 is properly configured in the workflow (already set)

### Release doesn't appear in Maven Central
**Solution**:
1. Check if it's in Sonatype staging: https://s01.oss.sonatype.org/
2. Wait 15-30 minutes for sync to Maven Central
3. Close and release the staging repository if auto-release is disabled

### Version mismatch
**Solution**: Make sure the version in `build.gradle` matches your git tag (without the `v` prefix)

---

## Manual Release (Alternative Method)

If you prefer to release manually without GitHub Actions:

1. **Set up local credentials** in `~/.gradle/gradle.properties`:
   ```properties
   ossrhUsername=your-username
   ossrhPassword=your-password
   signing.keyId=YOUR_KEY_ID
   signing.password=your-passphrase
   signing.secretKeyRingFile=/path/to/.gnupg/secring.gpg
   ```

2. **Run the publish command**:
   ```bash
   ./gradlew clean build publishMavenPublicationToOSSRHRepository
   ```

3. **Log in to Sonatype** and manually release:
   - Go to: https://s01.oss.sonatype.org/
   - Find your staging repository
   - Click "Close" then "Release"

---

## Post-Release Checklist

After a successful release:

- [ ] Verify the release appears in GitHub Releases
- [ ] Check Maven Central (wait 15-30 minutes): https://central.sonatype.com/artifact/com.betatel.esim/esim-sdk-kotlin
- [ ] Update any documentation with the new version
- [ ] Test installing the new version in a sample project
- [ ] Announce the release (blog post, social media, etc.)
- [ ] Update the project README with the latest version

---

## GPG Key Setup (For Reference)

If you need to create a GPG key:

```bash
# Generate a new key
gpg --full-generate-key
# Choose: RSA and RSA, 4096 bits, no expiration

# List your keys
gpg --list-secret-keys --keyid-format=long

# Export the key (for GitHub secret)
gpg --armor --export-secret-keys YOUR_KEY_ID

# Publish to key server (so Sonatype can verify)
gpg --keyserver keyserver.ubuntu.com --send-keys YOUR_KEY_ID
```

---

## Support

If you encounter issues:

1. Check GitHub Actions logs for detailed error messages
2. Review this document's troubleshooting section
3. Check Sonatype documentation: https://central.sonatype.org/publish/
4. Open an issue in the repository

---

## Quick Reference

### Create a release:
```bash
# Update version in build.gradle first, then:
git tag -a v1.0.2 -m "Release version 1.0.2"
git push origin v1.0.2
```

### Required GitHub Secrets:
- `OSSRH_USERNAME`
- `OSSRH_PASSWORD`
- `SIGNING_KEY`
- `SIGNING_PASSWORD`

### Maven Central URL:
https://central.sonatype.com/artifact/com.betatel.esim/esim-sdk-kotlin

### Workflow File:
`.github/workflows/publish.yml`
