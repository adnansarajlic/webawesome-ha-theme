# WebAwesome Theme for Home Assistant 🎨

<div align="center">

[![hacs_badge](https://img.shields.io/badge/HACS-Default-41BDF5.svg?style=for-the-badge)](https://github.com/hacs/integration) [![Last Commit](https://img.shields.io/github/last-commit/adnansarajlic/webawesome-ha-theme?style=for-the-badge)](https://github.com/adnansarajlic/webawesome-ha-theme/commits/main) [![GitHub license](https://img.shields.io/github/license/adnansarajlic/webawesome-ha-theme?style=for-the-badge)](LICENSE)

</div>

<div align="center">
  <p align="center">
    A premium, modern theme for Home Assistant inspired by <a href="https://webawesome.com/">WebAwesome</a>.
    <br />
    Focused on semantic colors, dynamic shadows, and elegant typography.
  </p>
</div>

<details>
  <summary>Table of Contents</summary>
  <ol>
    <li><a href="#screenshots">Screenshots</a></li>
    <li><a href="#features">Features</a></li>
    <li><a href="#installation">Installation</a></li>
    <li><a href="#usage">Usage & Chip Classes</a></li>
    <li><a href="#color-reference">Color Reference</a></li>
  </ol>
</details>

## Screenshots

<table>
  <tr>
    <td align="center" width="50%"><strong>Light Mode</strong><br /><img src="images/light.png" alt="WebAwesome Light Mode" width="620" /></td>
    <td align="center" width="50%"><strong>Dark Mode</strong><br /><img src="images/dark.png" alt="WebAwesome Dark Mode" width="620" /></td>
  </tr>
</table>

## ✨ Features
- **Semantic Color System**: Built-in variables for success, warning, danger, and info states.
- **Dynamic Nordic Shadows**: Soft floating shadows that adjust intensity between modes.
- **Inter Typography**: Uses the crisp *Inter* font family for a professional look.
- **Soft UI**: Balanced border-radius (12px-16px) across all cards and dialogs.
- **Mushroom Optimized**: Advanced styling for chips and template cards.

## 📦 Installation

### Via HACS (Recommended)
1. Go to **HACS** -> **Frontend**.
2. Click the three dots -> **Custom repositories**.
3. Add `adnansarajlic/webawesome-ha-theme` with type **Theme**.
4. Click **Download**.

### Manual Installation
1. Download `themes/webawesome.yaml`.
2. Place it in your `themes/` folder.
3. Add the following to your `configuration.yaml`:
```yaml
frontend:
  themes: !include_dir_merge_named themes
```

## 🚀 Usage & Chip Classes

WebAwesome includes custom CSS classes for **Mushroom Chips**. Use these via `card_mod` -> `class` for consistent status indicators:

- `wa-chip-success`: Pulsing green with dynamic transparency.
- `wa-chip-info`: Pulsing blue.
- `wa-chip-warning`: Pulsing amber.
- `wa-chip-danger`: Pulsing red.
- `wa-chip-danger-solid`: Solid high-visibility red for critical alarms.

Example:
```yaml
type: custom:mushroom-chips-card
chips:
  - type: template
    icon: mdi:fire
    card_mod:
      class: wa-chip-danger
```

## 🎨 Color Reference

### 🌈 Semantic Palette (Global)
These variables stay consistent across modes and are used for status indicators.

| Variable | Light/Dark Hex | Swatch |
| :--- | :--- | :--- |
| `--wa-success` | `#10b981` | ![](https://readme-swatches.vercel.app/10b981) |
| `--wa-info` | `#0ea5e9` | ![](https://readme-swatches.vercel.app/0ea5e9) |
| `--wa-warning` | `#f59e0b` | ![](https://readme-swatches.vercel.app/f59e0b) |
| `--wa-danger` | `#ef4444` | ![](https://readme-swatches.vercel.app/ef4444) |
| `--wa-purple` | `#8b5cf6` | ![](https://readme-swatches.vercel.app/8b5cf6) |
| `--wa-brown` | `#92400e` | ![](https://readme-swatches.vercel.app/92400e) |
| `--wa-neutral` | `#64748b` | ![](https://readme-swatches.vercel.app/64748b) |

### ☀️ Core UI (Light Mode)
Based on the WebAwesome Slate/Zinc palette.

| Variable | Hex Code | Swatch |
| :--- | :--- | :--- |
| `primary-background` | `#f8fafc` | ![](https://readme-swatches.vercel.app/f8fafc) |
| `secondary-background` | `#f1f5f9` | ![](https://readme-swatches.vercel.app/f1f5f9) |
| `card-background` | `#ffffff` | ![](https://readme-swatches.vercel.app/ffffff) |
| `primary-text` | `#0f172a` | ![](https://readme-swatches.vercel.app/0f172a) |

### 🌙 Core UI (Dark Mode)
Deep slate backgrounds with high-legibility text.

| Variable | Hex Code | Swatch |
| :--- | :--- | :--- |
| `primary-background` | `#0f172a` | ![](https://readme-swatches.vercel.app/0f172a) |
| `secondary-background` | `#020617` | ![](https://readme-swatches.vercel.app/020617) |
| `card-background` | `#1e293b` | ![](https://readme-swatches.vercel.app/1e293b) |
| `primary-text` | `#f8fafc` | ![](https://readme-swatches.vercel.app/f8fafc) |

---
*Created by Adnan Sarajlic with inspiration from the WebAwesome team.*
