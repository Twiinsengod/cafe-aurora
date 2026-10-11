# ☕ Café Aurora

Jogo 2D de gerenciamento de recursos em uma cafeteria, desenvolvido como protótipo jogável para validação de design. O jogador opera uma pequena cafeteria: compra ingredientes, prepara bebidas conforme os pedidos chegam e serve rápido para manter a reputação da loja.

## 🎮 Como jogar

1. **Abertura da Loja** — antes de cada dia, compre ingredientes e pré-monte até 2 bebidas (prep-ahead).
2. **Expediente** — clientes chegam no balcão (até 3 pedidos simultâneos) e nas 4 mesas.
3. **Preparo** — clique nos ingredientes para montar a receita e sirva. A bebida pronta vai automaticamente para o pedido compatível mais impaciente.
4. **Fim do dia** — balanço com lucro, satisfação e clientes perdidos. Dinheiro < R$ 10 ou reputação 0 = game over.

## 📋 Receitas

|
 Receita 
|
 Ingredientes 
|
 Preço 
|
|
---
|
---
|
---
|
|
 Café Preto 
|
 café 
|
 R$ 8 
|
|
 Latte 
|
 café + leite 
|
 R$ 12 
|
|
 Mocha 
|
 café + leite + chocolate 
|
 R$ 16 
|
|
 Chocolate Quente 
|
 leite + chocolate 
|
 R$ 13 
|
|
 Café Gelado 
|
 café + gelo 
|
 R$ 11 
|

Receitas especiais são desbloqueadas por conquistas e ficam disponíveis somente no dia seguinte.

## ⭐ Sistemas

- **Tutorial guiado** — dia 1 ensina fazendo, com tooltips curtos e sem punição (acessível para crianças e idosos).
- **Hora do Rush** — a partir do dia 4, um pico no meio do expediente: paciência menor, penalidade dobrada, gorjeta dobrada.
- **Conquistas** — marcos desbloqueiam receitas especiais (ex.: servir 10 cafés pretos → Mocha).
- **DevLog** — registro cronológico de todos os eventos com cálculos (preço + gorjeta, penalidades, balanço do dia), copiável para análise.
- **Relatório de Run** — estatísticas completas ao fim da partida, com histórico das últimas 10 runs salvo no navegador.

## 🛠️ Tecnologia

Protótipo em HTML/CSS/JavaScript puro, arquivo único, sem dependências. Para jogar, basta abrir o `index.html` no navegador.

## 🚀 Roadmap

- [ ] Migração para Godot 4 (versão final do jogo)
- [ ] Novos ingredientes e receitas
- [ ] Upgrades de máquinas na Abertura da Loja
- [ ] Tipos de clientes especiais (executivo, crítico gastronômico)

## 📄 Licença

MIT — veja o arquivo LICENSE.
