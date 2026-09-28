# commit-msg

Gera mensagens de commit concisas em português do Brasil, no padrão Conventional Commits. Prioriza o motivo da mudança, sem repetir o que o diff já mostra.

## Uso

Peça uma mensagem de commit ou use `/commit`. Forneça o diff ou uma breve descrição da mudança; sem contexto, a skill pedirá essas informações.

A skill entrega a mensagem em um bloco de código pronto para colar. Não executa `git commit`, não prepara arquivos e não usa `--amend`.

## Regras principais

- Usa um tipo Conventional Commits em inglês e resumo no imperativo em português.
- Mantém o assunto com até 72 caracteres e omite o corpo quando ele não acrescenta contexto.
- Inclui corpo para breaking changes, correções de segurança, migrações de dados e reversões.
- Preserva em inglês palavras-chave reconhecidas por ferramentas, como `BREAKING CHANGE:`, `Closes` e `Refs`.

Consulte as instruções completas em [SKILL.md](SKILL.md).