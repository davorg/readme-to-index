# readme-to-index

Generate a styled `index.html` from a `README.md` using Pandoc and Simple.css.

This GitHub Action turns a standard project README into a clean, minimal
static website — without modifying the source Markdown.

The HTML `<title>` is automatically taken from the first `# Heading` in the
README (via Pandoc’s `pagetitle` metadata), so you don’t get duplicate titles.

---

## Why not just use GitHub Pages + Jekyll?

You absolutely can.

But this action exists for two reasons:

### 1. Simplicity

* No Jekyll
* No Ruby toolchain
* No themes
* No `_config.yml`
* No implicit behaviours

It takes one Markdown file and produces one HTML file.

That’s it.

For small libraries, CPAN distributions, and utility projects, that’s often
exactly what you want.

### 2. Easy to Insert Into a Build Pipeline

This approach works anywhere Pandoc runs:

* As part of a release workflow
* As part of a documentation build step
* Inside a larger CI pipeline
* Before uploading artifacts somewhere else

It doesn't require the special assumptions of GitHub Pages.

It’s just a build step.

---

## What It Does

* Converts `README.md` → `index.html`
* Applies Simple.css for clean, classless styling
* Sets the HTML `<title>` from the first `# Heading`
* Suppresses Pandoc’s injected syntax-highlighting CSS
* Leaves your original README untouched

---

## Inputs

This action supports the following inputs:

### `readme`

Path to the Markdown source file.

**Default:** `README.md`

### `output`

Path to the generated HTML file.

**Default:** `index.html`

### `css_url`

CSS stylesheet to include in the generated HTML.

**Default:** `https://cdn.simplecss.org/simple.min.css`

### `install_pandoc`

Whether to install Pandoc using `apt-get` (set to `false` if your workflow already installs Pandoc).

**Default:** `true`

### `extra_pandoc_args`

Additional arguments passed directly to the Pandoc command.

**Default:** *(empty)*

---

## Example Usage

Minimal usage:

```yaml
- uses: davorg/readme-to-index@v1
```

With custom inputs:

```yaml
- uses: davorg/readme-to-index@v1
  with:
    readme: docs/README.md
    output: _site/index.html
    extra_pandoc_args: "--toc"
```

To publish via GitHub Pages using the modern deployment flow, see the example
workflow in this repository.

