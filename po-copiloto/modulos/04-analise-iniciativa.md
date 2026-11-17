# Módulo 04 — Análise de ideia ou iniciativa

**Objetivo:** antes de construir, responder "vale a pena?" e transformar a resposta numa descrição de Épico ou Feature que o time entenda sem reunião.

## 1. Problema antes da solução
- **Problema** em 2–3 frases, na linguagem de quem sofre com ele, **com evidência** (pedidos, chamados, dados de uso, perda de cliente). Sem evidência, marque como hipótese.
- **Para quem** (persona) e **com que frequência**.
- **Por que agora:** o que mudou. Sem isso, tudo parece igualmente urgente.
- **Trabalho a ser feito:** "Quando [situação], quero [motivação], para [resultado]."
- **Armadilha da paridade:** pedido "igual ao sistema X / à rotina Y" → descubra qual problema o sistema X resolve para o cliente. Copiar comportamento não convence; resolver o problema, sim.
- **Ligação com o objetivo (árvore de oportunidades, versão curta):** objetivo do produto ou do cliente → oportunidade (a dor ou necessidade) → soluções possíveis (pelo menos 2) → teste de cada uma. Evita apaixonar-se pela primeira solução e mostra para que a iniciativa serve.

## 2. Os 4 riscos (Marty Cagan)
| Risco | Pergunta | Quem responde |
|---|---|---|
| **Valor** | O cliente vai usar ou pagar por isso? | PO/PM |
| **Usabilidade** | Quem usa vai conseguir usar? | Design (ou o PO, quando não houver designer) |
| **Viabilidade técnica** | Dá para construir com o tempo, as pessoas e a tecnologia que temos? | Tech lead |
| **Viabilidade de negócio** | Funciona para a empresa (comercial, contrato, suporte, jurídico, custo)? | PO/PM |

## 3. Premissas
**Comece pela Matriz CSD:** o que é **Certeza** (com evidência), **Suposição** (acreditamos, sem prova) e **Dúvida** (não sabemos). Suposições e dúvidas viram as premissas abaixo ou perguntas com dono.
Liste as premissas — ditas e não ditas — por categoria: **de quem usa** (eles querem isso?), **do problema** (é frequente? importa?), **da solução** (resolve?), **do negócio** (move qual indicador?), **de viabilidade** (dá para fazer?) e **de adoção** (vão encontrar e usar?).
Aponte a **mais arriscada** — a que, se errada, mata a ideia — e o **teste mais barato** para ela antes de construir (conversa com o cliente, protótipo, operação manual, piloto com um cliente).

## 4. Escopo
- **Nesta entrega**
- **Fora desta entrega** (fica para depois)
- **Decidido que não faremos** (não volta à discussão)
Toda inclusão de escopo vem acompanhada de uma retirada ou de mais prazo. Ideias boas fora de escopo vão para um "estacionamento".

## 5. Resultado esperado (versão curta)
- **Indicador principal:** valor atual → meta → prazo (ou "a medir" / "a definir").
- **Guardrail:** o que não pode piorar (ex.: chamados de suporte, tempo de resposta).
- **Contra-leitura:** como esse número poderia subir sem nada de bom acontecer?
- **Como medir:** se o dado não existe hoje, medir vira requisito.
- **Retorno financeiro (quando houver número):** ganho ou economia por mês ÷ custo de construir e sustentar = em quantos meses se paga. Sem número confiável, diga "a estimar" — não invente.
- **Experimento:** com poucos clientes B2B, teste A/B raramente é viável. Prefira piloto com um cliente, liberação gradual e acompanhamento do guardrail — e diga isso.

## 6. Saída
Descrição de Épico/Feature (`templates/analise-iniciativa.md`). Depois, encaminhe à **po-historias-de-usuario** para o fatiamento em histórias.
