# Café da Serra — Web Semântica com Vite

Projeto acadêmico da disciplina **Gestão de Dados** (trabalho de recuperação de faltas).
É o site de uma loja fictícia de cafés especiais, criado com **Vite** e **JavaScript puro**,
para exemplificar o uso de **web semântica**.

Autor: Thales Yoshihico Mathuy de Sá — BDAG

## Recursos de web semântica usados

| Recurso | Onde está |
| --- | --- |
| HTML5 semântico (`header`, `nav`, `main`, `article`, `section`, `aside`, `footer`, `figure`, `time`, `address`, `data`, `dl`, `details`) | Todas as páginas |
| Schema.org em **JSON-LD** (`Store`, `WebSite`, `Product`, `Offer`, `BlogPosting`) | `<head>` de cada página |
| **Microdados** (`itemscope`, `itemtype`, `itemprop`) com `Product`, `Offer`, `Brand` e `FAQPage` | `index.html` |
| **RDFa** (`vocab`, `typeof`, `property`) com `Store`, `PostalAddress` e `BreadcrumbList` | Rodapé de `index.html` e trilha de `produto.html` |
| **Open Graph** e **Twitter Cards** | `<head>` de cada página |
| Acessibilidade: ARIA, `aria-current`, `role="status"`, link “pular para o conteúdo”, tabelas com `caption` e `scope` | Todas as páginas |
| **Inspetor de dados semânticos** (botão `{ } Ver dados semânticos`) que lê e exibe tudo isso | `src/main.js` e `src/semantica.js` |

## Como executar

Requisito: [Node.js](https://nodejs.org) 20.19 ou mais recente.

```bash
npm install      # instala o Vite
npm run dev      # abre em http://localhost:5173
npm run build    # gera a versão final na pasta dist/
npm run preview  # testa a versão final
```

## Estrutura

```
├── index.html        # página inicial: loja, produtos e perguntas frequentes
├── produto.html      # página de produto com breadcrumb e ficha técnica
├── blog.html         # artigo do blog
├── public/img/       # imagens (SVG)
├── src/
│   ├── main.js       # comportamento da página e inspetor semântico
│   ├── semantica.js  # funções que leem JSON-LD, Microdados, RDFa e Open Graph
│   └── style.css     # estilos
└── vite.config.js    # configuração de build com várias páginas
```

## Como validar os dados estruturados

1. Rode `npm run dev` e abra a página.
2. Clique no botão **{ } Ver dados semânticos** (canto inferior direito).
3. Ou cole o código-fonte da página em <https://validator.schema.org>.
