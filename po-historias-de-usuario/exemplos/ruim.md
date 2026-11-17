# Exemplos ruins — e como corrigir

*(Casos fictícios, inspirados em erros comuns de backlog.)*

## Ruim A — História sem cartão e com três funcionalidades
> "Informar o motivo da recusa do pedido. Permitir editar o pedido recusado. Permitir reenviar. Deve ser possível saber o motivo, editando ou apenas reenviando…"

- **Problemas:** sem persona e sem "para"; três fluxos numa história só (falha em Sob Medida); critérios vagos ("deve ser possível") e com "ou".
- **Correção — cartão:** *"Eu como vendedor externo quero corrigir um pedido recusado sem redigitá-lo para reduzir o retrabalho de montar o pedido outra vez."*
- **Correção — fatiamento por fluxo:** bloco 1 exibir o motivo; bloco 2 corrigir e reenviar (ver `boa.md`, Exemplo 3); bloco 3 reenviar sem editar.

## Ruim B — Escopo novo escondido num Bug, por camada e sem ordem
> "Os filtros do histórico não funcionam… se possível, incluir um botão Todos e transformar o campo vendedor em lista."
> Comentário: *"O front diz que depende do back, e o back diz que depende do banco."*

- **Problema 1 — triagem:** mistura um defeito real (filtro de data errado) com escopo novo (botão "Todos", lista de vendedores).
- **Problema 2 — ordem:** três cards sem dizer quem começa; o item ficou rodando entre as camadas.
- **Correção:** Bug só do filtro, com **ordem entre camadas** (*1º Banco → 2º Back → 3º Front*); História separada para o botão e a lista.

## Ruim C — Task só com título e print
> Descrição: o próprio título e uma imagem.

- **Problema:** o dev trabalha olhando o card e raramente abre a História. Sem contexto e critérios, cada um interpreta de um jeito.
- **Correção:** card autossuficiente (Modelo B) com contexto, critérios, ordem entre camadas, execução e validação.

## Ruim D — Item detalhado demais
> Uma história de "ocultar a promoção para um cliente" com 25 critérios, nomes de tabelas, colunas, regras de três sistemas e cinco Tasks por camada para um time de duas pessoas.

- **Problema:** ninguém lê; o essencial (o que muda e para quem) se perde; o PO teve que pedir para simplificar.
- **Correção:** cartão curto, 6 critérios testáveis e uma Task por pessoa (ver `boa.md`, Exemplo 2). Detalhes técnicos ficam com quem implementa ou num link para a documentação.

## Ruim 1 — Tarefa técnica escrita como História
> "Criar o worker e a tabela de fila para consumir a API do marketplace."

- **Problema:** sem persona e sem benefício (falha em Valorosa).
- **Correção:** *"Eu como analista de faturamento quero receber os pedidos aprovados no marketplace para eliminar a digitação manual."* Worker e tabela vão para a execução dos cards técnicos.
- **Exceção:** trabalho sem comportamento novo para quem usa o produto (ex.: atualizar framework) é **Débito Técnico**, sem persona forçada.

## Ruim 2 — Épico inteiro num cartão
> "Como usuário, quero um módulo de atendimento com fila do WhatsApp, abertura de chamado em popup, quadro Kanban e encerramento por inatividade."

- **Problemas:** "usuário"; épico inteiro numa frase; solução visual ("popup") no cartão.
- **Correção (fatiar pelo fluxo):** *"Eu como atendente de suporte quero registrar um chamado a partir de um atendimento em andamento para reduzir a digitação."*

## Ruim 3 — Tela no cartão, advérbio vago e "para" que repete o "quero"
> "Eu como supervisor quero consultar rapidamente os pedidos no Dashboard para ter os pedidos consultados."

- **Correção:** *"Eu como supervisor comercial quero acompanhar o total vendido por vendedor da minha equipe para identificar quem está abaixo da meta."* Critérios: *"Os totais carregam em até 3 segundos."* Pergunta: *"A meta é diária, semanal ou mensal?"*

## Ruim 4 — Fatiamento que cria dependência
> H-A: *"…cadastrar respostas prontas"* · H-B: *"…inserir respostas prontas durante a conversa"*

- **Problema:** H-B depende de H-A, e o valor só aparece com as duas (falha em Independente).
- **Correção:** entregar H-B primeiro, com a carga inicial feita por uma Task do PO; ou unir as duas numa história com dois blocos.
