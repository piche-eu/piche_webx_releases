# Q Desktop Application Releases

This repository contains the release artifacts and update feed for the Q desktop application.

## Release Process

Releases are automatically built and published when a new version tag is pushed to the main application repository.

### Automated Release Workflow

1. **Tag Creation**: Developer creates a version tag (e.g., `v1.0.0`) in the main repository
2. **Build Process**: GitHub Actions automatically builds for all platforms:
   - macOS (x64 and arm64)
   - Windows (x64)
   - Linux (AppImage)
3. **Asset Publishing**: Built artifacts are uploaded to GitHub Releases
4. **Release Publication**: The GitHub release is published (no longer draft)

### Manual Release Steps

If you need to create a release manually:

1. Ensure your working directory is clean
2. Run the release script with a version:
   ```bash
   RELEASE_VERSION=1.0.0 node scripts/release/release-all.mjs
   ```
   Or use the current package.json version:
   ```bash
   node scripts/release/release-all.mjs
   ```

## Repository Secrets

The following secrets must be configured in the main application repository:

### Required Secrets
- `DEPLOY_TOKEN`: GitHub token with access to this releases repository
- `APPLE_ID`: Apple ID for code signing (macOS)
- `APPLE_ID_PASSWORD`: App-specific password for Apple ID
- `APPLE_TEAM_ID`: Apple Developer Team ID

## Supported Platforms

- **macOS**: 10.14+ (Intel and Apple Silicon)
- **Windows**: Windows 10+
- **Linux**: Most distributions (via AppImage)

## Download Latest Release

Visit the [Releases page](https://github.com/piche-eu/piche_webx_releases/releases/latest) to download the latest version.
