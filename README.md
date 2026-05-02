# WebAwesome Theme for Home Assistant 🎨

A premium, modern theme for Home Assistant inspired by [WebAwesome](https://webawesome.com/). It features a clean, Nordic-inspired design with a focus on semantic colors, dynamic shadows, and elegant typography.

![Light Mode Showcase](https://raw.githubusercontent.com/adnansarajlic/webawesome-ha-theme/main/images/light.png)
![Dark Mode Showcase](https://raw.githubusercontent.com/adnansarajlic/webawesome-ha-theme/main/images/dark.png)

## ✨ Features
- **Semantic Colors**: Predefined variables for `--wa-success`, `--wa-warning`, `--wa-danger`, and more.
- **Dynamic Nordic Shadows**: Soft, floating shadows that adapt to light and dark modes.
- **Premium Typography**: Uses the Inter font family for a crisp, high-end feel.
- **Rounded Aesthetics**: Balanced border radii (12px-16px) for a friendly and modern UI.
- **Card-Mod Optimized**: Built-in support for advanced styling of Mushroom chips and other cards.

## 🎨 Color Reference (WebAwesome Palette)

WebAwesome uses a semantic color system. Use these variables in your `card_mod` style to keep a consistent look:

| Variable | Description | Example Hex (Light/Dark) |
| :--- | :--- | :--- |
| `--wa-success` | Success / Positive states | `#10b981` |
| `--wa-warning` | Warning / Attention needed | `#f59e0b` |
| `--wa-danger` | Danger / Alarm states | `#ef4444` |
| `--wa-info` | Information / Active states | `#0ea5e9` |
| `--wa-purple` | Special states / Night mode | `#8b5cf6` |
| `--wa-brown` | Nature / Coffee / Warm states | `#92400e` |
| `--wa-neutral` | Inactive / Muted states | `#64748b` |

## 📦 Installation

### Via HACS (Recommended)
1. Ensure [HACS](https://hacs.xyz/) is installed.
2. Go to **HACS** -> **Frontend**.
3. Click the three dots in the top right and select **Custom repositories**.
4. Add `adnansarajlic/webawesome-ha-theme` with type **Theme**.
5. Click **Download**.

### Manual Installation
1. Download `themes/webawesome.yaml` from this repository.
2. Place it in your `themes/` directory within your Home Assistant configuration folder.
3. Restart Home Assistant or reload themes.

## 🚀 Usage Example
Use the semantic color variables in your `card_mod` configurations for perfect consistency:

```yaml
card_mod:
  style: |
    ha-card {
      border-left: 4px solid var(--wa-success);
      background: color-mix(in srgb, var(--wa-success) 10%, var(--card-background-color));
    }
```

## 🛠️ Components Used in Examples
- [Lovelace Card Mod](https://github.com/thomasloven/lovelace-card-mod)
- [Mushroom Cards](https://github.com/piitaya/lovelace-mushroom)
- [Bubble Card](https://github.com/Clooos/Bubble-Card)

---
*Created by Adnan Sarajlic with inspiration from the WebAwesome team.*
