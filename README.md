# UFO CLI Homebrew tap

Inspect files, extract content and make guarded edits locally with [Universal File Opener CLI](https://universalfileopener.com/cli/).

Linux x86_64 with glibc 2.35 or later is required. Alpine/musl, macOS and ARM64 are unsupported by this release. The application includes Java; rendering and PDF conversion also need libGL, libX11 and fontconfig on your host.

Homebrew 7 loads formulae from other taps only after you trust them:

```sh
brew trust --formula krauqllc/ufo/ufo
brew install krauqllc/ufo/ufo
ufo --version
ufo doctor
ufo inspect /absolute/path/to/file
```

This formula pins CLI 1.6.0 to the published GitHub archive and its SHA-256. Homebrew downloads it during installation. Document processing runs locally without network or telemetry.

For MCP, run `ufo mcp print-config --client claude-code` and replace the allowed-root placeholders with existing absolute task directories. No directories are granted by default.

```sh
brew update
brew upgrade krauqllc/ufo/ufo
brew uninstall krauqllc/ufo/ufo
brew untap krauqllc/ufo
```

The formula and tap documentation are Apache-2.0 source. The downloaded application includes proprietary engines under separate business use terms; the executable as a whole is not Apache licensed. Read `ENGINE-LICENSE.txt` under `$(brew --prefix krauqllc/ufo/ufo)/libexec` before commercial use. This tap ships no application binaries. The [release](https://github.com/krauqllc/ufo-cli/releases/tag/v1.6.0) includes its notices and license terms.

Linux installation, offline `ufo doctor`, `ufo capabilities` and `brew test` were verified with Homebrew 7.0.0 on Ubuntu 24.04. All 467 installed runtime files retained the approved release bytes and executable flags. The formula source is maintained in [ufo-cli](https://github.com/krauqllc/ufo-cli).
