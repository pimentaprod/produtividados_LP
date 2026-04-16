# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Sobre o Projeto

Landing page estática da **ProdutiviDados** — empresa de automação de processos e análise de dados para pequenas e médias empresas. O site é escrito em HTML/CSS/JS puro, sem framework, build tool ou gerenciador de pacotes.

## Como Rodar

Abra `index.html` diretamente no navegador, ou use qualquer servidor HTTP local:

```bash
# Python
python -m http.server 8080

# Node.js (npx)
npx serve .
```

Não há etapa de build, transpilação ou instalação de dependências.

## Arquitetura

Todo o site está em um único arquivo `index.html`, que contém:

- **CSS inline** no `<head>` — variáveis CSS no `:root` definem a paleta de cores e são a fonte de verdade para o design.
- **HTML** — seções sequenciais: navbar, hero, sobre, serviços (automação e análise de dados), clientes, depoimentos, blog e rodapé/contato.
- **JavaScript inline** no fim do `<body>` — controla: scroll do navbar (`#navbar.scrolled`), animações de entrada (`.fade-in` via `IntersectionObserver`), menu hambúrguer mobile e quaisquer interações de UI.

O arquivo `Texto do Site.txt` contém o conteúdo textual de referência usado para preencher o HTML.

## Identidade Visual

A paleta de cores oficial está definida nas variáveis CSS:

| Variável    | Valor     | Uso                        |
|-------------|-----------|----------------------------|
| `--navy`    | `#001834` | Fundo escuro, navbar, texto de destaque |
| `--blue`    | `#01488A` | Azul intermediário         |
| `--sky`     | `#0495F0` | Cor de ação/destaque (CTAs, links, spans) |
| `--white`   | `#FFFFFF` | Fundo claro                |
| `--gray`    | `#f4f7fc` | Fundo de seções alternadas |
| `--text`    | `#1a2a3a` | Texto principal            |
| `--muted`   | `#5a7a99` | Texto secundário           |

Fonte: **Raleway** (Google Fonts), pesos 300–800.

Arquivos de identidade visual adicionais estão em `c:/Users/Acer/OneDrive/ProdutiviDados/Identidade Visual`. As imagens usadas na landing page ficam na pasta `Imagens/` dentro deste projeto.

## Padrões do Código

- Classes utilitárias reutilizáveis: `.container`, `.btn`, `.btn-primary`, `.btn-outline`, `.btn-dark`, `.section-tag`, `.section-title`, `.section-sub`, `.fade-in`.
- Animações de entrada usam a classe `.fade-in` ativada por `IntersectionObserver` — aplicar essa classe a novos elementos para consistência visual.
- O navbar muda de estilo ao rolar via a classe `.scrolled` adicionada por JS.
- Responsividade feita com media queries no CSS inline; menu mobile via classe `.nav-toggle`.
