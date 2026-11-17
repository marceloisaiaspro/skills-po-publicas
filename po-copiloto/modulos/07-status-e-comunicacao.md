# Módulo 07 — Status report, Wiki e comunicação

## 1. Status report
**Estrutura na Wiki** (ver `templates/status-report.md`):
- **Página-índice por cliente:** situação atual (com semáforo), marco de entrega, tabela `Data | Relatório | Fase` e link para as Solicitações Consolidadas.
- **Relatório datado** (uma subpágina por data): cabeçalho, entregue e validado, pendentes, decisões e desdobramentos, linha do tempo (quando houver), **Leitura do PO**, próximos passos.

**Semáforo — use com honestidade:**
- 🟢 **No prazo:** sem risco relevante. Não é a cor padrão; é a cor de quando está mesmo bem.
- 🟡 **Em risco:** atraso ou risco materializado, com mitigação em curso. Mude para amarelo **no primeiro sinal**: quanto antes, mais opções.
- 🔴 **Fora do trilho:** sem mitigação ao alcance do time; precisa de decisão de fora (escopo, prazo, pessoas). Use quando precisar de ajuda, não quando já for tarde.
- Ao mudar de cor, escreva o motivo.

**Riscos (ROAM):** cada risco aparece como **Resolvido**, **Com dono** (quem e o que faz), **Aceito** (por que seguimos sem mitigar) ou **Mitigado** (o que foi feito). Risco sem plano não entra no relatório sem a frase "precisamos de…".

**Marcos que sempre entram:**
- **Forma do aceite** (documento, e-mail, mensagem, chamada) e quem validou.
- **Congelamento de escopo** antes do go-live: "a partir daqui, novas necessidades entram como melhoria".
- **Leitura do PO:** o que este momento significa (ex.: "primeiro sinal de que o cliente espera outro produto").

**Métricas de fluxo do board** (quando o relatório pedir ou o prazo estiver em risco):
- **Tempo total (lead time):** da criação do item até Closed. Responde "quanto o cliente espera por um pedido".
- **Tempo de execução (cycle time):** de In Progress até Closed. Responde "quanto o time leva para entregar".
- **Itens parados:** quantos estão há mais de X dias em **Impedimento**, **Code Review** ou **QA**. Sem QA dedicado, a fila de revisão é onde a entrega costuma travar.
- Use para mostrar gargalo e pedir ajuda, nunca para comparar pessoas. A ferramenta do board costuma calcular essas medidas.

**Saúde do cliente depois do go-live** (seção do status report ou revisão mensal):
| Sinal | O que olhar | Alerta quando |
|---|---|---|
| **Adoção** | Usuários ativos e uso da função principal (ex.: vendedores que enviaram pedido, pedidos enviados por semana) | Queda ou uso abaixo do combinado |
| **Atrito** | Chamados abertos e reabertos, tempo de resposta | Chamados subindo ou o mesmo problema voltando |
| **Expectativa** | Pedidos de algo que o produto não se propõe a fazer | Vários pedidos fora de escopo no mesmo tema |
| **Relacionamento** | Quem fala com a empresa, tom, escalonamentos | Sócio ou dono entrando na conversa; silêncio longo |
Dois sinais em alerta = semáforo 🟡 e conversa proativa com o cliente. Com poucos clientes, cada cancelamento pesa; o objetivo é ver o risco antes do distrato.

## 2. Versões por público (o mesmo fato, perguntas diferentes)
| Público | O que quer saber | Formato |
|---|---|---|
| **Liderança** | Estamos bem? Precisa de mim? | Semáforo + resumo em uma frase + decisões necessárias com prazo + riscos que precisam de ajuda. Até 200 palavras |
| **Cliente** | O que ganho e o que preciso fazer? | O que foi entregue, o que muda para ele, o que precisa validar, próximos passos, limitações |
| **Time** | O que muda para nós? | Contexto, decisões, prioridades, impedimentos |
| **Suporte** | O que vai mudar e o que eu respondo? | O que mudou na tela, perguntas frequentes com resposta pronta, problemas conhecidos e contorno, quando escalar |

## 3. Comunicação de entrega
- **Benefício antes da mecânica:** "o vendedor corrige o pedido rejeitado sem redigitar" antes de "nova tela de edição".
- **Limitação declarada gera confiança;** esconder só adia o chamado.
- **Não prometa data** do que ainda não foi construído.
- Marque com **[CONFIRMAR: …]** tudo o que foi suposto por falta de informação.
- Confira se nome, disponibilidade, data e limitações batem em todas as peças.

## 4. Mensagens prontas
Mensagens curtas para WhatsApp ou e-mail (recusa, congelamento de escopo, pedido de aceite, aviso de entrega, pedido de regras por escrito, retorno de escalonamento): `templates/mensagens-cliente.md`.

## 5. Saída
Página ou relatório no template, pronto para colar na Wiki (ou gravar via MCP somente após confirmação), e a versão para cada público pedido.
