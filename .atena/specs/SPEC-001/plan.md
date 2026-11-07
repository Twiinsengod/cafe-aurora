---
id: "PLAN-001"
spec_id: "SPEC-001"
status: "draft"
revision: 1
origin: "post-hoc"
approval:
  mode: "per-plan"
---

# Plano — SPEC-001

## Plan mode

Origin: post-hoc

Reconstruction: true

This document maps the implementation after the fact. It is not evidence of prior planning or approval.

O HTML do Café Aurora já existia. Os passos S-001 e S-002 abaixo descrevem o que foi encontrado, não uma ordem que alguém aprovou antes de programar. Os passos S-003 e S-004 são o trabalho documental autorizado depois, pelo plano "Começar o Café Aurora com ADD", em granularidade `per-plan`. Essa autorização cobre adoção do ADD e rascunhos. Não cobre canon, Godot nem edição do jogo.

Um plano pós-hoc não é ativado como plano de execução. `.atena/state/plan.yaml` permanece ocioso.

## Recommended approach

Guardar a metodologia e escrever a memória em cima do protótipo que já roda. Não reimplementar o loop para documentá-lo.

## Reuse

O arquivo HTML único já é o protótipo. Os templates de jogo vieram dentro do snapshot `.atena/methodology/0.5.0/templates/game/` e foram adaptados nos rascunhos. Nenhuma skill de jogo foi copiada para fora do snapshot.

## Implementation sequence

1. `S-001` — Protótipo HTML já presente no repositório, com loop, rush, conquistas, DevLog e relatório. Reconstruído. Não foi executado por esta spec.
2. `S-002` — README já descrevia o jogo e divergia do script na bandeja e no nome do arquivo. Reconstruído. O README não foi alterado.
3. `S-003` — Instalar o ADD 0.5.0 depois da prévia, no commit `21a9a2c353dae2a33cb44220ce4a3d6f4daf553b`.
4. `S-004` — Escrever os rascunhos, o plano de playtest pendente e esta spec, sem promover canon.

## Approval checkpoints

O modo escolhido para o ciclo documental é `per-plan`. Não há lote `B-XXX` nem checkpoint por passo. O cursor não foi ativado: um plano pós-hoc não vira plano de execução, e este arquivo não guarda um registro `approved` que pudesse ser lido como licença para implementar o jogo.

## Expected changes

- `.atena/methodology/0.5.0/` — snapshot da distribuição.
- `AGENTS.md` — ponte gerada pelo CLI, sem texto extra.
- `.atena/vault/drafts/` — cinco rascunhos.
- `.atena/specs/SPEC-001/` — spec, plano, tarefas e aceite.
- `.atena/evidence/PLAYTEST-001.md` — resultado ainda pendente.

## Validation

- `atena-add status --details` — versão 0.5.0 e integridade verificada.
- `node .atena/methodology/0.5.0/tools/validate-add-state.cjs` — estado ocioso válido.
- `git diff` no HTML do protótipo — vazio.

## Limits

- Sem nova dependência de jogo.
- Sem retentativa de instalação: a prévia foi lida e o `--apply` rodou uma vez.

## Recovery

O CLI gravou `.atena/install-backups/fef82932-6953-4669-8692-6bd79cc99bc1.json` antes de escrever. `recover` restaura só o bloco de instrução e o recibo se os bytes ainda casarem. Apagar `.atena/` por git reverte a adoção. O HTML não precisa de recuperação porque não entra no diff.

## Mandatory gates

- Publicação do branch pede o fluxo normal de PR. Não há deploy.
- Canon, Godot e edição do HTML continuam fora do checkpoint.

## Approval record

Not applicable — implementation preceded specification.

O plano "Começar o Café Aurora com ADD", aprovado nesta conversa em 2026-11-07, autorizou a adoção e os rascunhos. Essa frase não é um checkpoint executável e não aprova o HTML depois do fato. O status deste plano permanece `draft`. O conteúdo de design continua DRAFT e o playtest não foi feito.

## Step progress and prepared handoff

Revision: 1. Índice documental 4/4 depois que os rascunhos e esta spec estão no disco. S-001 e S-002 são história reconstruída. S-003 e S-004 são o trabalho deste ciclo.

| Step | Objective | Inputs | Deliverable | Actions/checks | Checkpoint/status |
| --- | --- | --- | --- | --- | --- |
| S-001 | Reconhecer o protótipo já jogável | HTML | Regras no design rascunho | Leitura do script | reconstruído; sem checkpoint |
| S-002 | Reconhecer o README | README | Divergências anotadas, arquivo intacto | Comparar bandeja e nome do arquivo | reconstruído; sem checkpoint |
| S-003 | Adotar o ADD | Pacote local no SHA pinado | Snapshot 0.5.0 e ponte | Prévia, `--apply`, status | PLAN; aprovado para este escopo |
| S-004 | Escrever a memória | Templates e o script | Rascunhos, playtest pendente, spec | Pastas e validador de estado | PLAN; aprovado para este escopo |

Não há passo S-005. O playtest humano fica visível como pendência, fora desta sequência. O cursor de execução não é ativado.
