---
id: "DRAFT-DESIGN-001"
type: "rule"
title: "Café Aurora — design observado"
status: "draft"
revision: 1
origin: "post-hoc"
maturity: "DRAFT"
created: "2026-11-07"
canonical: false
sources:
  - "Café Aurora — Protótipo de Playtest.html"
  - "README.md"
---

# Design — Café Aurora

Rascunho de trabalho, revisão 1, origem pós-hoc. Quando o README e o script divergem, a regra descrita aqui é a do script em `Café Aurora — Protótipo de Playtest.html`. Isto não reescreve o README e não muda o jogo.

## Loop central

Entre expedientes, a partir do dia 2, o jogador compra ingredientes e pode pré-montar bebidas. Durante o expediente, clientes pedem receitas já disponíveis. O jogador monta a receita na bancada, espera a cafeteira e a bebida segue para o pedido compatível com menos paciência, no balcão ou nas mesas. Entregar cedo paga mais gorjeta; perder o cliente custa reputação. No fim do dia, bebidas prontas não entregues são descartadas e o balanço decide se a loja abre de novo.

O que vale testar: se essa escolha, entre estoque, pressa e gorjeta, fica legível sem explicação fora da tela.

## Mecânicas e controles

| Ação | Input | Regra e consequência, como no script | Retorno | Evidência | Estado |
| --- | --- | --- | --- | --- | --- |
| Comprar insumos | Clique na tela de abertura | Preços: café R$ 2, leite R$ 3, chocolate R$ 4, gelo R$ 1. O carrinho só fecha se o caixa cobre o total | Caixa atualizado | `handleConfirmOpenShop` | proposto |
| Pré-montar | Seleção e botão na abertura | Até 3 bebidas, não 2. Consome estoque ou itens do carrinho. Desfazer devolve os ingredientes | Contador `n/3` | `handlePrepAheadAdd` | proposto |
| Montar na bancada | Clique no ingrediente | Até 3 itens. Sem estoque, o clique não entra. Descartar devolve o estoque | Chips na bandeja e som de despejo | `addIngredient` | proposto |
| Passar o café | Botão servir | A combinação precisa ser uma receita disponível. Cafeteira: 1,5 s no tutorial e 2 s nos outros dias. Combinação inválida não consome a montagem | Barra e texto "Preparando…" | `handleServeClick` | proposto |
| Entregar o que acabou de sair | Automático | Entre pedidos do mesmo tipo, ganha o de menor paciência restante, balcão e mesas juntos. Sem pedido compatível, vai para a bandeja se houver vaga; com a bandeja em 3/3, a bebida é descartada | Feedback e DevLog | `deliverDrinkDirect` | proposto |
| Entregar da bandeja | Clique em Entregar | Mesma prioridade. A gorjeta dessa entrega é R$ 4 antes do multiplicador de rush, não a gorjeta proporcional | Botão desliga se não há pedidos ou a cafeteira está ocupada | `deliverPreppedDrink` | proposto |
| Esperar | Nenhuma | Paciência cai 0,1 a cada 100 ms | Barra colorida e segundos | `onCustomerTick` | proposto |

Estado inicial observado: caixa R$ 30, reputação 50 de 100, estoque café 6 e leite 4, chocolate e gelo 0, bandeja vazia.

## Metas, desafio e progressão

