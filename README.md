# WebAwesome Home Assistant Theme

Ett modernt Home Assistant-tema (2025/2026 standard) inspirerat av [WebAwesome](https://webawesome.com/). Temat använder det nya semantiska systemet för variabler och inkluderar globalt Card-Mod-stöd för en polerad, interaktiv upplevelse.

## Funktioner

- 🌓 **Fullt stöd för ljust och mörkt läge** i samma fil (`modes:`).
- 🎨 **WebAwesome Palett**: Använder WebAwesomes "Sky" (`#0ea5e9`) som primärfärg, med tydliga semantiska färger för Success, Warning och Danger.
- ✨ **Card-Mod Integration**: Global CSS injiceras för att ge alla kort en mjuk sväveffekt (hover box-shadow) och moderna focus-ringar på inputs och switchar.
- ⚙️ **2026 Kompatibel**: Använder Home Assistants nya semantiska formulär-variabler (t.ex. `--ha-color-form-background`) för kompatibilitet med WebAwesome-migreringen av HA-frontend.

## Installation

### 1. Via HACS (Om konfigurerad som custom repo)
*(För närvarande avsedd för manuell installation)*

### 2. Manuell installation

1. Gå till din Home Assistant konfigurationsmapp (där `configuration.yaml` finns).
2. Skapa en mapp som heter `themes` om den inte redan finns.
3. Kopiera filen `webawesome_theme.yaml` in i `themes/` mappen.
4. Se till att du har följande i din `configuration.yaml`:
   ```yaml
   frontend:
     themes: !include_dir_merge_named themes/
   ```
5. Starta om Home Assistant, eller gå till **Developer Tools -> YAML** och klicka på **Reload Themes**.

## Beroenden

För att få ut maximalt av detta tema rekommenderas starkt att installera:

- [lovelace-card-mod](https://github.com/thomasloven/lovelace-card-mod) via HACS. Detta möjliggör de avancerade CSS-effekterna som mjuka hovers och skräddarsydda formulärfälts-ramar.

## Användning

När temat är laddat:
1. Gå till din profil i Home Assistant.
2. Välj **WebAwesome** under Tema-inställningarna.
3. Välj "Mörk" eller "Ljus" eller låt den följa systemet.
