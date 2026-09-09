# Portfólio — Luiz Eduardo

Site estático (um único arquivo `index.html`, sem build, sem dependências além de uma fonte do Google Fonts) pronto para publicar no GitHub Pages. Agora com **PT/EN** (botão de idioma ao lado do de tema) e uma linha do tempo ("Jornada") também dirigida por dados, no mesmo padrão dos projetos.

## Como publicar (GitHub Pages)

1. Crie um repositório novo no GitHub (público, de preferência). Sugestão de nome: `portfolio` ou `seu-usuario.github.io` (esse último já publica na raiz do domínio).
2. Coloque o arquivo `index.html` na raiz do repositório e faça o commit/push.
3. No GitHub, vá em **Settings → Pages**.
4. Em "Source", selecione a branch `main` e a pasta `/ (root)`. Salve.
5. Em alguns minutos o site estará em `https://seu-usuario.github.io/nome-do-repo/`.

## O fluxo: terminar algo → publicar no portfólio

A ideia é que isso vire parte do "fechamento" de cada módulo/curso/parte do TCC, não uma tarefa separada que empilha. Dois lugares diferentes pra atualizar, dependendo do que você terminou:

- **Terminou um exercício, módulo de curso, ou uma etapa/parte do TCC** (algo que marca progresso, mas não é "um projeto" fechado em si) → adicione um item ao array `jornada`.
- **Terminou algo com resultado concreto e mostrável** (um notebook, uma EDA, um projeto pequeno, a entrega final do TCC) → adicione um item ao array `projetos` (e, se fizer sentido, também um item na `jornada` marcando o marco).

Nos dois casos, o processo é: abra `index.html` no editor, ache o array certo (comentários `ADICIONE NOVOS MARCOS DA SUA JORNADA AQUI` ou `ADICIONE SEUS PROJETOS AQUI`), copie um bloco `{ ... }` existente, cole antes do `]`, edite os campos, salve, `git add` + `git commit` + `git push`. GitHub Pages atualiza sozinho em alguns minutos.

### Adicionar um marco na Jornada

```js
{
  atual: false, // true só no marco que representa "agora" (ganha destaque visual)
  status: "done", // "done" | "progress" | "planned"
  data: { pt: "Setembro 2026", en: "September 2026" },
  titulo: { pt: "Concluí o módulo de SQL do curso de Data Engineering", en: "Finished the SQL module of the Data Engineering course" },
  descricao: {
    pt: "Joins, agregações, window functions e um mini-projeto de modelagem de schema.",
    en: "Joins, aggregations, window functions, and a small schema-design mini-project."
  }
},
```

Importante: quando adicionar um novo marco "atual", lembre de mudar o anterior de `atual: true` para `atual: false` (só um item deve ter `atual: true` por vez).

### Adicionar um projeto

```js
{
  titulo: { pt: "Análise Exploratória de Vendas", en: "Sales Exploratory Analysis" },
  descricao: {
    pt: "Exploração de um dataset público de vendas, com limpeza, EDA e visualizações em Python.",
    en: "Exploration of a public sales dataset, with cleaning, EDA and visualizations in Python."
  },
  tecnologias: ["Python", "Pandas", "Matplotlib"],
  status: "done", // "done" | "progress" | "planned"
  repo: "https://github.com/seu-usuario/seu-projeto",
  demo: "" // opcional
},
```

Preencha sempre `pt` e `en` juntos — é isso que mantém o botão de idioma funcionando para todo o conteúdo, não só para os textos fixos da página.

## Sobre o idioma (PT/EN)

- O botão de idioma fica ao lado do botão de tema (claro/escuro), no canto superior direito.
- O idioma inicial é controlado por uma única linha no `<script>`, perto do início do bloco de i18n:
  ```js
  const DEFAULT_LANG = 'pt';
  ```
  Quando quiser que o inglês vire o padrão, troque para `'en'` — nada mais no arquivo precisa mudar.
- Textos fixos da página (menu, seções, rótulos) ficam centralizados no objeto `i18n` no `<script>`. Se um dia quiser ajustar uma frase, é lá que ela está — em `i18n.pt.<chave>` e `i18n.en.<chave>`.

## Onde editar seus links reais

Procure por `TODO` no arquivo: são os dois pontos (LinkedIn e GitHub) onde o `href="#"` precisa virar o seu link de verdade. O e-mail de contato já está preenchido.

## Próximos passos sugeridos

- Trocar os emojis dos cards de skills por ícones SVG, se quiser um visual ainda mais "de produto".
- Adicionar uma foto/avatar no hero.
- Mais pra frente, quando o objetivo for um backend de verdade (API própria, Docker, banco de dados), esse vira um projeto **separado** — já está registrado que essa decisão fica pra depois.
