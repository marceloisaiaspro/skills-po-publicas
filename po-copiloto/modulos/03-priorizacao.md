# Módulo 03 — Priorização e recusa argumentada

**Princípio:** framework não decide; ele obriga a mostrar as premissas da decisão. **Nenhuma nota sem premissa declarada** — nota sem premissa é opinião com casas decimais.

## 1. Antes de pontuar
- **Normalize:** não compare "redesenhar a tela" com "trocar um texto". Agrupe ou quebre antes.
- **Tire da competição** o que entra por outra via: bug crítico, obrigação legal, compromisso contratual, bloqueio de outro time. Liste com o motivo.
- **Pergunte a capacidade** do time (ou declare a suposição).

## 2. Escolha do método
| Situação | Método | Em uma frase (para o Professor explicar) |
|---|---|---|
| Itens comparáveis, sem prazo externo | **RICE** (padrão) | Alcance × Impacto × Confiança ÷ Esforço |
| Prazo externo real (contrato, lei, go-live) | **Custo do atraso** | Quanto valor se perde por semana de espera; divida pela duração |
| Definir o mínimo de um produto ou entrega para um cliente | **Kano** | Básico (falta irrita), desempenho (quanto mais, melhor), encantamento (surpreende), indiferente (ninguém nota), reverso (incomoda quem usa). Cubra os básicos primeiro; indiferente sai; reverso vira configurável ou não entra |
| Cortar o escopo de uma entrega já decidida | **MoSCoW** | Must / Should / Could / Won't. Pode ser feito em sessão com os stakeholders: eles classificam, o PO ordena |
| Muitas solicitações de um mesmo cliente, "tudo é urgente" | **Compre uma funcionalidade** | O cliente distribui 100 pontos entre os pedidos; o que recebe mais pontos vale mais para ele. Revela a ordem real e divide a responsabilidade da escolha |
| Muitas dependências e itens que destravam outros | **WSJF** | (valor + urgência + risco reduzido) ÷ tamanho |
| Conversa rápida em reunião | **Valor × Esforço** | Faça primeiro o de alto valor e baixo esforço; não faça o de baixo valor e alto esforço |

## 3. Regras de honestidade
- **RICE:** escolha um período fixo para o alcance (padrão: trimestre). Impacto: 3 massivo, 2 alto, 1 médio, 0,5 baixo, 0,25 mínimo — e diga **impacto em quê**. Confiança: 100% só com dado direto; 80% evidência forte; 50% qualitativa; 20% palpite. **Abaixo de 50%, a recomendação é investigar**, não decidir. Esforço inclui revisão, testes e homologação.
- **MoSCoW:** se mais de 60% está em Must, a classificação foi contornada. O **Won't** é a coluna mais valiosa: registra o que não será feito e evita rediscussão.
- **Kano sem ouvir o cliente** é hipótese do time — rotule assim. Exemplos de **reverso**: um campo obrigatório a mais ou uma confirmação extra que atrasa quem usa.
- **Classificação dos stakeholders é insumo, não decisão** (MoSCoW em sessão, Compre uma funcionalidade). A ordem final considera também **risco e dependências técnicas** (entre camadas, com o ERP, com outro time) e é do PO.
- **Esforço vem do time.** O PO não estima sozinho; story points e velocidade são ferramentas do time, não medidas de valor.
- **Empates:** notas a menos de ~20% uma da outra estão empatadas; a escolha entre elas é estratégica.
- **Teste de sensibilidade:** para os 3 primeiros, qual premissa, se errada, inverte a ordem? Se uma premissa fraca sustenta o topo, esse é o achado principal.
- **Framework como escudo:** se a decisão já foi tomada e o número só vai justificá-la, diga isso com clareza.
- **Decisão da liderança contrária:** registre no módulo 06 (quem decidiu, impacto, consequências) e siga.

## 4. Quando refazer a priorização
Revise a ordem quando houver: **informação nova** (dado, chamado, resposta do cliente), **escalonamento**, **mudança de capacidade** do time, **fim de uma entrega ou go-live**, ou na cadência combinada (ex.: a cada sprint). Priorização feita uma vez e esquecida vira lista de desejos.

## 5. Tradução para o board
- **Urgente** → prioridade mais alta do board + tag `PRIORIDADE`.
- **Padrão** → prioridade padrão, sem a tag.
- Spike ou investigação → tag `Em Análise`.

## 6. Recusa ou adiamento argumentado
Estrutura da resposta ao solicitante:
1. **Reconheça** o pedido e o problema por trás dele.
2. **Mostre o custo:** o que deixaria de ser feito.
3. **Explique** por que não agora (critério, não opinião).
4. **Ofereça alternativa** (contorno, versão menor, lacuna de expectativa resolvida com treinamento).
5. **Diga o que mudaria a decisão** (a pergunta que destravaria o valor).
6. **Diga quando** o assunto volta a ser avaliado.
Mensagem pronta em `templates/mensagens-cliente.md`.

## 7. Saída
```
Premissas gerais: período, métrica de impacto, origem do esforço, o que ficou de fora
| # | Item | (colunas do método) | Nota | Premissa crítica (≤10 palavras) |
Fora da competição: item — motivo
Recomendação: top N dentro da capacidade; o que fica de fora e por quê
Sensibilidade: premissas que mudam a ordem e como validá-las barato
Investigar antes de decidir: itens com confiança < 50%
No board: prioridade e tags de cada item
```
