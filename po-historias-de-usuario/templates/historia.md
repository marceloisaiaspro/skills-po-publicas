# Templates

## Roteiro padrão de implantação (Modo Cliente — qualquer produto)
*(Nomes atuais das Features; podem mudar conforme o PO informar. As histórias são as etapas-chave e se adaptam ao projeto.)*

| Feature | Histórias (etapas-chave) |
|---|---|
| **01: Planejamento / Pré-Projeto** | 1.1 Start com o cliente · 1.2 Levantamento de requisitos (confirmar o contratado, rotinas e parametrizações) · 1.3 Acessos e ambiente do cliente |
| **02: Desenvolvimento / Parametrização** (uma ou mais) | Execução conforme o produto — ex.: subir o ambiente, criar e integrar o banco, configurar integrações; ou montar o fluxo aprovado no planejamento · **Última história: homologação interna** |
| **03: Implementação e Go-Live** | 3.1 **Homologação com o cliente** (teste no cenário dele) · Go-Live · Treinamento / Hand-over · Encerramento formal (e-mail e documento de entrega) |

---

## Roteiro padrão do Modo Projeto Pontual / Evento
*(Features = fases, no formato `N: <Fase> (<Dono>)`, com uma US de mesmo título. Adaptar as fases ao projeto; cada Feature fecha pelo seu critério de saída. Regras na seção 2 do SKILL.md.)*

| Feature (fase) | Tasks típicas | Critério de saída |
|---|---|---|
| **1: Infraestrutura e Integrações (Fornecedor)** | Subir os serviços; validar a integração em homologação | Serviços no ar e integração validada em homologação |
| **2: App / Produto (Fornecedor)** | Gerar a versão final; teste ponta a ponta interno | Versão final gerada e testada |
| **3: Acessos e Ambiente (Mista)** | Enviar a lista de acessos (cliente); cadastrar e testar o login (fornecedor) | Acessos cadastrados e login testado |
| **4: Homologação (Cliente)** | Testar no ambiente de homologação; registrar o aceite e a forma do aceite | Aceite do cliente registrado |
| **5: Validação em Produção (Mista)** | Teste em produção com PLANO DE REVERSÃO; carga dos dados finais; validar os equipamentos do evento | Teste confirmado e revertido, dados carregados, equipamentos validados |
| **6: Operação (Mista)** | Prontidão: créditos de serviços de terceiros, limpeza de dados de evento anterior, monitoramento | Janela encerrada sem interrupção |
| **7: Encerramento e Pós-Evento (Mista)** | Números da operação; aceite formal; decisão sobre o ambiente após a janela | Encerramento registrado |

**Tasks deste modo:** título `N [Fornecedor | <Cliente>]: <ação>. (Meta: DD/MM)`, numeração única no Épico; a Meta é a mesma data do campo Data estimada. Corpo: Modelo B para desenvolvimento; Modelo A para as demais (Task do cliente = Task PO, atribuída ao PO).

---

## Template 1: História de Usuário (User Story)

## [H-XX] <Título curto: Verbo no Infinitivo + Complemento>
- **Tipo:** História
- **Épico:** <conforme a hierarquia da seção 2 do SKILL.md>
- **Feature:** <conforme a hierarquia da seção 2 do SKILL.md>
- **Produto / Tela:** <produto, conforme o glossário do time> — <Tela ou Módulo>
- **Origem:** <cliente/solicitante> — <solicitação nº, ata, chamado ou e-mail> — <data> *(tag `Origem <Cliente>`)*
- **Tags:** <produto; tema; `PRIORIDADE` se urgente (com Priority = 1); `Em Análise` se ainda não pronta>
- **Cobre:** <RFxx / RNxx — somente quando o produto tiver especificação; nunca criar código>

### Cartão da História
**Eu como** <persona real — nunca "usuário">
**quero** <ação única, sem "e/ou", sem advérbio vago, sem tela ou sistema>
**para** <benefício real único>

### Descrição e Contexto de Negócio
<Problema, telas envolvidas e regras do produto. Integrações e sistemas legados somente com o que foi informado; o resto "(a confirmar)".>
- **Blocos de entrega:** <cada bloco vira um conjunto de Tasks por camada>
- **Fora do escopo desta versão:** <o que não será entregue agora>
- **Implantação / Pré-requisitos (se aplicável):** <parâmetros ou configurações por cliente>

