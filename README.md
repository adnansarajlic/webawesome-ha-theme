# 🎨 WebAwesome Home Assistant Theme

[![HACS Badge](https://img.shields.io/badge/HACS-Custom-orange.svg?style=for-the-badge)](https://github.com/hacs/integration)
![Version](https://img.shields.io/badge/version-1.0.0-blue.svg?style=for-the-badge)
![HA Version](https://img.shields.io/badge/Home%20Assistant-2024.12+-blue.svg?style=for-the-badge)

A modern, high-performance Home Assistant theme inspired by the award-winning [WebAwesome](https://webawesome.com/) framework. Designed to give your home a clean, professional, and interactive interface future-proofed for 2026 standards.

---

## ✨ Key Features

- 🌓 **Seamless Light & Dark Mode**: Automatic adaptation within a single theme file.
- 🎨 **WebAwesome Palette**: Utilizes the official WebAwesome "Sky" palette for a fresh and airy look.
- 💎 **Soft UI & Glassmorphism**: Elegant soft shadows and dynamic transparency inspired by Nordic aesthetics.
- 🚀 **Mushroom Optimized**: Native support and built-in variables for Mushroom Cards and Chips.
- 🛠️ **Card-Mod Integration**: Global CSS for interactive hover effects and modernized form fields.

---

## 📸 Preview

*(Coming soon: Screenshots from the `images/` folder)*
> [!TIP]
> For the ultimate experience, use this theme together with [Mushroom Cards](https://github.com/piitaya/lovelace-mushroom).

---

## 📦 Installation

### Option 1: Via HACS (Recommended)
1. Open **HACS** > **Frontend**.
2. Click the three dots in the corner > **Custom repositories**.
3. Add this repository's URL and select the category **Theme**.
4. Click **Download** and reload your Home Assistant frontend.

### Option 2: Manual Installation
1. Download `themes/webawesome.yaml`.
2. Place it in your `config/themes/` directory.
3. Ensure you have `!include_dir_merge_named themes` in your `configuration.yaml`.

---

## 🛠️ For Developers & Power Users

### State Colors
The theme automatically maps colors for common entities:
- **Lights**: `var(--wa-warning)` (Amber)
- **Binary Sensors**: `var(--wa-info)` (Sky Blue)
- **Alarms**: Dynamic based on status (Success/Warning/Danger)

### Using WebAwesome Backgrounds
You can use our built-in variables in your custom cards to match the theme perfectly:
`--wa-bg-success`, `--wa-bg-warning`, `--wa-bg-danger`, `--wa-bg-info`.

---

## 🤝 Contributing
Found a bug or have a suggestion for improvement? Please feel free to open an Issue or a Pull Request!

---

*Built with ❤️ by Atlas*
