# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [1.1.0] - 2026-08-23

### Added

- New optional `google_analytics` input. When set to a GA4 measurement ID
  (e.g. `G-XXXXXXXXXX`), the standard GA4 gtag snippet is injected into the
  generated HTML immediately after the `<head>` tag.

## [1.0.3] - 2026-03-01

### Fixed

- Improved Pandoc installation mechanism to handle environments where `sudo`
  is not available and to skip installation when Pandoc is already present.

## [1.0.2] - 2026-02-28

### Added

- GitHub Marketplace and release badges added to the README.

## [1.0.1] - 2026-02-28

### Changed

- Metadata and Marketplace polish: updated `action.yml` with branding, author,
  and description improvements.

## [1.0.0] - 2026-02-28

### Added

- Initial release.
- Converts `README.md` to a styled `index.html` using Pandoc and Simple.css.
- Automatically sets the HTML `<title>` from the first `# Heading`.
- Suppresses Pandoc's injected syntax-highlighting CSS.
- Supports custom `readme`, `output`, `css_url`, `install_pandoc`, and
  `extra_pandoc_args` inputs.
- Example GitHub Pages deployment workflow included.

[Unreleased]: https://github.com/davorg/readme-to-index/compare/v1.1.0...HEAD
[1.1.0]: https://github.com/davorg/readme-to-index/compare/v1.0.3...v1.1.0
[1.0.3]: https://github.com/davorg/readme-to-index/compare/v1.0.2...v1.0.3
[1.0.2]: https://github.com/davorg/readme-to-index/compare/v1.0.1...v1.0.2
[1.0.1]: https://github.com/davorg/readme-to-index/compare/v1.0.0...v1.0.1
[1.0.0]: https://github.com/davorg/readme-to-index/releases/tag/v1.0.0
