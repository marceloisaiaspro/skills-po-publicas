# Módulo 02 — Consolidação de atas, solicitações e feedback

**Objetivo:** transformar uma pilha de pedidos (ata, lista do cliente, WhatsApp, chamados, feedback) em temas auditáveis e encaminhados, sem perder a origem de nenhum item.

## 1. Inventário da fonte
- Conte os itens, o período e quem pediu (pessoa/cargo/cliente).
- Descarte duplicatas e mensagens que não são pedido — e diga quantos descartou e por quê.
- Declare o viés da fonte: chamado de suporte mostra o que quebra, não o que incomoda em silêncio; reunião de feedback mostra o que o participante lembrou naquele dia; lista enviada por escrito costuma ser a versão "oficial" e mais completa.
- **Conte por cliente, não só por item:** um cliente com dez mensagens sobre o mesmo ponto é um pedido.

## 2. Agrupar pelo problema, não pelo pedido
O cliente pede soluções ("botão", "relatório", "igual à rotina X"). Agrupe pelo **problema** que está por trás e registre as soluções pedidas dentro do tema.
- Bons temas têm **dono** (alguém reconhece como seu), são **distintos** (um item cabe claramente em um só) e **acionáveis** (dá para dizer em uma frase o que resolveria).
- "Usabilidade", "performance", "melhorias" não são temas — são gavetas. Desça um nível.

## 3. Classificar cada item
Para cada item: **tipo** e **encaminhamento** (módulo 01), **situação** e **origem**.

| Situação | Símbolo |
|---|---|
| Concluído, validado, testado e publicado | ✅ |
| Em atuação, com cards criados | 🔧 |
| Cards abertos, aguardando | 📋 |
| Alinhamento futuro (roadmap) | 🗓 |
| Precisa de reunião com o cliente / em análise | ❓ |
| Recusado ou fora de escopo (com motivo) | ⛔ |

## 4. Triagem para decidir o que detalhar agora
| # | Demanda | Tipo | Encaminhamento | Valor percebido | Recomendação |
|---|---|---|---|---|---|
| | | | | alto / médio / baixo / não demonstrado | Detalhar agora / Backlog / Recusar com justificativa |

Detalhe só o "Detalhar agora", na ordem de valor (priorização no módulo 03).

## 5. Achados que ninguém escreve
- **Achados negativos:** o que o time achava que era o maior problema e quase não apareceu.
- **Lacunas de expectativa:** pedidos de algo que o produto já faz.
- **Sinais de expectativa diferente do contratado:** muitos pedidos "igual ao sistema X" indicam que o cliente espera outro produto — leve isso ao PO como risco, não como lista de tarefas.

## 6. Volume
Até ~30 itens: consolide direto na conversa. Acima disso, registre item a item em arquivo (planilha/CSV) e conte com script — nunca estime percentuais de cabeça.

## 7. Saída
Página **Solicitações Consolidadas** (`templates/solicitacoes-consolidadas.md`): origem, como foi conduzido, resumo por situação, lista completa com responsáveis, item no board do cliente e item no backlog do produto, e o que estes dados **não** permitem afirmar.
