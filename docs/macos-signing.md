# macOS bundle signing

On macOS, `bun run tauri:build --bundles app` produces an ad-hoc signed app when no distribution identity is configured. Releases can use the existing Apple signing credentials. The macOS workflows verify the entire app with `codesign --verify --deep --strict` before accepting it. The installer checks the existing signature and preserves it through installation.

Install with `bun run install:mac --launch`, or use `--no-build` to install an already signed bundle. Rebuild older bundles that fail strict verification. Ad-hoc signing does not give successive builds a stable identity for macOS privacy permissions.
