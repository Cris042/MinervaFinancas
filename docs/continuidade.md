## Task ativa

T-004 aberta para corrigir a documentação do deploy já realizado no Render, sem mudança de produto ou infraestrutura versionada.

## Estado atual

Classificação: via rápida. O usuário confirmou que os fatos apenas atualizam documentação de um serviço já implantado e determinou que a ADR-001 permaneça intacta. A task curta T-004 delimita `README.md` e documentos de governança; Jarvis implementa por se tratar de ambiente/deploy, e Yoda é o revisor independente esperado. Patrick Jane não é acionado porque não há comportamento, endpoint ou contrato de produto; Neo não é acionado porque não há alteração de superfície de segurança, segredo, acesso a arquivo, dependência, hook ou pipeline.

## Decisões vigentes

O serviço já existe no Render free, região virginia, mas esta task não altera ambiente nem código: registra que o banco SQLite usa `/tmp` no Render free e, portanto, é efêmero. A decisão do usuário nesta sessão é manter essa opção, sem alterar ADR-001.

## Riscos e lacunas

O banco efêmero perde dados cadastrados após hibernação ou novo deploy; isso está explícito no README. Nota Obsidian `tasks/t-004-deploy-render.md` sincronizada e conferida em 2026-09-29; a pendência foi removida de `docs/pendencias-obsidian.md`. O usuário ratificou o fallback do Jarvis só para esta task; o contrato de `docs/agentes/jarvis.md` (sem caso para código 0 com efeito ausente, e sandbox sem raízes graváveis para `.git` e vault) segue sem correção decidida. Falta também a ADR de hospedagem e persistência (dívida registrada no README).

## Próximo passo

Yoda faz a auditoria independente do PR; Jarvis não aprova nem faz merge. Decidir a correção do contrato do Jarvis e abrir a ADR de hospedagem em PRs próprios.

## Região gerada

<!-- minerva-continuity:generated:start -->
<!-- minerva-continuity:generated:end -->
