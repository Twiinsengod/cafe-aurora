# Aceite — SPEC-001

## Criteria

| ID | Criterion | Evidence | Result |
| --- | --- | --- | --- |
| AC-1 | ADD 0.5.0 instalado e íntegro | `status`: versão 0.5.0, integrity verified, issues vazios, agentRuntime not-installed | pass |
| AC-2 | Cinco rascunhos DRAFT r1, origem pós-hoc, e canon sem registro | `vision.md`, `design.md`, `visual-bible.md`, `prototype-readiness.md`, `playtest-001.md`; canon só tem `.gitkeep` | pass |
| AC-3 | Design usa o script quando o README diverge | `design.md` registra bandeja de 3 e o nome real do HTML | pass |
| AC-4 | Playtest 001 com as quatro perguntas e resultado pendente | `playtest-001.md` e `.atena/evidence/PLAYTEST-001.md` com status pending | pass |
| AC-5 | HTML do protótipo intocado | `git diff` de `Café Aurora — Protótipo de Playtest.html` e de `README.md` vazio | pass |
| AC-6 | Estado ADD ocioso, plano pós-hoc não ativado | Validador: valid true, state idle, executionReady false | pass |

## Validation summary

- Commands/checks run: `atena-add status --details` em 2026-11-07; `node .atena/methodology/0.5.0/tools/validate-add-state.cjs --project /workspace`; `git diff` do HTML e do README.
- Regressions found: none. O protótipo não foi editado.
- Exceptions accepted by user: o playtest humano permanece pendente. O plano deste ciclo trata essa sessão como passo seguinte, não como critério desta reconciliação.

## Approval evidence

- Approval mode: `per-plan`
- Checkpoints approved: PLAN, só para adoção e rascunhos, conforme o plano da conversa em 2026-11-07.
- Pending checkpoints: nenhum deste ciclo. O playtest não é checkpoint desta spec.

## Reconciliation

- Canonical records updated: none
- Operational facts updated: instalação ADD, identidade do projeto em `add.yaml`, estado de plano ocioso.
- Derived artifacts refreshed: none. `generated/` fica vazio.
- Deferred items retained: Godot, conteúdo, arte, correção do README, playtest por fazer.

## Final state

`verified` para a reconciliação documental. O playtest 001 continua `pending` e bloqueia a próxima spec de design ou de motor.
