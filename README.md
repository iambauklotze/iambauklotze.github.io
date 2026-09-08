# Portfólio — Luiz Eduardo

Site estático (um único arquivo `index.html`, sem build, sem dependências além de uma fonte do Google Fonts) pronto para publicar no GitHub Pages.

## Como publicar (GitHub Pages)

1. Crie um repositório novo no GitHub. Pode ser público (recomendado, pra recrutador acessar) — sugestão de nome: `portfolio` ou `seu-usuario.github.io` (esse último já publica na raiz do domínio, sem subpasta).
2. Coloque o arquivo `index.html` na raiz do repositório e faça o commit/push.
3. No GitHub, vá em **Settings → Pages**.
4. Em "Source", selecione a branch `main` (ou `master`) e a pasta `/ (root)`. Salve.
5. Em alguns minutos o site estará no ar em `https://seu-usuario.github.io/nome-do-repo/` (ou `https://seu-usuario.github.io/`, se o repositório se chamar `seu-usuario.github.io`).

## Como adicionar um novo projeto

Abra `index.html`, procure pelo comentário:

```
ADICIONE SEUS PROJETOS AQUI
```

Perto do final do arquivo tem um array chamado `projetos`. Copie um bloco `{ ... }`, cole antes do `]` e edite os campos:

```js
{
  titulo: "Nome do projeto",
  descricao: "Uma frase clara sobre o que o projeto faz e qual problema resolve.",
  tecnologias: ["Python", "Pandas", "scikit-learn"],
  status: "Concluído", // ou "Em andamento" ou "Planejado"
  repo: "https://github.com/seu-usuario/seu-projeto",
  demo: "" // opcional — link de uma demo online, se tiver
},
```

Salve, faça commit e push — o GitHub Pages atualiza o site sozinho em alguns minutos. Não precisa mexer em HTML/CSS pra isso.

## Como atualizar a linha do tempo ("Jornada")

Cada marco da seção **Jornada** é um bloco `<div class="tl-item">...</div>` dentro de `<div class="timeline">`. Copie um bloco existente, ajuste data/título/descrição/status (`progress`, `done` ou `next` na classe `tl-status`) e cole na posição certa.

## Onde editar seus links reais

No arquivo, procure por `TODO`: são os dois pontos (LinkedIn e GitHub) onde o `href="#"` precisa virar o seu link de verdade. O e-mail de contato já está preenchido.

## Próximos passos sugeridos (quando quiser evoluir o portfólio)

- Trocar os emojis dos cards de skills por ícones SVG, se quiser um visual ainda mais "de produto".
- Adicionar uma foto/avatar no hero.
- Mais pra frente, quando o objetivo for um backend de verdade (API própria, Docker, banco de dados), esse vira um projeto **separado** — o registro dessa decisão já está guardado para quando você quiser retomar esse assunto.
