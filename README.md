# ClimaSUS Design System

> **Repositório central de identidade visual, assets compartilhados e dados institucionais do ecossistema ClimaSUS.**

---

## O que está aqui

| Caminho | Conteúdo |
|---------|----------|
| `assets/css/style.css` | CSS completo — paleta, tipografia, componentes |
| `assets/css/variables.css` | Design tokens isolados |
| `assets/css/theme.css` | Overrides para MkDocs Material e pkgdown |
| `assets/logos/` | Logo oficial em PNG e JPG |
| `data/team/members.json` | Dados completos da equipe |
| `data/team/teams.json` | Grupos da equipe |
| `data/project/organization.json` | Dados institucionais do ecossistema |
| `data/project/repositories.json` | Catálogo de repositórios |
| `data/i18n/pt.json` | Strings de interface em português |
| `data/i18n/en.json` | Strings de interface em inglês |
| `data/i18n/es.json` | Strings de interface em espanhol |

---

## Documentação

**→ https://climasus.github.io/design-system/**

Guia rapido de integracao com MkDocs:

- `docs/mkdocs-integration.md`

---

## Como usar em outro repositório

No workflow GitHub Actions, adicione antes do build:

```yaml
- name: Fetch design-system assets
  run: |
    DS=https://climasus.github.io/design-system
    curl -fsSL "$DS/assets/css/style.css"  -o docs/assets/climasus.css
    curl -fsSL "$DS/assets/logos/logo-symbol.png" -o docs/assets/logo.png
    for lang in pt en es; do
      curl -fsSL "$DS/data/i18n/${lang}.json" -o assets/i18n/${lang}.json
    done
```

**Regra de ouro: nunca duplicar CSS, logo ou dados de equipe em outros repositórios.**