### Métrica de Sucesso (opcional)
- **Indicador:** <o que será medido> · **Situação atual:** <valor ou "a medir"> · **Meta:** <valor ou "a definir">

### Critérios de Aceite (Sentenças Simples)
1. <Comportamento principal e tela>
2. <Isolamento de visibilidade/permissão do produto>
3. <Exibição, ordenação e filtros>
4. <Regras de negócio, integração e tempo de resposta>
5. <Estado vazio, exceções e falha de comunicação>
*(Uma regra por sentença, no presente. Valor pendente: "a definir — ver Perguntas em Aberto".)*

### Dependências e Riscos
- <Dependência ou risco, com a ação: Pergunta, Spike ou Task Técnica — ou "Nenhum">

### Perguntas em Aberto
- **[Para o PO / Cliente]:** <dúvida de regra ou escopo>
- **[Para o Time Técnico]:** <dúvida técnica, incluindo itens "(a confirmar)">

---

## Modelo B: Task de desenvolvimento por camada (autossuficiente)
*(Gere um card por camada envolvida no bloco: `- front`, `- back`, `- banco`. O conteúdo é o mesmo; muda o título, a tag e a camada destacada. No Modo Projeto Pontual / Evento, o título segue a seção 2 do SKILL.md. Blocos COBRE e PLANO DE REVERSÃO somente quando se aplicarem.)*

```html
<h3>[Funcionalidade] - [nº do bloco]: [Descrição] - [front | back | banco]</h3>
<p><b>CONTEXTO (USER STORY)</b><br>Eu como [persona], quero [ação], para [benefício].</p>
<p><b>COBRE</b><br>[RFxx / RNxx — somente quando houver especificação.]</p>
<p><b>REGRAS DE NEGÓCIO / INTEGRAÇÕES</b><br>[Regras do bloco, visibilidade/permissão e telas. ERP, sistemas legados ou APIs somente com o que foi informado.]</p>
<p><b>CRITÉRIOS DE ACEITE</b></p>
<ol>
  <li>[Cópia fiel do critério da História]</li>
  <li>[Cópia fiel do critério da História]</li>
</ol>
<p><b>ORDEM ENTRE CAMADAS</b><br>[Ex.: 1º Banco → 2º Back → 3º Front. O front monta a tela em paralelo e testa após o back.]</p>
<p><b>O QUE PRECISA SER FEITO — ESTE CARD: [FRONT-END | BACK-END | BANCO DE DADOS]</b></p>
<ul>
  <li>[Ações da camada deste card]</li>
</ul>
<p><b>VISÃO DO BLOCO — DEMAIS CAMADAS</b></p>
<p><b>[CAMADA]</b> (se aplicável)</p>
<ul>
  <li>[Ações das outras camadas do bloco, para contexto e para dev fullstack]</li>
</ul>
<p><b>VALIDAÇÃO (QA)</b><br>[Roteiro para o Code Review e o QA, executável pelo dev, por outro dev, pelo tech lead ou pelo PO. Massa de teste concreta em texto corrido.]</p>
<pre><code>Funcionalidade: [Nome]

  Contexto:
    Dado que [pré-condição comum]

  Cenário: [Caminho feliz]
    Quando [ação da persona]
    Então [resultado esperado]

  Cenário: [Exceção ou permissão]
    Dado que [condição]
    Quando [ação]
    Então [resultado esperado]
</code></pre>
<p><b>EVIDÊNCIAS ESPERADAS</b><br>[O que anexar no campo Evidências. Ex.: print da tela após a ação; resultado da consulta no banco.]</p>
<p><b>HOMOLOGAÇÃO DO PO</b><br>[O que o PO vai testar na prática, no cenário do cliente, quando o card chegar em QA.]</p>
<p><b>PLANO DE REVERSÃO</b><br>[Somente em teste em produção: como desfazer o teste. Ex.: pedido com cliente bloqueado e cancelamento no ERP.]</p>
<p><b>FORA DO ESCOPO</b><br>[Itens que não fazem parte deste bloco.]</p>
```

---

