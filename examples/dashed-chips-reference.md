# Referens: Chips med streckad ring (Dashed Border)

Detta är koden från din original-konfiguration (Request #2) som använde en streckad röd ring och en "ping"-animation.

```yaml
type: custom:auto-entities
card:
  type: custom:mushroom-chips-card
card_param: chips
filter:
  include:
    - options:
        type: entity
        content_info: name
        card_mod:
          style: |
            ha-card {
              --chip-background: rgba(210, 31, 60, 0.2) !important;
              --chip-border-color: #D21F3C !important;
              --chip-border-width: 2px !important;
              --chip-border-style: dashed !important;
              --chip-icon-color: red !important;
              --chip-font-size: 9px !important;
              animation: ping 2s infinite;
            }
            @keyframes ping {
              0% {box-shadow: 0 0 0 0 rgba(210, 31, 60, 0.7);}
              70% {box-shadow: 0 0 0 10px transparent;}
            }
```

### Varför fungerade det inte?
Mushroom Chips använder ofta en standard-border som inte alltid reagerar på `--chip-border-style`. För att få det att fungera till 100% brukar man behöva lägga till detta i CSS-blocket:

```css
ha-card {
  border: 2px dashed var(--chip-border-color) !important;
}
```
