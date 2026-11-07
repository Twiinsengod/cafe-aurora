---
id: "DRAFT-READINESS-001"
type: "requirement"
title: "Café Aurora — prontidão do protótipo"
status: "draft"
revision: 1
origin: "post-hoc"
maturity: "DRAFT"
created: "2026-11-07"
canonical: false
sources:
  - "Café Aurora — Protótipo de Playtest.html"
  - "README.md"
  - ".atena/vault/drafts/vision.md"
  - ".atena/vault/drafts/design.md"
  - ".atena/vault/drafts/visual-bible.md"
---

# Prontidão do protótipo — Café Aurora

Relatório de trabalho, revisão 1, origem pós-hoc. O protótipo já foi escrito antes deste relatório. O relatório não autoriza implementação nova.

Pendências principais: falta o playtest humano, e a direção visual ainda não está aprovada. As duas bloqueiam a próxima decisão. Nenhuma das duas bloqueia a leitura do que o HTML já faz.

## Intenção do protótipo

- Hipótese: o jogador entende o expediente, executa compra, preparo e entrega, e percebe caixa, gorjeta e reputação.
- Limite jogável: arquivo `Café Aurora — Protótipo de Playtest.html`, do dia 1 até o fim do primeiro rush no dia 4.
- Fora deste recorte: motor novo, arte nova, receitas novas, upgrades, clientes especiais e mudança de regra.
- Aceite deste ciclo de documentação: os rascunhos existem, apontam o script quando o README diverge, e o playtest está descrito com resultado pendente.
- Primeiro playtest: [playtest-001.md](playtest-001.md). Ninguém jogou.

## Evidência da definição inicial

| Área | Decisão ou evidência atual | Pendência e efeito |
| --- | --- | --- |
| Visão e público | Fantasia de operar a cafeteria. Público amplo está só proposto no README | Sem playtest, o público continua proposta |
| Design e loop | Regras extraídas do script, revisão 1 do design | Não mudar regra neste ciclo |
| Escopo | Um HTML, navegador, clique. Sem prazo, equipe ou orçamento registrados | Não estimar produção final |
| Bíblia visual | Rascunho inicial a partir do CSS e do layout | Bloqueia arte e escolha de motor |
| Objetivo de teste | Quatro perguntas já impressas na página | Falta a resposta de uma pessoa |

## Pendências principais

| Item | Classe | Por que importa | Default ou ação | Dono |
| --- | --- | --- | --- | --- |
| Ninguém jogou a revisão atual | BLOCKING para a próxima decisão de design | Diversão, justiça e clareza do DevLog não saem do código | Fabio joga do dia 1 até passar o primeiro rush e responde o roteiro | Fabio, antes da próxima spec |
| Direção visual sem aprovação | BLOCKING para arte e para motor | Escolher ferramenta sem direção repete trabalho | Manter o HTML como jogável e a bíblia como DRAFT r1 | Rever depois do playtest |
| Bandeja de 3 e arquivo sem o nome `index.html` | RESOLVABLE | O README diz bandeja de 2 e manda abrir `index.html` | A regra jogável é a do script: bandeja 3 e o nome atual do arquivo. Não corrigir o README agora | Spec futura, se ainda incomodar |
| Godot 4 | DEFERRED | Está no roadmap e o `.gitignore` já ignora pastas Godot, mas não há projeto | Não instalar nem migrar | Depois do playtest e de uma bíblia aprovada |
| Especialistas de jogo, sprites, áudio além dos bipes | DEFERRED | Não há entrega visual nem defeito medido que peça outro papel | Atena mantém a documentação; ninguém mais entra neste ciclo | Quando houver necessidade concreta |

Há defaults. Eles estão escritos de propósito, para não parecer que a pendência sumiu.

## Recomendação técnica — ainda não feita

A visão, o design, o escopo e a bíblia inicial existem como rascunho. O playtest que sustentaria uma escolha de motor não aconteceu. Por isso esta tabela não recomenda motor.

| Opção | Encaixe com o que já está decidido | Custo | Fonte e data | Recomendação |
| --- | --- | --- | --- | --- |
| Continuar no HTML atual | O loop já roda nesse arquivo | Nenhum neste ciclo | Script no repositório, 2026-11-07 | Veículo do playtest 001. Não é decisão de produto final |
| Godot 4 | Capaz de uma versão 2D futura, em tese | Migração inteira, ainda sem bíblia aprovada | Menção no README e ignores do Git. Sem projeto e sem checagem de licença ou versão nesta data | Adiado. Não instalar |

- Motor, ferramentas e arquitetura recomendados: nenhum, neste ciclo.
- Razão: a escolha vem depois da experiência, do design, da bíblia e do playtest. Só o primeiro jogável está pronto, e ele já tem veículo.
- Incerteza: não foi pesquisada a capacidade atual do Godot 4, nem licença, custo ou exportação.
- Registro: hipótese de produção, não constraint aprovada. O HTML existente é fato, não voto pelo navegador como destino final.

## Atualização antes de implementar qualquer coisa nova

- Ferramenta já disponível: navegador abre o HTML. Node 22 serviu só para instalar o ADD. Godot não está no projeto.
- Autorização: este ciclo autoriza adoção do ADD e estes rascunhos. Não autoriza dependência nova, canon, Godot nem edição do HTML.
- Spec: [SPEC-001](../../specs/SPEC-001/spec.md), origem pós-hoc. O plano reconstruído não é plano de execução.
- BLOCKING para começar implementação nova: 2. Os dois continuam, de propósito. Eles não impedem fechar a reconciliação documental.
- RESOLVABLE em uso: regras pelo script; playtest no arquivo atual.
- DEFERRED: Godot, conteúdo novo, arte, especialistas, correção do README.
- Próximo passo concreto: a pessoa joga e o resultado entra em `.atena/evidence/`. Sem essa sessão, a próxima spec não avança.
- Partida de implementação nova: fechada.
