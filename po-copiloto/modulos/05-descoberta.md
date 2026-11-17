# Módulo 05 — Descoberta: planejamento de implantação e levantamento de requisitos

**Objetivo:** fazer o cliente, a empresa e o time entenderem **a mesma coisa** antes de construir. A maior parte dos projetos que dão errado já estava errada no planejamento: o cliente esperava um produto e comprou outro.

## 1. Kick-off (início de implantação ou de iniciativa grande)
Checklist:
- [ ] O que foi contratado (escopo, prazo, responsáveis dos dois lados).
- [ ] **O que o cliente acha que comprou** — pergunte com as palavras dele e compare com o contratado.
- [ ] **É / Não é / Faz / Não faz** (obrigatório em implantação — seção 2).
- [ ] **Matriz CSD** do projeto (seção 2.1).
- [ ] Mapa de stakeholders (seção 3).
- [ ] Acessos e pré-requisitos (ambiente, banco, ERP, parametrizações).
- [ ] Combinado de comunicação: canal, frequência do status report, quem aprova.
- [ ] **Como será o aceite** de cada entrega (seção 6).

## 2. É / Não é / Faz / Não faz (Lean Inception, Paulo Caroli)
Preencha com o cliente, em uma conversa curta, e registre na Wiki:
| O produto **É** | O produto **NÃO É** |
|---|---|
| | |
| O produto **FAZ** | O produto **NÃO FAZ** |
| | |
**Use as colunas "Não é" e "Não faz" para nomear o que o cliente pode estar esperando** (ex.: "não é um sistema de força de vendas completo"; "não cancela pedidos — o cancelamento é feito no ERP"). Uma expectativa desfeita no kick-off custa uma conversa; desfeita depois da entrega, custa o cliente.

### 2.1 Matriz CSD (Certezas, Suposições, Dúvidas)
Em 15 minutos, com o time e, se possível, com o cliente:
| Certezas (com evidência) | Suposições (acreditamos, sem prova) | Dúvidas (não sabemos) |
|---|---|---|
| | | |
Cada **suposição** vira algo a validar, com dono e prazo; cada **dúvida** vira pergunta no roteiro da seção 4. Volte à matriz a cada marco: suposições confirmadas passam para certezas. Exemplo de suposição perigosa: "o cliente entende que o produto cria e grava pedidos, e não que é um força de vendas completo".

## 3. Mapa de stakeholders (Poder × Interesse)
| | Interesse alto | Interesse baixo |
|---|---|---|
| **Poder alto** | Gerenciar de perto (decisores, donos, sócios) | Manter satisfeito (diretoria, quem pode escalar) |
| **Poder baixo** | Manter informado (usuários-chave, vendedores) | Monitorar |
Em B2B, quem usa raramente é quem decide. Mapeie também **quem pode escalar** (sócios, donos) e trate esse grupo antes que ele apareça num momento crítico. Revise o mapa quando entrar gente nova no grupo do projeto.

## 4. Levantamento de requisitos
**Roteiro de conversa (baseado no passado, não em hipóteses):**
- "Me conta a última vez que vocês precisaram fazer [processo]. O que fizeram, passo a passo?"
- "Quanto tempo levou? O que deu errado?"
- "Como resolvem hoje?" (é a referência que o produto precisa superar)
- "O que isso custa quando dá errado?"
- Evite "vocês usariam…?" e "seria bom ter…?" — as respostas são cortesia, não evidência.

**Ao analisar as respostas, marque cada afirmação:**
- **[FEZ]** comportamento concreto já ocorrido → evidência.
- **[DISSE]** opinião ou pedido → hipótese.
- **[FARIA]** projeção sobre o futuro → no máximo uma pista.
Só [FEZ] sustenta uma decisão sozinho.

**Fluxo atual × fluxo futuro:** desenhe como o processo funciona **hoje** e como vai funcionar **com o produto**, passo a passo, incluindo os **bastidores** que o cliente não vê: rotinas e parâmetros do ERP, integrações, carga de dados, suporte. As diferenças entre os dois fluxos são o escopo real; os bastidores são onde moram os riscos técnicos. Um diagrama simples (caixas e setas, em Mermaid) basta — a skill desenha, o PO valida.

**Regras de negócio por escrito:** peça ao cliente as regras (ex.: quem pode editar o quê, em qual situação) por escrito e registre na Wiki antes de desenvolver.

## 5. Mapa da jornada (planejar o que entra no go-live)
Antes de fatiar em histórias, monte o mapa:
1. **Linha de cima:** as etapas da jornada de quem usa, da esquerda para a direita (ex.: entrar → montar o pedido → enviar → acompanhar → corrigir).
2. **Embaixo de cada etapa:** o que o produto precisa ter para ela, do mais essencial ao menos.
3. **Corte horizontal:** a primeira faixa (o mínimo de cada etapa) é o go-live; as faixas seguintes são as próximas entregas.
O mapa mostra lacunas (etapa sem nada) e evita entregar uma etapa completa enquanto outra nem existe. Depois, cada item vai para a **po-historias-de-usuario**.

## 6. Aceite
Combine no kick-off **como cada entrega será aceita** (documento assinado, e-mail, mensagem formal) e registre sempre a **forma do aceite** no status report. Aceite só em chamada ou em grupo de mensagens é frágil — recomende formalizar.

## 7. Questionário antes do kick-off
Envie `templates/questionario-implantacao.md` ao cliente antes da primeira reunião. As respostas alimentam a Matriz CSD (seção 2.1) e o roteiro da seção 4; o kick-off passa a ser para esclarecer, não para coletar.

## 8. Montar o projeto no board espelhando o fluxo do cliente ou parceiro
Quando o cliente ou parceiro já trabalha em outra ferramenta (Trello, planilha, outro board), o projeto pode **espelhar o fluxo dele** em vez de impor o padrão Épico → Feature → História:
- **Backlog plano de PBIs como catálogo de cenários:** um item por cenário testável, com padrão de título fixo (ex.: `ID: NN - GRUPO: <grupo> - <cenário>`). O parceiro reconhece o que já usa e cada card tem um "pronto" claro.
- **Estados que dizem com quem está a bola:** ex.: A fazer → Em progresso - <nossa empresa> / Em progresso - <parceiro> → Teste correções/ajustes → Teste OK. Na daily, a coluna mostra quem deve a próxima ação.
- **Board como visão do dia a dia; Wiki como fonte da verdade** (módulo 10): andamento se discute no board, regra se discute na Wiki.
- **Cuidados:** cada item cita os códigos RF/RN que cobre (módulo 10, seção 9); o estado do PBI acompanha o das tasks; itens parados entram na métrica de fluxo do status report (módulo 07).
- **Quando não usar:** se o projeto for de implantação com fases e marcos de aceite, prefira o Modo Cliente — Implantação da po-historias-de-usuario; para entrega com data ou janela fixa (evento, campanha), o Modo Projeto Pontual / Evento.
Criar processo, estados ou projeto no board é decisão do PO e da administração do board: a skill propõe, o PO executa ou autoriza.

## 9. Saída
- Página de planejamento na Wiki (`templates/planejamento-implantacao.md`), com É / Não é, Matriz CSD, fluxo atual × futuro e mapa da jornada.
- Requisitos levantados → Perguntas e regras para a **po-historias-de-usuario**.
- Riscos de expectativa → status report (módulo 07) e, se graves, decisão (módulo 06).
- Produto novo ou add-on → estrutura de documentação do módulo 10.
