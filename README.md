# Openlexia

**A clean, accessible Obsidian theme for academic writing.**  
Built from scratch for clarity, contrast, and ease of use—especially for users with ADHD and/or Dyslexia.

## ✨ Features

- OpenDyslexic font for improved readability
- High-contrast, distraction-minimizing color palette
- Clear typographic hierarchy for writing and reading
- Custom Sass build for modular and maintainable styling

## 🛠 How to Use

1. Clone or download this theme into your `.obsidian/themes/` directory.
2. Build the CSS: run `npm install` once, then `npm run build` to compile `base.scss` → `theme.css`.
3. Enable **Openlexia** in Obsidian via `Settings → Appearance → Themes`.
4. To pick up edits while iterating, re-run `npm run build` and reload snippets/theme in Obsidian.

## 📐 Architecture (SCSS)

- `base.scss`: main entry; imports modular settings and component styles.
- `settings/colors-dark.scss`, `settings/colors-light.scss`: single sources of truth for color swatches.
- `settings/code-colors.scss`: exposes code/inline-code colors as CSS vars per theme.
- `settings/links-tags.scss`: exposes link and tag variables (and list marker color) per theme.
- `settings/metadata.scss`: metadata link colors as CSS vars per theme.
- `settings/pwc.scss`: Pandoc/WriterCitations CSS vars per theme.
- `settings/workspace-overrides.scss`: workspace background and UI overrides (e.g., `--tab-divider-color`).
- `settings/rainbow-accents.scss`: Rainbow Folders accent RGBs and core RGBs.
- `features/rainbow-folders/*`: Rainbow Folders styling.

## 🎯 View Compatibility

- Reading view: styled via `.markdown-reading-view`/`.markdown-preview-view` selectors.
- Live Preview / Source: styled via CodeMirror tokens.
  - Inline code uses `.cm-inline-code` to match Reading view colors and Fira Code font/size.
  - Hashtags use `.cm-hashtag`, `.cm-hashtag-begin`, `.cm-hashtag-end` for tight, gapless tags.

## 🎨 Key Variables

- Inline code colors: `--inline-code-text-color`, `--inline-code-background-color` (from swatches).
- Code block colors: `--code-text-color`, `--code-background-color` (from swatches).
- Link colors: `--link-internal-color`, `--link-external-color` (per theme).
- Tags: `--tag-color`, `--tag-background`, etc. Tags and inline code share the Fira Code font and size.
- Horizontal rule: uses `--tab-divider-color` from `settings/workspace-overrides.scss` (dark `#ffd76d`, light `#884800`).

## 🔧 Development Notes

- Build: `npm run build` (compiles Sass).
- If you change swatches in `settings/colors-*.scss`, rebuild to propagate to all CSS variables.

## 📦 License

This project is licensed under the [GNU GPL v3.0](LICENSE).
