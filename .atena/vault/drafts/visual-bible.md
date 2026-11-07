---
id: "DRAFT-VISUAL-001"
type: "vision"
title: "Café Aurora — bíblia visual inicial"
status: "draft"
revision: 1
origin: "post-hoc"
maturity: "DRAFT"
created: "2026-11-07"
canonical: false
sources:
  - "Café Aurora — Protótipo de Playtest.html"
---

# Bíblia visual — Café Aurora

Rascunho de trabalho, revisão 1, origem pós-hoc. Cobre só o que o protótipo HTML já mostra. Não autoriza gerar imagem, comprar asset nem escolher motor. Produção visual de especialista não começa neste ciclo: não há identidade de personagem aprovada nem pedido de cena.

## Intenção e revisão

- Revisão: 1, em 2026-11-07.
- Liga a [vision.md](vision.md) e a [design.md](design.md).
- Intenção artística observada: cafeteria quente, legível, com ícones grandes e pouco texto de sistema. O rush esquenta a página inteira, não só um selo.
- Cobertura deste rascunho: interface do protótipo. Não define sprites, cenário ilustrado nem animação de personagem.
- Estado: proposto. Nenhum trecho está aprovado.

## Referências anotadas

| Referência | Aspecto | Uso | Condições | Estado |
| --- | --- | --- | --- | --- |
| O próprio HTML do protótipo | Paleta, hierarquia e ícones emoji | Evidência do que já está na tela | Arquivo do repositório | proposto |
| Inter, carregada de fonts.googleapis.com | Texto da interface | Fonte já ligada na página | Uso via CDN; não é um asset vendorizado no repo | proposto |
| basecoat-css 1.0.2, via jsDelivr | Casca de página | CSS já ligado na página | Uso via CDN | proposto |

Não há prancha de referência externa. Não tratar emoji, fonte ou CSS de CDN como pacote de arte reutilizável fora do protótipo.

## Linguagem visual

- Dimensão e estilo observados: interface 2D plana, ilustrada por emoji e cartões, não por sprites.
- Formas: cartões de pedido, barras de paciência, chips de ingrediente, modais de balanço e de abertura.
- Paleta observada no CSS do jogo: fundo `--coffee-cream` `#fbf6ee`, texto `#2b1810`, destaque `--accent` `#b25329`, âmbar `#d97736`, grão `#4a2711`, borda `#e3d2be`. Cabeçalho em degradê `#3d1f0e` para `#693418`.
- Rush: aviso com fundo `#faede0`; rush ativo com fundo `#fce1cb` e borda dos pedidos `#e25822`. O fim do rush usa um banner verde.
- Câmera: página única rolável, sem câmera de jogo. Leitura de cima para baixo: estado da loja, bancada, mesas, últimos pedidos, roteiro de playtest.
- Há também tokens de uma casca clara/escura no começo do arquivo (`--bg`, `--surface`). O `body` do jogo fixa o fundo creme por cima dessa casca.

## Personagens, props e ambientes

| Categoria | Regra visual observada | Necessidade do protótipo | Limite | Pendência |
| --- | --- | --- | --- | --- |
| Clientes | Só nome e pedido. Sem corpo, roupa ou retrato | Nenhum sprite | Não desenhar neste ciclo | Identidade visual não se aplica ainda: não há personagem desenhado |
| Bebidas e insumos | Emoji mais nome e preço | Os quatro ingredientes e as cinco receitas | Reusar o que a página já mostra | Nenhum asset novo |
| Loja | Balcão com 3 pedidos, 4 mesas, cafeteira, bandeja | Layout HTML atual | Um arquivo | Cenário ilustrado adiado |

## Interface e acessibilidade

- Hierarquia: dinheiro, reputação, dia e estoque no topo; a ação de servir é o botão grande; o rush ganha faixa e mudança de fundo.
- Ícones emoji acompanham o nome. Cor não é o único sinal de pressa: a barra mostra segundos restantes. O rush também muda o texto do selo.
- Tutorial: faixa com uma frase e tooltips curtos. Há botão para pular ao dia 2.
- Estados de erro usam texto, além de vermelho. O DevLog repete o cálculo em palavras.
- Tamanho de tela: o layout quebra em colunas flexíveis. Não houve revisão de contraste, leitor de tela ou alvo de toque.

## Animação, efeitos e retorno

| Ação ou estado | Resposta observada | Leitura | Fidelidade deste protótipo |
| --- | --- | --- | --- |
| Servir | Barra da cafeteira enche em 1,5 s ou 2 s | A espera é visível | Manter a duração legível |
| Acerto e erro | Banner de feedback e bipe | Sucesso e perda se distinguem | Sem animação de personagem |
| Rush | Fundo, selo e banner | O pico é impossível de ignorar | Sem efeito de partícula |
| Receita nova | Toast "disponível amanhã" | O desbloqueio não libera o pedido no mesmo dia | Sem ilustração da bebida |

## Restrições de produção

- Volume: zero sprites. A página é o placeholder.
- Capacidade registrada: não há equipe de arte, prazo nem orçamento no repositório.
- Reuso: continuar com emoji e CSS até um playtest dizer que a leitura do loop falhou por causa da apresentação.
- Implicação para uma recomendação técnica futura: o motor, se um dia for escolhido, precisa suportar interface 2D densa, texto, ícones e uma troca clara de estado no rush. Isso não escolhe Godot nem permanece no HTML.

## Revisão e pendências

| Tema | Critério | Evidência | Classe | Próximo passo |
| --- | --- | --- | --- | --- |
| Direção aprovada | Um texto desta revisão marcado como aprovado | Só o CSS do protótipo | BLOCKING para arte e para motor | Não produzir arte agora |
| Leitura do rush e da paciência | O jogador percebe pressa e destino da bebida | Ainda sem sessão | BLOCKING para a próxima decisão | Playtest 001 |
| Sprites e cena | Fora do loop testado | Não há identidade nem cena pedida | DEFERRED | Depois da direção aprovada |
| Contraste e toque | Revisão própria | Não feita | DEFERRED | Spec de interface, se o playtest apontar barreira |

Gerar imagem ou baixar asset pede outra spec. Este texto basta para não escolher ferramenta no escuro.
