# Agentic skills

Repositório centralizado de skills de desenvolvimento de software para agentes (Opencode e outros) compatível com [Skills CLI](https://github.com/vercel-labs/skills).

## Como usar

- Listar skills disponíveis: `npx skills add Jayneanderson/agentic-skills --list`
- Instalar skill em um projeto: `npx skills add Jayneanderson/agentic-skills`
  - Será perguntado quais skills e se deseja instalar local ou global

## Estrutura

Fonte única em `.agents/skills/` (formato aberto Agent Skills). Os diretórios `.claude/skills/` e `.cursor/skills/` contêm symlinks relativos para a mesma pasta e sem duplicação. Vantagem: um único lugar para editar.

- [.agents/skills/](.agents/skills/) — fonte (formato `SKILL.md` universal)
- [.opencode/skills/](.opencode/skills/) — symlinks → `../../.agents/skills/<skill>` (OpenCode)

## Criando skills

Vamos criar uma skill global de forma manual:

```
# 1. crie em .agents/skills/<nome>/SKILL.md
# 2. exponha pros runtimes (symlinks relativos):
`ln -s ../../.agents/skills/<nome> .opencode/skills/nome<nome>`
# 3. adicione na tabela "Skills globais" abaixo
```

## Skills globais

| Skill | Descrição |
|---|---|
| [openspec-setup-brownfield](.agents/skills/openspec-setup-brownfield/SKILL.md) | Inicializa OpenSpec em projetos brownfield (com código existente em produção).|