## Modelo A: Task PO, Spike, Débito Técnico ou Técnica isolada (sem Gherkin)
*(Task PO somente nos casos (1), (2) e (3) da seção 4 do SKILL.md. No Modo Projeto Pontual / Evento, o título segue a seção 2 do SKILL.md. Blocos COBRE e PLANO DE REVERSÃO somente quando se aplicarem.)*
```html
<h3>[Funcionalidade] - [PO | Spike | Técnico]: [Descrição]</h3>
<p><b>CONTEXTO</b><br>[Task PO/Técnica: cartão da História pai. Spike: pergunta a responder e História candidata. Débito Técnico: Risco se não fizermos / Prazo limite / Impacto no negócio.]</p>
<p><b>COBRE</b><br>[RFxx / RNxx — somente quando houver especificação.]</p>
<p><b>REGRAS DE NEGÓCIO / INTEGRAÇÕES</b><br>[Regras envolvidas ou escopo da investigação.]</p>
<p><b>CRITÉRIOS DE CONCLUSÃO</b></p>
<ol>
  <li>[Critério em sentença simples]</li>
</ol>
<p><b>O QUE PRECISA SER FEITO: [PO | SPIKE | TÉCNICO]</b></p>
<ul>
  <li>[Ação a executar ou hipótese a investigar]</li>
</ul>
<p><b>VALIDAÇÃO (QA / HOMOLOGAÇÃO)</b><br>[Como será conferida. Spike: prazo máximo e entregável, ex.: decisão registrada na Wiki.]</p>
<p><b>EVIDÊNCIAS ESPERADAS</b><br>[O que anexar no campo Evidências. Ex.: print da parametrização; e-mail ou ata de aceite; entregável do Spike.]</p>
<p><b>PLANO DE REVERSÃO</b><br>[Somente em teste em produção: como desfazer o teste.]</p>
<p><b>FORA DO ESCOPO</b><br>[Se aplicável.]</p>
```

---

## Modelo C: Bug (campo "Repro Steps")
Cabeçalho na conversa (fora do HTML):
- **Tipo:** Bug · **Épico / Feature:** <conforme a hierarquia>
- **Severidade:** <1 - Critical | 2 - High | 3 - Medium | 4 - Low> — <justificativa em 1 frase> *(campo Severity)*
- **Origem:** <cliente/solicitante> — <chamado ou e-mail> — <data>
- **Ambiente:** <Produção | Homologação> — <cliente/base>
- **Camadas:** <um card por camada envolvida, com a mesma descrição; se a camada for desconhecida, um card único até a investigação>

```html
<h3>[Título curto da falha] - [front | back | banco]</h3>
<p><b>DESCRIÇÃO DO DEFEITO</b><br>Quando [persona] faz [ação], então [resultado observado], quando deveria [resultado esperado pela regra existente].</p>
<p><b>SEVERIDADE</b><br>[Severidade e justificativa em 1 frase.]</p>
<p><b>PASSOS PARA REPRODUÇÃO</b></p>
<ol>
  <li>Acessar [Produto] em [Ambiente] com o perfil [Perfil].</li>
  <li>Navegar até [Tela].</li>
  <li>Executar [Ação].</li>
  <li>Observar [Falha].</li>
</ol>
<p><b>EVIDÊNCIAS E CONTEXTO</b><br>[Regra existente quebrada, prints e logs.]</p>
<p><b>ORDEM ENTRE CAMADAS</b><br>[Ex.: 1º Banco → 2º Back → 3º Front, ou "a definir após investigação da causa raiz".]</p>
<p><b>O QUE PRECISA SER FEITO</b></p>
<ul>
  <li><b>[DEV]:</b> Investigar a causa raiz e corrigir para restabelecer o comportamento esperado.</li>
</ul>
<p><b>VALIDAÇÃO (QA)</b><br>Massa de teste: [dados para reproduzir e validar].</p>
<pre><code>Funcionalidade: Correção de [Funcionalidade]

  Contexto:
    Dado que [pré-condição em que o erro ocorria]

  Cenário: [Comportamento esperado]
    Quando [a persona executa a ação que gerava a falha]
    Então [o resultado correto conforme a regra existente]
</code></pre>
<p><b>EVIDÊNCIAS ESPERADAS</b><br>[O que anexar no campo Evidências para comprovar a correção.]</p>
<p><b>HOMOLOGAÇÃO DO PO</b><br>[O que o PO vai testar na prática, no cenário do cliente, para aceitar a correção.]</p>
```
