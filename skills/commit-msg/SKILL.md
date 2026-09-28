---
name: commit-msg
description: >
  Escreve mensagens de commit em português do Brasil no padrão Conventional Commits, comprimidas à intenção (o porquê, não o quê). USE quando o usuário pedir para escrever um commit, uma mensagem de commit ou usar /commit.
metadata:
  author: Eduardo Albuquerque - github.com/eac0d3r
  version: 1.0.0  
---

# Commit conciso

Escreva mensagens de commit curtas e exatas no formato Conventional Commits, em português do Brasil. Sem enrolação. Priorize o porquê em vez do quê: o diff já mostra o quê.

Se nenhum diff ou contexto for fornecido, peça ao usuário o diff ou uma breve descrição da mudança antes de gerar a mensagem.

## Assunto (primeira linha)

Formato: `<tipo>(<escopo>): <resumo no imperativo>`. O escopo é opcional.

- Tipos permitidos (mantenha em inglês): `feat`, `fix`, `refactor`, `perf`, `docs`, `test`, `chore`, `build`, `ci`, `style`, `revert`
- Verbo no imperativo: "adicione", "corrija", "remova", "renomeie". Nunca no passado ("adicionado"), na terceira pessoa ("adiciona") ou no gerúndio ("adicionando")
- Até 50 caracteres quando possível; limite máximo de 72
- Sem ponto final
- Letra minúscula após os dois pontos, a menos que a convenção do projeto indique outra

## Corpo (somente se necessário)

- Omita quando o assunto for autoexplicativo, exceto quando a seção Clareza obrigatória exigir corpo
- Inclua apenas para: *porquê* não óbvio, breaking changes, notas de migração, issues relacionadas
- Quebre linhas em 72 caracteres
- Use marcadores `-`, não `*`
- Referencie issues e PRs no fim: `Closes #42`, `Refs #17`

## O que NUNCA incluir

- "Este commit faz X", "eu", "nós", "agora", "atualmente"
- "Conforme solicitado por..." (use o trailer `Co-authored-by`)
- "Gerado com Claude Code" ou qualquer atribuição a IA. Exceção: se o usuário tiver uma regra própria exigindo um trailer `Assisted-by` ou de atribuição a IA, adicione-o como trailer
- Emoji, a menos que a convenção do projeto exija
- O nome do arquivo quando o escopo já o indica

## Palavras-chave que permanecem em inglês

Mantenha em inglês os elementos que ferramentas e plataformas interpretam: `BREAKING CHANGE:`, `Closes`, `Fixes`, `Refs`, `Co-authored-by`, `Assisted-by`. O texto descritivo ao redor fica em português.

## Exemplos

**Diff:** novo endpoint de perfil de usuário, com corpo explicando o porquê

- ❌ `feat: adicione um novo endpoint para obter as informações de perfil do usuário no banco de dados`
- ✅
  ```
  feat(api): adicione GET /users/:id/profile

  O app mobile precisa dos dados de perfil sem o payload completo
  do usuário, para reduzir o consumo de dados em redes 4G nas telas
  de primeira abertura.

  Closes #128
  ```

**Diff:** breaking change na API

- ✅
  ```
  feat(api)!: renomeie /v1/orders para /v1/checkout

  BREAKING CHANGE: clientes que usam /v1/orders devem migrar para
  /v1/checkout antes da v3.0. A rota antiga retorna 410 a partir dela.
  ```

**Diff:** correção simples, sem necessidade de corpo

- ✅ `fix(auth): trate token expirado no refresh`

## Clareza obrigatória

Sempre inclua corpo em: breaking changes, correções de segurança, migrações de dados e qualquer commit que reverta outro, mesmo que o assunto seja autoexplicativo. Esta regra prevalece sobre a omissão de corpo. Nunca comprima esses casos em apenas o assunto: quem for depurar no futuro precisa do contexto.

## Limites

- Apenas gere a mensagem. Não execute `git commit`, não faça stage de arquivos, não use `--amend`
- Entregue a mensagem em um bloco de código, pronta para colar
- Se o usuário disser "parar commit-conciso" ou "modo normal", volte ao estilo detalhado: mantenha Conventional Commits e português, mas escreva sempre um corpo explicando o quê e o porquê de cada mudança relevante, sem o limite de omissão de corpo.
