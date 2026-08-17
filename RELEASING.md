# Publishing a release

Stable releases use a version tag such as `v1.1.2` and always attach these two
public asset names:

- `PromptLight.zip`
- `PromptLight.zip.sha256`

Keeping the asset names stable lets the website use GitHub's
`releases/latest/download/PromptLight.zip` URL without changing on every app
release.

For each release:

1. Build, sign, notarize, staple, and verify the app from the private macOS
   source repository.
2. Copy the final notarized archive into `.release-assets/PromptLight.zip`.
3. Generate `.release-assets/PromptLight.zip.sha256` against that filename.
4. Create a GitHub release using the matching stable version tag.
5. Attach both assets and publish the release as neither a draft nor a
   prerelease.
6. Download the public asset and verify its SHA-256 checksum and Gatekeeper
   acceptance before announcing it.

Drafts and prereleases do not replace the latest stable download target.
