# privacy-terms

## 👨‍💻 Projeto desenvolvido por:
[Rafael Torres Nantes](https://github.com/rafael-torres-nantes)

## Índice

* [📚 Contextualização do projeto](#-contextualização-do-projeto)
* [🛠️ Tecnologias/Ferramentas utilizadas](#%EF%B8%8F-tecnologiasferramentas-utilizadas)
* [🖥️ Funcionamento do sistema](#%EF%B8%8F-funcionamento-do-sistema)
* [📁 Estrutura do projeto](#estrutura-do-projeto)
* [📌 Como executar o projeto](#como-executar-o-projeto)

## 📚 Contextualização do projeto

**Template reutilizável de documentos legais** — **Política de Privacidade** e **Termos de Uso** —
em páginas estáticas prontas para o **GitHub Pages**. Serve para qualquer aplicativo que eu
desenvolvo, preenchendo os campos **Privacy Policy URL** e **Terms of Service URL** exigidos em
processos como o **App Review do Meta for Developers**.

A estrutura legal (base **LGPD – Lei nº 13.709/2018**), a identidade do operador
(**Rafael Torres Nantes**, MEI, CNPJ 62.244.560/0001-49), o contato e o foro são **fixos**; tudo que
é específico de cada app fica em **marcadores `{{PLACEHOLDER}}`** que se preenche por projeto.

> ⚠️ Não constitui parecer jurídico. Valide com um advogado antes do go-live, sobretudo em setores
> regulados.

## 🛠️ Tecnologias/Ferramentas utilizadas

[<img src="https://img.shields.io/badge/HTML5-E34F26?logo=html5&logoColor=white">](https://developer.mozilla.org/docs/Web/HTML)
[<img src="https://img.shields.io/badge/CSS3-1572B6?logo=css3&logoColor=white">](https://developer.mozilla.org/docs/Web/CSS)
[<img src="https://img.shields.io/badge/GitHub_Pages-222222?logo=githubpages&logoColor=white">](https://pages.github.com/)
[<img src="https://img.shields.io/badge/GitHub-181717?logo=github&logoColor=white">](https://github.com/)

## 🖥️ Funcionamento do sistema

São três páginas HTML estáticas com uma folha de estilo compartilhada, sem build nem dependências:

* **`index.html`** — página inicial com links para os dois documentos e o contato do operador.
* **`privacy-policy.html`** — Política de Privacidade (LGPD), com seções fixas e placeholders para os
  dados coletados, finalidades/base legal e operadores de cada app.
* **`terms-of-service.html`** — Termos de Uso, com seções fixas e placeholders para descrição do
  serviço, funcionalidades e perfis de usuário.
* **`styles.css`** — estilo compartilhado, responsivo e com suporte a tema claro/escuro.

Cada app se materializa substituindo os marcadores. Os principais:

| Placeholder | O que preencher |
|---|---|
| `{{NOME_DO_APP}}` | Nome do aplicativo |
| `{{DATA_ATUALIZACAO}}` | Data da última revisão (ex.: 15 de julho de 2026) |
| `{{TABELA_DE_DADOS_COLETADOS}}` | Linhas `<tr>` com dado + finalidade |
| `{{TABELA_FINALIDADES_BASE_LEGAL}}` | Linhas `<tr>` com finalidade + base legal (LGPD) |
| `{{LISTA_DE_OPERADORES}}` | Itens `<li>` dos provedores usados (ex.: AWS) |
| `{{DESCRICAO_DO_SERVICO}}` / `{{FUNCIONALIDADES}}` | O que o app faz e suas funções |
| `{{URL_POLITICA_PRIVACIDADE}}` / `{{URL_TERMOS}}` | URLs públicas dos documentos |

Seções marcadas como **OPCIONAL** nos comentários HTML (integração com plataformas de terceiros,
perfis de usuário, contexto regulado) devem ser removidas quando não se aplicam ao app.

A **raiz** guarda o **template** com os `{{PLACEHOLDERS}}`. Cada aplicativo tem sua versão
**preenchida** em `src/<nome-do-app>/`, reaproveitando o `styles.css` compartilhado da raiz. Hoje
existe apenas o **Election Assistant**; novos apps ganham uma nova pasta em `src/`.

## 📁 Estrutura do projeto

```
.
├── index.html                          # TEMPLATE — página inicial (placeholders)
├── privacy-policy.html                 # TEMPLATE — Política de Privacidade (placeholders)
├── terms-of-service.html               # TEMPLATE — Termos de Uso (placeholders)
├── styles.css                          # estilo compartilhado (claro/escuro)
├── src/
│   └── election-assistant/             # versão preenchida por app
│       ├── index.html
│       ├── privacy-policy.html
│       └── terms-of-service.html
└── README.md
```

## 📌 Como executar o projeto

1. **Clone o repositório:**
   ```bash
   git clone https://github.com/rafael-torres-nantes/privacy-terms.git
   ```

2. **Visualize localmente:** basta abrir os arquivos no navegador (não há build).
   ```bash
   # opcional, para servir via HTTP local
   python -m http.server 8000
   ```

3. **Crie um novo app:** duplique um dos HTML da raiz em `src/<nome-do-app>/`, ajuste o
   `<link>` para `../../styles.css`, substitua os `{{PLACEHOLDERS}}` e remova as seções opcionais
   que não se aplicam.

4. **Publique via GitHub Pages:** em *Settings → Pages*, sirva a branch `main`. As páginas
   preenchidas do **Election Assistant** ficam disponíveis em:

   | Documento | URL |
   |---|---|
   | Política de Privacidade | https://rafael-torres-nantes.github.io/privacy-terms/src/election-assistant/privacy-policy.html |
   | Termos de Uso | https://rafael-torres-nantes.github.io/privacy-terms/src/election-assistant/terms-of-service.html |
