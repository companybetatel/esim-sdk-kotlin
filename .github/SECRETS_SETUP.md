# GitHub Secrets Setup Guide

This guide will help you set up the required secrets for automatic publishing to Maven Central.

## Required Secrets

You need to configure **4 secrets** in your GitHub repository.

### Where to Add Secrets

1. Go to your repository on GitHub
2. Click **Settings** (top menu)
3. Click **Secrets and variables** → **Actions** (left sidebar)
4. Click **New repository secret**

---

## 1. OSSRH_USERNAME

**Value**: Your Sonatype OSSRH username

### How to Get It:
1. Go to https://central.sonatype.com/
2. Sign up or log in
3. Use the email or username you registered with

**Example**: `john.doe@company.com` or `johndoe`

---

## 2. OSSRH_PASSWORD

**Value**: Your Sonatype OSSRH password or user token

### How to Get It:
**Option A - Use Password** (simple but less secure):
- Use the password you set when registering

**Option B - Generate User Token** (recommended):
1. Log in to https://s01.oss.sonatype.org/
2. Click your username → **Profile**
3. Go to **User Token** dropdown
4. Click **Access User Token**
5. Copy the password value

---

## 3. SIGNING_KEY

**Value**: Your GPG private key in ASCII-armored format

### How to Get It:

#### If you don't have a GPG key yet:

```bash
# 1. Generate a new GPG key
gpg --full-generate-key

# Choose:
#   - RSA and RSA
#   - 4096 bits
#   - No expiration (or 2-5 years)
#   - Your name: "Betatel LTD" or your name
#   - Your email: info@betatel.com or your email
#   - Passphrase: Choose a strong password (you'll need this for SIGNING_PASSWORD)

# 2. List your keys to find the KEY_ID
gpg --list-secret-keys --keyid-format=long

# Output will look like:
# sec   rsa4096/ABCDEF1234567890 2024-01-01 [SC]
#                ^^^^^^^^^^^^^^^^
#                This is your KEY_ID

# 3. Export your private key
gpg --armor --export-secret-keys ABCDEF1234567890
```

#### If you already have a GPG key:

```bash
# List your keys
gpg --list-secret-keys --keyid-format=long

# Export the key
gpg --armor --export-secret-keys YOUR_KEY_ID
```

### The output will look like:

```
-----BEGIN PGP PRIVATE KEY BLOCK-----

lQdGBGXxxx...
[many lines of encoded key data]
...xxxxx==
-----END PGP PRIVATE KEY BLOCK-----
```

**IMPORTANT**:
- Copy the **ENTIRE output** including the `-----BEGIN` and `-----END` lines
- Keep all line breaks as they are
- This is sensitive data - never share it publicly

### Publish Your Public Key:

```bash
# This allows Sonatype to verify your signatures
gpg --keyserver keyserver.ubuntu.com --send-keys YOUR_KEY_ID

# Alternative key servers:
# gpg --keyserver keys.openpgp.org --send-keys YOUR_KEY_ID
# gpg --keyserver pgp.mit.edu --send-keys YOUR_KEY_ID
```

---

## 4. SIGNING_PASSWORD

**Value**: The passphrase you used when creating your GPG key

This is the password you entered when running `gpg --full-generate-key`.

**Security Note**: If you forgot your passphrase, you'll need to create a new GPG key.

---

## Verification Checklist

After adding all secrets:

- [ ] `OSSRH_USERNAME` - Your Sonatype username
- [ ] `OSSRH_PASSWORD` - Your Sonatype password or token
- [ ] `SIGNING_KEY` - Full GPG private key (with BEGIN/END lines)
- [ ] `SIGNING_PASSWORD` - Your GPG key passphrase

All four secrets should show up in: **Settings → Secrets and variables → Actions → Repository secrets**

---

## Testing the Setup

After adding secrets, test with a release:

```bash
# Create a test tag
git tag -a v1.0.2-test -m "Test release"
git push origin v1.0.2-test
```

Then check the **Actions** tab in GitHub to see if the workflow runs successfully.

---

## Troubleshooting

### "Cannot find secret key"
**Problem**: `SIGNING_KEY` is not formatted correctly
**Solution**:
- Make sure you copied the entire output including headers
- Check for any extra spaces or missing line breaks
- Re-export and copy again

### "401 Unauthorized"
**Problem**: `OSSRH_USERNAME` or `OSSRH_PASSWORD` is incorrect
**Solution**:
- Verify credentials by logging in to https://s01.oss.sonatype.org/
- Try using a user token instead of password
- Check if there are any special characters that need escaping

### "Bad passphrase"
**Problem**: `SIGNING_PASSWORD` is incorrect
**Solution**:
- Test locally: `echo "test" | gpg --clear-sign`
- If you can't remember, create a new GPG key
- Make sure there are no extra spaces in the secret

### "Namespace not found"
**Problem**: Your namespace `com.betatel.esim` is not verified on Maven Central
**Solution**:
1. Go to https://central.sonatype.com/
2. Register namespace `com.betatel.esim`
3. Follow their verification process (DNS or GitHub verification)

---

## Security Best Practices

1. **Never commit secrets to git**
   - Always use GitHub Secrets
   - Never put credentials in `gradle.properties` in the repository

2. **Use User Tokens instead of passwords**
   - More secure
   - Can be revoked without changing your password
   - Can have limited scope

3. **Rotate secrets periodically**
   - Update your Sonatype password every 6-12 months
   - Consider regenerating GPG keys every few years

4. **Backup your GPG key**
   - Store the private key securely
   - Keep the passphrase in a password manager
   - You'll need it to sign future releases

---

## Quick Reference Commands

```bash
# List GPG keys
gpg --list-secret-keys --keyid-format=long

# Export private key for GitHub
gpg --armor --export-secret-keys YOUR_KEY_ID

# Export public key (for verification)
gpg --armor --export YOUR_KEY_ID

# Publish public key
gpg --keyserver keyserver.ubuntu.com --send-keys YOUR_KEY_ID

# Test signing locally
echo "test" | gpg --clear-sign

# Delete a test tag
git tag -d v1.0.2-test
git push origin :refs/tags/v1.0.2-test
```

---

## Getting Help

- **Sonatype Documentation**: https://central.sonatype.org/publish/
- **GPG Documentation**: https://gnupg.org/documentation/
- **GitHub Secrets**: https://docs.github.com/en/actions/security-guides/encrypted-secrets

If you need assistance, open an issue in the repository with:
- The error message (without exposing secrets)
- Which step you're stuck on
- What you've already tried
