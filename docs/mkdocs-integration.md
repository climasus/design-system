# Como aplicar o design-system em um MkDocs

Este guia padroniza a estetica dos repositorios Python do ecossistema ClimaSUS.

## 1. Configure o `mkdocs.yml`

```yaml
theme:
  name: material
  custom_dir: docs/overrides
  palette:
    - scheme: default
      primary: custom
      accent: custom
    - scheme: slate
      primary: custom
      accent: custom
  font:
    text: Inter
    code: JetBrains Mono

extra_css:
  - https://climasus.github.io/design-system/assets/css/theme.css
  - stylesheets/climasus-extras.css
```

## 2. (Opcional) Space Grotesk nos headings

```css
@import url("https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@500;600;700;800&display=swap");

.md-typeset h1,
.md-typeset h2 {
  font-family: "Space Grotesk", sans-serif;
}
```

## 3. Fallback offline

Se o build precisar funcionar sem rede, baixe o arquivo remoto e aponte para uma copia local:

```yaml
extra_css:
  - stylesheets/theme.css
```
