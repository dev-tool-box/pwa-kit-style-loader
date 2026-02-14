````
# 🚀 pwa-style-loader

**Vanilla CSS support for Salesforce PWA Kit — in one command.**

`pwa-style-loader` is a small CLI utility that helps Salesforce PWA Kit developers
quickly enable **plain CSS + PostCSS support** without manually touching webpack internals.

Built to be:
- simple
- safe
- enterprise-friendly
- zero-guesswork

---

## ✨ What problem does this solve?

Salesforce PWA Kit does not enable **global / vanilla CSS imports** out of the box.

Developers often need to:
- dig into PWA Kit webpack config
- add `css-loader`, `style-loader`, `postcss-loader`
- configure PostCSS manually
- risk breaking existing setups

**This tool removes that friction.**

---

## ✅ What this tool does

When you run:

```bash
npx pwa-style-loader
````

The CLI will:

1. Detect whether you are inside a **Salesforce PWA Kit project**
2. Create the following files **if they don’t exist**:
   - `webpack.config.js`
   - `postcss.config.js`

3. If files already exist, it will:
   - ask for **explicit confirmation** before replacing

4. Add:
   - CSS loader support
   - PostCSS with Autoprefixer

5. Do **nothing silently**
6. Never append or mutate existing configs without permission

---

## 🧠 Key design principles

- **No silent overwrites**
- **No guessing**
- **No forced dependency changes**
- **Single source of truth**
- **User stays in control**

This makes it safe for:

- enterprise codebases
- teams
- CI/CD environments

---

## 📦 Installation & Usage

You don’t need to install anything globally.

Just run:

```bash
npx pwa-style-loader
```

That’s it.

---

## 🧪 Example flow

### If files do NOT exist

```txt
✅ webpack.config.js created
✅ postcss.config.js created
🎉 Setup complete!
```

### If files already exist

```txt
⚠️ webpack.config.js already exists.
Do you want to replace webpack.config.js? (y/N):
```

Press:

- `y` → replace
- `Enter` / `n` → skip safely

---

## 📁 Files generated

### `webpack.config.js`

Extends the official PWA Kit webpack configuration and enables:

- `style-loader`
- `css-loader`
- `postcss-loader`

### `postcss.config.js`

Includes:

- `autoprefixer` (default)

---

## 🔍 Project validation

This tool ensures it is being run inside a **Salesforce PWA Kit project** by checking:

```json
"ccExtensibility": {
  "extends": "@salesforce/retail-react-app"
}
```

and the presence of:

```json
"@salesforce/retail-react-app"
```

If not detected, the CLI exits with a helpful message.

---

## 🛡️ Safety & Guarantees

- ❌ No append logic
- ❌ No auto-overwrite
- ❌ No hidden changes
- ✅ Explicit user consent
- ✅ Repeatable & idempotent
- ✅ Easy to revert (delete files)

---

## 🧩 Roadmap ideas (open for contribution)

This project is intentionally minimal, but there’s room to grow.

Possible improvements:

- SCSS / SASS support
- Tailwind CSS preset
- `--yes` / CI mode
- Backup files before replace
- Monorepo support
- Version compatibility checks

---

## 🤝 Contributing

Contributions are **very welcome** 🙌

If you:

- work with Salesforce PWA Kit
- have ideas to improve DX
- want to add optional features
- want to harden enterprise support

Please feel free to:

- open an issue
- suggest improvements
- submit a pull request

Even small improvements are appreciated.

---

## 👤 Maintainer

Maintained by **Abhisek Maiti**
SFCC / PWA Kit Developer

- GitHub: [https://github.com/abhisekmaiti19](https://github.com/abhisekmaiti19)
- LinkedIn: [https://linkedin.com/in/abhisekmaiti19](https://linkedin.com/in/abhisekmaiti19)

---

## 📄 License

MIT License — free to use, modify, and distribute.

---

> Built with ❤️ for the Salesforce PWA Kit community.
