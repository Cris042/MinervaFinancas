---
type: minerva-task
project: Minerva
date: 2026-09-29
status: em-andamento
tags:
  - minerva
  - task
ai-first: true
---

# T-004: Registrar o deploy já realizado no Render

## Para o futuro agente

Atualizar a documentação para descrever, sem alterar o produto, o deploy já realizado no Render. A task termina quando o README, a continuidade e a nota Obsidian correspondente registrarem fatos verificáveis do ambiente e a revisão independente por Yoda estiver concluída.

## Origem

- Caminho: **via rápida** — manutenção documental delimitada, sem introduzir, alterar ou remover comportamento de produto, regra de negócio, endpoint, contrato público, persistência, integração, dependência ou decisão estrutural.
- PRD: não aplicável na via rápida.
- FDD aprovado: não aplicável; não há comportamento de produto.
- HLD: não aplicável; não há impacto estrutural.
- ADRs aplicáveis: ADR-001 permanece intacta; a task registra a decisão operacional explícita do usuário de manter SQLite efêmero no Render free, sem criar ou alterar decisão arquitetural.

## Resumo decisório mínimo

- Objetivo: substituir a lacuna falsa de deploy em nuvem por fatos verificados do Render, com limites operacionais explícitos.
- Decisão: via rápida; publicar somente fatos fornecidos pela sessão principal em `README.md` e artefatos de governança documental.
- Evidências: fatos de produção verificados pela sessão principal em 2026-09-29; validações documentais proporcionais previstas nesta task.
- Riscos e lacunas: dados SQLite são efêmeros no Render free e se perdem após hibernação ou novo deploy; não há lacuna bloqueante para registrar esse fato.
- Próximo passo: Jarvis atualiza os arquivos permitidos, executa os gates documentais e abre PR para auditoria independente de Yoda.

## Responsáveis

- Planejamento: Jarvis, com escopo explícito do usuário.
- Implementação: Jarvis.
- Auditoria: Yoda, independente do implementador.

## Resultado esperado

O README informa que `minerva-financas` está disponível no Render e descreve publicação, configuração, limites do banco e reprodução em outra plataforma sem alterar código, Dockerfile ou pipeline.

## Escopo

### Incluído

- `README.md`, exclusivamente a seção `## Deploy` e a remoção coerente da lacuna em `## O que não foi entregue`.
- `docs/tasks/T-004-deploy-render.md`, `docs/tasks/README.md`, `docs/continuidade.md`, `docs/historico/2026-09.md` e `docs/pendencias-obsidian.md`.
- Nota Obsidian em `tasks/t-004-deploy-render.md`.

### Excluído

- Código, Dockerfile, `docker-compose.yml`, pipelines, dependências e variáveis versionadas.
- Criação ou alteração de ADR, HLD, PRD e FDD; ADR-001 permanece intacta.
- Mudança no serviço Render, credenciais, permissões, autenticação, autorização ou endpoints.

## Dependências e bloqueios

- Fatos do deploy fornecidos e verificados pela sessão principal em 2026-09-29; disponíveis.
- Acesso de escrita ao vault Obsidian; a pendência deve permanecer aberta se o caminho externo não puder ser escrito.

## Passos de implementação

1. Rotacionar o estado da task anterior para o histórico mensal e registrar o estado desta task na continuidade.
2. Registrar imediatamente a pendência Obsidian e atualizar o README dentro da superfície permitida.
3. Executar validações documentais, sincronizar o vault se houver acesso e abrir PR para Yoda.

## Critérios de aceite

- [ ] A classificação **via rápida**, objetivo, arquivos permitidos, exclusões, validações e revisor independente estão visíveis nesta task.
- [ ] `README.md` registra plataforma, plano, região, serviço, URL, publicação, variáveis, banco efêmero e reprodução em outra plataforma somente com os fatos fornecidos.
- [ ] A lacuna de deploy em nuvem foi removida de `README.md` sem alterar outras seções além da coerência necessária.
- [ ] `docs/continuidade.md` respeita o contrato de forma e o limite de 8 KB.
- [ ] A obrigação Obsidian está sincronizada e conferida, ou tem pendência completa dentro de 24 horas.

## Testes obrigatórios

- [ ] Verificador de continuidade e links relativos de `README.md` e `docs/*.md`.
- [ ] Gates documentais aplicáveis ao diff.

## Evidências obrigatórias

- [ ] Saídas verdes dos validadores documentais executados.
- [ ] PR com classificação via rápida, escopo, validações, estado do Obsidian e auditoria esperada de Yoda.

## Acionamento proporcional de agentes

- Jarvis é o implementador porque a documentação registra ambiente e deploy já operados.
- Yoda é o revisor independente exigido para a auditoria do PR.
- Patrick Jane não é acionado: não há comportamento observável, endpoint, contrato público, critério de aceite de produto ou cobertura funcional a definir.
- Neo não é acionado: não há alteração de autenticação, autorização, input/output, segredo, dependência, hook, pipeline, credencial, acesso a arquivo ou outra superfície de ataque; as referências a Basic e às variáveis apenas documentam fatos já configurados fora do repositório.

## Documentação e Obsidian

- Arquivos `.md` do repositório: `README.md`, esta task, índice de tasks, continuidade, histórico e pendências.
- Notas Obsidian: `/mnt/c/Users/mclov/OneDrive/Documentos/Obsidian Vault/mclov/Documents/SecondBrain/Bases/Minerva/tasks/t-004-deploy-render.md`.

## Riscos e lacunas

- O Render free não oferece volume nem disco persistente; o banco em `/tmp` é recriado após hibernação ou deploy. Mitigação: aviso explícito no README; dono: usuário, que escolheu SQLite efêmero.

## Definição de pronto

- [ ] Implementação respeita a superfície e as validações da via rápida.
- [ ] Testes e evidências obrigatórias foram produzidos.
- [ ] Documentação e nota Obsidian foram atualizadas ou a pendência completa permanece dentro do prazo.
- [ ] PR foi auditado por Yoda, agente diferente do implementador.
- [ ] Pipelines obrigatórios estão verdes.

## Histórico

- 2026-09-29: task criada com status em-andamento.
- 2026-09-29: o usuário ratificou explicitamente o fallback usado nesta task (o Codex saiu com código 0, mas o sandbox bloqueou git, `gh` e vault, e esse efeito ficou ausente). A ratificação vale só para esta task; o contrato de `docs/agentes/jarvis.md` não foi alterado.
- 2026-09-29: achados N3 (origem da evidência é a sessão principal) e N5 (executor do fallback foi Claude Sonnet sobre edições do Codex; a linha `Co-Authored-By: Claude Opus 5.5` do commit anterior veio de instrução da sessão principal) corrigidos.
- 2026-09-29: as correções N1 a N5 foram levadas por este PR de acompanhamento porque o squash do PR #2 foi feito antes delas.
