---
id: "DRAFT-VISION-001"
type: "vision"
title: "Café Aurora — visão de trabalho"
status: "draft"
revision: 1
origin: "post-hoc"
maturity: "DRAFT"
created: "2026-11-07"
canonical: false
sources:
  - "README.md"
  - "Café Aurora — Protótipo de Playtest.html"
---

# Visão — Café Aurora

Rascunho de trabalho, revisão 1. Origem pós-hoc: o protótipo já existia quando este texto foi escrito. Nada aqui é canon. Promover um trecho exige aprovação explícita desse trecho e desta revisão.

## Experiência do jogador

- Fantasia do jogador: operar uma cafeteria pequena, comprando insumos, montando bebidas e entregando antes que o cliente desista.
- Sentimentos desejados, propostos e ainda não confirmados por playtest: controle no rush, clareza do que o dinheiro e a reputação fizeram, e antecipação ao desbloquear uma receita que só entra no dia seguinte.
- Público pretendido, proposto no README e ainda não aprovado: acessível a crianças e idosos, com o dia 1 ensinando pelo tutorial, sem punição.
- Propósito observado: protótipo jogável para validar o design, não a versão final.
- Conceito curto: em cada expediente o jogador abastece a loja, prepara cafés no balcão e nas mesas e fecha o dia no lucro. A pressa do cliente é o desafio.

## Pilares de experiência

| Pilar | Experiência pretendida | Implicação observável no protótipo | Estado |
| --- | --- | --- | --- |
| Atendimento sob pressão | Decidir a ordem dos pedidos pela paciência que resta | A bebida recém-passada vai sozinha ao pedido compatível com menos paciência | proposto, r1 |
| Planejar o estoque | Comprar e pré-montar antes do movimento | Tela de abertura a partir do dia 2; bandeja de até 3 bebidas | proposto, r1 |
| Tutorial sem punição | O primeiro dia ensina fazendo | Dia 1 atende 3 clientes, um por vez, sem perda de reputação | proposto, r1 |
| Conta transparente | O jogador entende preço, gorjeta e penalidade | DevLog cronológico e relatório da run | proposto, r1; a clareza ainda não foi jogada |

## Referências e diferenciação

| Referência e fonte | Aspecto relevante | Interpretação |
| --- | --- | --- |
| Nenhuma referência externa foi registrada no repositório | — | Não inventar referências. O HTML e o README são a evidência disponível |

Referências futuras são inspiração até que o direito de uso de um asset seja registrado à parte.

## Escopo e restrições de produção

- Plataforma e input observados: navegador, clique. Há `viewport` para tela estreita. Isso é requisito do protótipo, não escolha de motor.
- Equipe, tempo e orçamento: não registrados.
- Escala de conteúdo observada: 4 ingredientes, 5 receitas, 3 conquistas, balcão com 3 vagas, 4 mesas, dias de 60 segundos a partir do dia 2.
- Limite de produção observado: um arquivo HTML/CSS/JavaScript, sem build. Fontes e CSS de terceiros vêm de CDN no `<head>`.
- Decisão já materializada: o primeiro jogável é esse arquivo. O nome real é `Café Aurora — Protótipo de Playtest.html`. O README pede para abrir `index.html`; esse arquivo não existe.
- Não-objetivos deste rascunho: Godot, receitas novas, upgrades de máquina, clientes especiais, sprites e trilha de áudio além dos bipes já sintetizados.

## Intenção do primeiro jogável

- Hipótese a testar: uma pessoa entende o objetivo pelo tutorial, consegue comprar, montar e entregar, e percebe o efeito no caixa e na reputação.
- Menor experiência já jogável: do dia 1 até atravessar o primeiro rush, no dia 4.
- Observação de sucesso: o jogador completa esse trecho e responde, com as próprias palavras, às quatro perguntas já escritas na página. Sem essa sessão, a hipótese continua aberta.

## Decisões e pendências

| Item | Escolha ou pergunta atual | Razão | Classe | Aprovação |
| --- | --- | --- | --- | --- |
| Público crianças e idosos | Proposto no README | Ainda não há sessão de jogo | RESOLVABLE, default: manter como proposta | pendente |
| Motor final | Godot 4 aparece só no roadmap do README e no `.gitignore` | Não há projeto Godot; a bíblia visual e o playtest ainda não sustentam a escolha | DEFERRED | não decidir neste ciclo |
| Arquivo de entrada | Jogar o HTML com o nome atual | O README aponta para um `index.html` inexistente | RESOLVABLE, default: não renomear agora | pendente |

## Próxima rodada

O conceito já está implementado. A pergunta que muda o passo seguinte é o playtest humano descrito em [playtest-001.md](playtest-001.md). Não reabrir entrevista de gênero, dimensão ou plataforma antes desse resultado.
