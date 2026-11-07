---
id: "SPEC-001"
title: "Reconciliar o protótipo do Café Aurora e preparar o playtest"
status: "draft"
origin: "post-hoc"
implementation_preceded_spec: true
created: "2026-11-07"
revision: 1
approval_mode: "per-plan"
canonical_refs: []
---

# Reconciliar o protótipo do Café Aurora e preparar o playtest

## Objective

Deixar registrado, como rascunho pós-hoc, o que o protótipo jogável já faz, onde o README diverge do script, e qual playtest humano precisa acontecer antes de qualquer spec nova. Nenhum registro entra em canon.

## Context and evidence

O repositório já continha `README.md` e `Café Aurora — Protótipo de Playtest.html` antes desta spec. Não havia `.atena/`. A implementação do jogo precedeu este texto. Esta spec não finge que o plano existia antes do HTML.

Não há registro canônico para referenciar. Esta spec também não cria o registro canônico inicial. Os rascunhos em `.atena/vault/drafts/` são a proposta. A promoção fica para uma aprovação futura que nomeie o texto e a revisão.

Evidência usada na reconstrução:

- o script do HTML, como fonte da regra quando o README diverge;
- o README, como descrição anterior e como lista do que ele diz diferente;
- a instalação do ADD portátil 0.5.0, commit `21a9a2c353dae2a33cb44220ce4a3d6f4daf553b`, com integridade verificada.

## Scope

- Adotar o ADD 0.5.0 neste repositório, com prévia antes de `--apply`.
- Escrever visão, design, bíblia visual inicial, prontidão e plano de playtest como DRAFT, revisão 1, origem pós-hoc.
- Abrir o lugar da evidência do playtest, vazio de resultado.
- Registrar esta spec, o plano reconstruído, as tarefas e o aceite.

## Non-goals

- Editar o HTML.
- Renomear o arquivo para `index.html` ou corrigir o README.
- Promover canon.
- Instalar Godot, runtime de agente, especialistas de jogo ou o perfil Marizverso.
- Novas receitas, upgrades, clientes especiais, sprites ou mudança de regra.
- Realizar o playtest no lugar de Fabio.

## Decisions

| Decisão | Escolha | Evidência | Estado |
| --- | --- | --- | --- |
| Fonte da regra | O script do HTML | Bandeja no código é 3; o README diz 2. O arquivo jogável não se chama `index.html` | decidido para o rascunho |
| Veículo do próximo teste | O HTML atual | O loop já roda | decidido para o playtest 001 |
| Motor | Não escolher | Bíblia ainda é rascunho e ninguém jogou | adiado |
| Canon | Não promover | O plano aprovado autoriza só adoção e rascunhos | decidido neste ciclo |
| Granularidade | `per-plan` | Uma revisão cobre adoção e rascunhos | decidido para este ciclo documental |

A aprovação deste ciclo, no plano "Começar o Café Aurora com ADD", autoriza escrever estes arquivos. Não é aprovação retroativa do HTML e não é aprovação de conteúdo canônico.

## Gaps

### BLOCKING

Nenhum bloqueio impede fechar esta reconciliação documental.

Dois bloqueios continuam para a próxima spec, e estão fora do aceite desta:

- não há playtest humano;
- a bíblia visual não está aprovada, então arte e motor não começam.

### RESOLVABLE

- README desatualizado: o design rascunho segue o script. Default: não editar o README neste ciclo.
- Público "crianças e idosos": permanece proposta na visão, não vira canon.

### DEFERRED

- Godot 4, conteúdo novo, sprites, áudio além dos bipes, especialistas, correção do contador `wrongOrders`, e o texto da conquista de Chocolate Quente que não menciona as condições extras do código.

## Acceptance criteria

- [ ] O ADD 0.5.0 está instalado e `status` reporta integridade verificada.
- [ ] Os cinco rascunhos existem, marcados DRAFT, revisão 1, origem pós-hoc, e não há registro em `.atena/vault/canon/` além do marcador de pasta vazia.
- [ ] O design registra bandeja 3 e o nome real do arquivo quando o README diz o contrário.
- [ ] O playtest 001 descreve as quatro perguntas e o resultado pendente.
- [ ] O HTML do protótipo não foi modificado por esta spec.

## Impact

### Expected files/systems

- `AGENTS.md` e `.atena/methodology/0.5.0/` pela instalação.
- `.atena/add.yaml`, `.atena/installation.json`, `.atena/state/plan.yaml`.
- `.atena/vault/drafts/` com os cinco rascunhos.
- `.atena/evidence/PLAYTEST-001.md` pendente.
- `.atena/specs/SPEC-001/`.

### Canonical impact

Nenhum. O canon inicial não foi criado.

## Risks

- Tratar o rascunho como regra aprovada. Mitigação: status `draft`, `canonical: false` e pasta de canon vazia.
- O backup de instalação em `.atena/install-backups/` repete os arquivos em base64. É o recibo de recuperação do CLI, não uma segunda fonte de regra.

## Post-hoc disclosure

A implementação do protótipo ocorreu antes desta spec. A reconstrução usa o HTML e o README presentes no repositório em 2026-11-07. O plano em `plan.md` mapeia o que já estava feito e o trabalho documental deste ciclo. Ele não é evidência de planejamento anterior nem de aprovação prévia do jogo.
