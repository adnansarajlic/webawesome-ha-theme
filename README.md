# 🎨 WebAwesome Home Assistant Theme

[![HACS Badge](https://img.shields.io/badge/HACS-Custom-orange.svg?style=for-the-badge)](https://github.com/hacs/integration)
![Version](https://img.shields.io/badge/version-1.0.0-blue.svg?style=for-the-badge)
![HA Version](https://img.shields.io/badge/Home%20Assistant-2024.12+-blue.svg?style=for-the-badge)

Ett modernt, högpresterande Home Assistant-tema inspirerat av det prisbelönta ramverket [WebAwesome](https://webawesome.com/). Designat för att ge ditt hem ett rent, professionellt och interaktivt gränssnitt som känns framtidssäkrat för 2026 års standarder.

---

## ✨ Nyckelfunktioner

- 🌓 **Sömlöst Ljust & Mörkt Läge**: Automatisk anpassning i en och samma fil.
- 🎨 **WebAwesome Palett**: Använder WebAwesomes "Sky"-palett för ett modernt och luftigt utseende.
- 💎 **Soft UI & Glassmorphism**: Mjuka skuggor och dynamisk transparens inspirerad av Nordic-temat.
- 🚀 **Optimerat för Mushroom**: Inbyggda variabler för Mushroom Chips som gör styling enklare än någonsin.
- 🛠️ **Card-Mod Integration**: Global CSS för interaktiva hovringseffekter och förbättrade formulärfält.

---

## 📸 Förhandsvisning

*(Här kan du senare lägga in bilder från din `images/` mapp)*
> [!TIP]
> För bästa upplevelse, använd temat tillsammans med [Mushroom Cards](https://github.com/piitaya/lovelace-mushroom).

---

## 📦 Installation

### Alternativ 1: Via HACS (Rekommenderas)
1. Öppna **HACS** > **Frontend**.
2. Klicka på de tre prickarna i hörnet > **Custom repositories**.
3. Lägg till länken till detta repo och välj kategori **Theme**.
4. Klicka på **Download** och ladda om din frontend.

### Alternativ 2: Manuell installation
1. Ladda ner `themes/webawesome.yaml`.
2. Lägg den i din `config/themes/` mapp.
3. Se till att du har `!include_dir_merge_named themes` i din `configuration.yaml`.

---

## 🛠️ För utvecklare & Power Users

### Tematillstånd (State colors)
Temat mappar automatiskt färger för vanliga enheter:
- **Lights**: `var(--wa-warning)` (Amber)
- **Binary Sensors**: `var(--wa-info)` (Sky Blue)
- **Alarms**: Dynamiskt baserat på status (Success/Warning/Danger)

### Använda WebAwesome Bakgrunder
Du kan använda våra inbyggda variabler i dina egna kort för att matcha temat perfekt:
`--wa-bg-success`, `--wa-bg-warning`, `--wa-bg-danger`, `--wa-bg-info`.

---

## 🤝 Bidra
Hittat en bugg eller har ett förslag på förbättring? Öppna gärna en Issue eller en Pull Request!

---

*Skapat med ❤️ av Atlas*
