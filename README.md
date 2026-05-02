# WebAwesome Theme for Home Assistant 🎨

A premium, modern theme for Home Assistant inspired by [WebAwesome](https://webawesome.com/). It features a clean, Nordic-inspired design with a focus on semantic colors, dynamic shadows, and elegant typography.

<p align="center">
  <img src="https://raw.githubusercontent.com/adnansarajlic/webawesome-ha-theme/main/images/light.png" width="400" alt="WebAwesome Light Mode">
  <img src="https://raw.githubusercontent.com/adnansarajlic/webawesome-ha-theme/main/images/dark.png" width="400" alt="WebAwesome Dark Mode">
</p>
<p align="center">
  <em>Light Mode vs Dark Mode</em>
</p>

## ✨ Features
- **Semantic Colors**: Predefined variables for `--wa-success`, `--wa-warning`, `--wa-danger`, and more.
- **Dynamic Nordic Shadows**: Soft, floating shadows that adapt to light and dark modes.
- **Premium Typography**: Uses the Inter font family for a crisp, high-end feel.
- **Rounded Aesthetics**: Balanced border radii (12px-16px) for a friendly and modern UI.
- **Card-Mod Optimized**: Built-in support for advanced styling of Mushroom chips and other cards.

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

## 🚀 Usage
To get the most out of WebAwesome, use the semantic color variables in your `card_mod` configurations:

```yaml
card_mod:
  style: |
    ha-card {
      background: var(--wa-success);
      color: white;
    }
```

## 🛠️ Components Used in Examples
- [Lovelace Card Mod](https://github.com/thomasloven/lovelace-card-mod)
- [Mushroom Cards](https://github.com/piitaya/lovelace-mushroom)
- [Bubble Card](https://github.com/Clooos/Bubble-Card)

---
*Created by Adnan Sarajlic with inspiration from the WebAwesome team.*
