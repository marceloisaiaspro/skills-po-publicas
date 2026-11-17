# Módulo 09 — Estratégia de produto e portfólio

**Objetivo:** ligar o backlog do dia a dia a uma direção. Sem visão e roadmap, priorizar vira escolher entre pedidos; com eles, vira escolher o que leva o produto aonde ele precisa chegar.

**Quando usar:** início de ano ou semestre, conversa com a liderança, produto novo, decisão de onde investir o time entre vários produtos. Uso ocasional — não precisa rodar a cada sprint.

## 1. Visão do produto (uma frase e quatro linhas)
- **Frase:** "Para [quem], que [problema], o [produto] é [categoria] que [benefício principal]. Diferente de [alternativa atual], [diferencial]."
- **Para quem:** persona principal e quem decide a compra (em B2B, raramente a mesma pessoa).
- **Problema:** o que acontece hoje sem o produto.
- **O que o produto é e não é:** reaproveite o "É / Não é" do módulo 05.
- **Como saberemos que está funcionando:** a North Star (seção 2).
Visão boa ajuda a dizer não: se o pedido não aproxima o produto da visão, o ônus de provar valor é de quem pede.

## 2. North Star e métricas de apoio
- **North Star:** **uma** métrica que mostra o valor que o cliente recebe — não a receita da empresa. Ela sobe quando o cliente ganha.
- **Métricas de apoio (2 a 4):** o que o time consegue mover e que empurra a North Star (adoção, frequência, qualidade, tempo).
- **Guardrails (1 a 2):** o que não pode piorar enquanto a North Star sobe (chamados, erros de integração, tempo de resposta).
- **Teste:** "se esta métrica subir, o cliente está mesmo melhor?" e "dá para medir hoje?". Se não dá, medir vira item de backlog.
- Candidatas por produto ficam no arquivo de contexto da empresa, **marcadas como a validar** com a liderança.

## 3. Roadmap por resultado (Agora / Próximo / Depois)
| | Agora (em curso) | Próximo (definido, ainda não começou) | Depois (direção, sem compromisso) |
|---|---|---|---|
| **Resultado buscado** | | | |
| **Iniciativas** | | | |
| **Como medimos** | | | |
Regras:
- Cada linha é um **resultado** ("reduzir pedidos rejeitados pelo ERP"), não uma lista de funcionalidades.
- **Datas só no "Agora"**; "Próximo" e "Depois" não levam data — levam condição.
- Toda entrada no roadmap aponta o que sai ou atrasa (mesma regra do escopo no módulo 04).
- Clientes enxergam o "Agora" e, no máximo, o "Próximo". "Depois" é conversa interna.
- **OKR:** use só se a empresa já trabalha com OKR. Nesse caso, o objetivo é o resultado da linha do roadmap e os resultados-chave são as métricas de apoio.

## 4. Análise de cenário — SWOT por produto
| | Ajuda | Atrapalha |
|---|---|---|
| **Interno (sob nosso controle)** | Forças | Fraquezas |
| **Externo (fora do nosso controle)** | Oportunidades | Ameaças |
Regras de honestidade:
- **Cada item com evidência** (cliente perdido, chamado, pedido recorrente, mudança de lei, concorrente concreto). Item sem evidência é suposição — marque assim.
- **Cruze os quadrantes** para virar ação: força × oportunidade = onde atacar; fraqueza × ameaça = onde se proteger primeiro.
- Fatores externos que mais pesam em produto B2B integrado a ERP: **legislação e regras fiscais, mudanças do fornecedor do ERP, LGPD e o movimento dos concorrentes**. Lei nova costuma virar **requisito transversal** (módulo 01).

## 5. Portfólio — onde investir o time (matriz BCG adaptada)
A matriz BCG original pede crescimento de mercado e participação de mercado — dados que quase nunca existem em nichos B2B. Use a versão adaptada, com o que se consegue observar:
| | Demanda crescendo (pedidos, vendas novas, interesse) | Demanda estável ou caindo |
|---|---|---|
| **Produto forte** (clientes ativos, receita, poucos problemas) | **Investir:** evolução e escala | **Sustentar:** estabilidade, correções, retenção; pouca novidade |
| **Produto fraco** (poucos clientes, problemas recorrentes) | **Apostar com limite:** descoberta rápida e prazo para decidir se continua | **Aposentar ou congelar:** plano de saída, migração dos clientes, liberar o time |
- Classifique cada produto com **evidência**, não com afeto. Diga quais dados faltam.
- O quadrante define o **tipo de trabalho** que domina o backlog do produto (evolução, sustentação, descoberta ou saída) e ajuda a dividir a capacidade do time entre produtos.
- Decisão de aposentar ou congelar um produto vai para o **módulo 06** (one-pager).

## 6. Produto ou módulo novo (opcional)
Quando a pergunta for "vale criar este produto?", resuma numa página:
- **Proposta de valor:** de um lado, as tarefas, dores e ganhos de quem usa; do outro, como o produto alivia cada dor e cria cada ganho. Dor sem resposta = lacuna; resposta sem dor = desperdício.
- **Modelo em uma página:** problema, segmento, proposta de valor, solução, canais, receita, custos, métrica-chave e vantagem difícil de copiar.
Depois, siga para o **módulo 04** (riscos e premissas).

## 7. Saída
Visão, North Star e roadmap em `templates/roadmap-visao.md`; SWOT e portfólio no mesmo arquivo, quando pedidos. Decisões de investimento ou de aposentadoria → módulo 06.
