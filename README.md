# Agent Skills

Skills para ampliar as instruções de agentes de código.

## Skills disponíveis

| Skill | Descrição | Documentação |
| --- | --- | --- |
| `commit-msg` | Gera mensagens de commit concisas em português no padrão Conventional Commits. | [README](skills/commit-msg/README.md) |

## Instalação

Os exemplos usam o CLI [`skills`](https://github.com/vercel-labs/skills) e instalam a skill `commit-msg`.

### Claude Code

```bash
# No projeto atual: .claude/skills/
npx skills add eac0d3r/skills --skill commit-msg --agent claude-code

# Global: ~/.claude/skills/
npx skills add eac0d3r/skills --skill commit-msg --agent claude-code --global
```

### Diretório universal `.agents`

```bash
# No projeto atual: .agents/skills/
npx skills add eac0d3r/skills --skill commit-msg --agent universal

# Global: ~/.config/agents/skills/
npx skills add eac0d3r/skills --skill commit-msg --agent universal --global
```