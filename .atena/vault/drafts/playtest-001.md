---
id: "DRAFT-PLAYTEST-001"
type: "requirement"
title: "Playtest 001 — loop do Café Aurora"
status: "draft"
revision: 1
origin: "post-hoc"
maturity: "DRAFT"
created: "2026-11-07"
canonical: false
result: "pending"
sources:
  - "Café Aurora — Protótipo de Playtest.html"
---

# Playtest 001 — loop do Café Aurora

Plano de teste, revisão 1. O roteiro de quatro perguntas já estava na página antes deste arquivo. A sessão em si não aconteceu. Resultado: pendente. Quando alguém jogar, o relato vai para `.atena/evidence/PLAYTEST-001.md`, sem apagar este plano.

Este teste investiga se o loop já implementado se entende e se sustenta até o primeiro rush. Não investiga Godot, arte nova nem regras novas.

## Briefing para quem joga

- O que se investiga: se a pessoa entende o expediente, consegue comprar, montar e entregar, e se o DevLog, a espera da receita nova, a entrega ao mais impaciente e o balanceamento atual parecem justos.
- Build: o arquivo `Café Aurora — Protótipo de Playtest.html` neste repositório, aberto no navegador. Não há número de versão além desta revisão de documento.
- Quem joga: uma pessoa, de preferência Fabio, sozinha, sem explicação além do tutorial da tela. Duração esperada: do dia 1 até o fim do rush do dia 4, alguns minutos, ou até o game over se acontecer antes.
- Limites: interface de protótipo com emoji, sem sprites. O dia 1 pode ser pulado pelo botão da tela; para este teste, não pular. O relatório automático da run só grava no `localStorage` quando a partida acaba em game over, então uma partida que continua depois do dia 4 pode não gerar esse arquivo sozinha. Nesse caso, copiar o DevLog e anotar caixa, reputação, atendidos e perdidos à mão.

## Procedimento

| Passo | Ação | O que observar | Critério ou pergunta | Evidência |
| --- | --- | --- | --- | --- |
| 1 | Abrir o arquivo e jogar o dia 1 inteiro, sem pular | Onde há dúvida e se os 3 clientes do tutorial fecham o dia | A pessoa executa a ação central sem ajuda externa | Notas da sessão |
| 2 | Na abertura do dia 2, comprar e, se quiser, pré-montar | Se a compra e a bandeja de 3 ficam claras | A pessoa relaciona estoque e caixa | Notas |
| 3 | Seguir até o dia 4 e atravessar o rush | Ritmo, perdas, gorjeta e sensação de controle | Ajuste cafeteira 2 s, gorjeta mínima, bandeja 3, mesa 40 s e rush com spawn ainda de 4–6 s | DevLog copiado e notas |
| 4 | Se uma conquista abrir, olhar o dia seguinte | Expectativa ou frustração com a receita que só entra amanhã | Pergunta já impressa na página | Notas |
| 5 | Responder as quatro perguntas abaixo com palavras próprias | Clareza, justiça e diversão | Resposta humana, não métrica | Texto da pessoa |

Perguntas, copiadas do sentido da seção "Roteiro de Playtest" da página:

1. O DevLog ajudou a entender o que aconteceu e os cálculos de preço, gorjeta, penalidade e balanço?
2. Esperar um dia para usar a receita nova criou expectativa ou frustração?
3. A entrega automática ao pedido compatível mais impaciente funcionou bem?
4. Com cafeteira de 2 s, gorjeta mínima, bandeja de 3, mesa de 40 s e rush menos denso, a partida ficou mais justa e a sensação de controle se manteve no horário cheio?

## Responsabilidades

- Documentação e checagem técnica: conferir se o arquivo abre e se as regras descritas no design batem com o script. Isso não mede diversão.
- Quem joga: diz, com as próprias palavras, como foi o controle, a dificuldade e o gosto.
- Métrica e julgamento de modelo não provam que o jogo é bom. Como ninguém jogou, o playtest permanece pendente.

## Aceite e avanço

- Critério apoiado por este teste: a hipótese do primeiro jogável em [prototype-readiness.md](prototype-readiness.md).
- Feedback humano necessário: as quatro perguntas. Responsável: quem jogar.
- Resultado pendente bloqueia a próxima spec de design ou de motor: sim. Não bloqueia o fechamento da reconciliação documental da SPEC-001.
- Feedback que pode esperar: contraste, toque, sprites, Godot.

## Resultados — só depois do teste

- Estado: pendente.
- Data, build jogado e participantes: nenhum.
- Checagens técnicas feitas nesta revisão: leitura do script e do README. Navegador não foi aberto nesta sessão de documentação.
- Observações de jogador: nenhuma.
- Controle, dificuldade e diversão: pendentes.

| Pergunta | Evidência | Resultado | Incerteza |
| --- | --- | --- | --- |
| DevLog | — | pendente | — |
| Receita no dia seguinte | — | pendente | — |
| Entrega ao mais impaciente | — | pendente | — |
| Balanceamento do rush | — | pendente | — |

## Decisão seguinte

- Decisão: não continuar para conteúdo novo nem para motor enquanto este teste estiver pendente.
- Próxima ação: jogar e gravar o relato em `.atena/evidence/PLAYTEST-001.md`.
- Impacto canônico: nenhum. Um resultado futuro pode propor revisão de regra; não reescreve este rascunho sozinho.
