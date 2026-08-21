# Publishing a release

Stable releases use a version tag such as `v1.1.3` and attach these public
assets:

- `PromptLight-VERSION.zip`
- `PromptLight.zip`
- `PromptLight.zip.sha256`

Keeping the asset names stable lets the website use GitHub's
`releases/latest/download/PromptLight.zip` URL without changing on every app
release. The immutable versioned ZIP is used by the signed Sparkle appcast.

For each release:

1. Build, sign, notarize, staple, and verify the app from the private macOS
   source repository.
2. Generate and verify `appcast.xml` with the Sparkle key stored under Keychain
   account `app.promptlight.mac`.
3. Stage the versioned ZIP, stable ZIP, and checksum in `.release-assets/`.
4. Create a GitHub prerelease using the matching version tag and attach all
   three assets.
5. Confirm the immutable versioned asset is public, then push the newly signed
   `appcast.xml` to `main` without editing it afterward.
6. Use a lower updater-enabled build to complete a real update through Sparkle.
7. Verify the installed app's version, checksum, code signature, notarization,
   and Gatekeeper acceptance.
8. Promote the GitHub prerelease to stable and verify the website's latest
   stable download before announcing it.

Never reuse a release tag or replace a versioned ZIP after publishing its
signature in the appcast. Publish a new version and build instead.

Drafts and prereleases do not replace the latest stable download target.