- Meta imediata: entregar o pedido antes da paciência zerar.
- Meta da sessão: manter caixa de pelo menos R$ 10 e reputação acima de 0 para abrir o dia seguinte.
- Derrota, conferida no fechamento: `money < 10` ou `reputation <= 0`. As duas mensagens existem; se as duas forem verdadeiras, o texto exibido é o da reputação, porque ele substitui o do caixa.
- Paciência no balcão: 60 s no tutorial, 20 s no expediente normal, 12 s no rush. Quem já está no balcão quando o rush começa tem a paciência cortada para 12 s se ainda tinha mais que isso.
- Mesas: 4. O cliente só senta se o balcão já tem 3 pedidos. Paciência da mesa: 40 s, também no rush. O script não reduz a paciência da mesa para 12 s.
- Cliente sem vaga no balcão e nas mesas desiste na porta. Isso entra no DevLog e não soma cliente perdido nem tira reputação.
- Penalidade por desistência de quem já pediu: reputação −5, ou −10 no rush. No tutorial a desistência não tira reputação. Reputação bem-sucedida: +2, teto 100.
- Gorjeta de uma bebida recém-passada: `max(1, round(4 * paciência_restante / paciência_inicial))`. No rush, a gorjeta dobra depois desse cálculo. Entrega da bandeja usa 4 no lugar da fórmula e também dobra no rush.
- Satisfação do dia: média, em porcentagem, da fração de paciência no momento de cada entrega. Cliente perdido entra na contagem do dia e não soma fração, então puxa a média para baixo. Dia sem clientes registra 100% no DevLog.
- Dias: o dia 1 não usa o relógio de 60 s. Do dia 2 em diante o expediente dura 60 s. A abertura da loja aparece depois do dia 1, não antes dele. A previsão do dia é um texto aleatório entre movimento alto, tranquilo e equilibrado; o script não usa esse texto para mudar o spawn.
- Spawn fora do tutorial: um cliente a cada 4–6 s, inclusive no rush. O comentário no código diz que o intervalo foi mantido para o rush não ficar denso.
- Rush: do dia 4 em diante. Aviso quando o relógio marca 45 s. Rush ativo com o relógio de 40 s até 20 s. Ao cair abaixo de 20 s, o rush termina e `rushesSurvived` aumenta, mesmo que tenham existido perdas naquele rush.
- Receitas disponíveis no dia 1: Café Preto (café, R$ 8) e Latte (café + leite, R$ 12).
- Conquistas, e a receita só entra no dia seguinte:
  - 10 cafés pretos servidos desbloqueiam Mocha (café + leite + chocolate, R$ 16).
  - Satisfação média de pelo menos 80%, com pelo menos 3 clientes no denominador e nenhum cliente perdido no dia, desbloqueia Chocolate Quente (leite + chocolate, R$ 13). O texto da conquista na tela não menciona o mínimo de 3 clientes nem a exigência de zero perdas.
  - 3 entregas no rush atual com zero perdas naquele rush, avaliadas ainda durante o rush, desbloqueiam Café Gelado (café + gelo, R$ 11).
- Chocolate e gelo só ficam compráveis quando uma receita disponível daquele dia pede o ingrediente.
- Fim de dia: a montagem aberta volta ao estoque. Bebidas da bandeja são descartadas e os ingredientes não voltam. Pedidos ainda na fila somem sem penalidade extra nesse fechamento.
- Relatório: as últimas 10 runs ficam em `localStorage`, chave `cafe_aurora_runs`, gravadas no game over. O campo "pedidos incorretos" existe no relatório e em `RUN_DATA.wrongOrders`, que o script zera e nunca incrementa.

## Mundo e narrativa

Não há lore além da cafeteria, dos nomes de clientes e dos títulos das conquistas. Narrativa maior não se aplica a este protótipo.

## Escopo e dependências

- Conteúdo do protótipo: o arquivo HTML único já implementa o loop acima.
- Adiado, com motivo e momento de rever: Godot 4, receitas novas, upgrades de máquina e clientes especiais. Rever depois do playtest 001 e de uma bíblia visual aprovada.
- Leitura visual já exigida pelo loop: distinguir balcão, mesas, paciência, rush, bandeja cheia e receita bloqueada. A direção está em [visual-bible.md](visual-bible.md).
- Áudio observado: bipes sintetizados pela Web Audio API para acerto, erro, clique, despejo e aviso de rush. Sem música e sem arquivos de som.
- Plataforma observada: navegador. O `<head>` carrega Inter e basecoat por CDN.

## Hipóteses de validação

| Hipótese | Tarefa do jogador | O que observar | Evidência técnica | Feedback humano |
| --- | --- | --- | --- | --- |
| O tutorial basta | Jogar o dia 1 sem ajuda externa | Onde a pessoa para | O dia termina ao atender ou perder 3 clientes | Sim, sensação de entendimento |
| A entrega ao mais impaciente parece justa | Atender balcão e mesas juntos | Se a pessoa percebe quem recebeu a bebida | DevLog nomeia o destinatário | Sim |
| Esperar um dia pela receita cria expectativa | Desbloquear uma conquista e abrir o dia seguinte | Se a pessoa planeja a compra | A receita só passa em `isRecipeAvailable` no dia seguinte | Sim |
| O balanceamento atual parece controlável | Chegar ao rush do dia 4 | Ritmo, perdas e gorjeta | Relatório da run, se a partida terminar em game over | Sim |

O roteiro completo está em [playtest-001.md](playtest-001.md). Ninguém jogou esta revisão ainda.

## Lacunas

- BLOCKING para a próxima decisão de design: não há resultado de playtest.
- BLOCKING para escolher motor ou produzir arte: a bíblia visual ainda é rascunho inicial.
- RESOLVABLE: as regras deste arquivo seguem o script, inclusive bandeja 3, rush com spawn de 4–6 s e abertura só depois do dia 1. O README fica desatualizado até uma spec posterior.
- DEFERRED: corrigir o README, renomear o HTML para `index.html`, fazer `wrongOrders` contar algo, alinhar o texto da conquista de Chocolate Quente ao código, e qualquer mudança de regra.
