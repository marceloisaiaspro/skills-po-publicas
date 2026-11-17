# Módulo 01 — Triagem de demanda

**Objetivo:** antes de escrever qualquer item, decidir **o que a demanda é** e **para onde ela vai**. Triagem errada custa caro: escopo novo tratado como bug interrompe a Sprint e distorce a qualidade; bug tratado como melhoria deixa o cliente com o produto quebrado.

## 1. Pergunta-chave: havia uma promessa?
- **Funcionava antes, ou a regra estava combinada/documentada, e agora não funciona** → **Defeito (Bug)**.
- **Nunca foi prometido** → não é bug, mesmo que o cliente chame de bug. É evolução, parametrização ou lacuna de expectativa.
- **Na dúvida**, procure a promessa: escopo contratado, critérios de aceite, status report, Wiki. Sem promessa encontrada, trate como evolução e diga ao PO por quê.

## 2. Os 7 tipos de item
| Tipo | Sinais | O que gerar |
|---|---|---|
| **História** | Necessidade nova ou mudança de comportamento para quem usa | Encaminhar à po-historias-de-usuario |
| **Bug** | Regra existente quebrada | Card de Bug (po-historias-de-usuario), com severidade |
| **Spike** | O time não consegue estimar por falta de conhecimento | Pergunta a responder, prazo máximo, entregável; tag `Em Análise` |
| **Débito Técnico** | Trabalho técnico sem comportamento novo (atualização, segurança) | Justificativa de risco: risco se não fizer, prazo limite, impacto |
| **Parametrização** | Configurar o que já existe, sem código | Somente Task PO; se surgir código, vira História |
| **Requisito Transversal** | Regra que vale para todo o produto (LGPD, desempenho) | Registrar na DoD/Wiki + História de adequação |
| **Sem valor demonstrado** | Valor não identificável ou pedido isolado de baixo impacto | Recusa ou adiamento argumentado (módulo 03) |

## 3. Os 5 tipos de encaminhamento (o que a demanda pede ao produto)
| Encaminhamento | O que é | Para onde vai |
|---|---|---|
| **Defeito** | O produto prometeu e não entrega | Correção, fora do ciclo de roadmap; se concentrado após uma publicação, tratar como incidente |
| **Atrito** | Funciona, mas custa caro: passos demais, lento, confuso, exige gambiarra | Melhoria priorizada, com medida antes/depois |
| **Capacidade ausente** | O produto não faz e não prometeu fazer | Análise de iniciativa (módulo 04) antes de construir |
| **Lacuna de expectativa** | O produto já faz, mas o cliente não sabe, não acha ou entendeu diferente | Treinamento, comunicação, nome na tela — quase sempre mais barato que código |
| **Fora de escopo** | Pedido legítimo que a estratégia não vai atender | Recusa explícita e comunicada; registrar para revisitar |

**Testes rápidos:**
- **Atrito ou capacidade ausente?** Se um usuário experiente consegue chegar ao resultado hoje, por mais penoso que seja, é atrito.
- **Lacuna de expectativa?** Para todo "não dá para fazer X", confira se X já existe. Achar uma lacuna de expectativa grande é o melhor resultado possível de uma triagem.

## 4. Pedido misturado
Quando um item mistura defeito e escopo novo (ex.: "o filtro não funciona — e coloquem um botão Todos"), **separe**: o defeito vira Bug; o restante vira História com origem registrada. Avise o PO e explique a separação ao cliente.

## 5. Saída
```
Tipo: <um dos 7> · Encaminhamento: <um dos 5>
Por quê: <a promessa encontrada (ou a ausência dela), em 1–2 frases>
Épico / Feature sugeridos: <conforme o contexto da empresa>
Próximo passo: <encaminhar para…, perguntar a…, recusar com…> — dono e prazo
Perguntas em aberto: <se houver>
```
