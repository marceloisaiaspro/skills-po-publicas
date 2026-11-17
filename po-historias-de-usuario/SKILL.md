---
name: "po-historias-de-usuario"
description: "Escreve, fatia, revisa e prepara para o board itens de backlog — Histórias de Usuário, Tasks autossuficientes por camada, Bugs, Spikes e Débitos Técnicos — com 3 Cs, INVEST, fatiamento, critérios de aceite em sentenças simples e validação em Gherkin. Use quando o pedido for escrever, detalhar, fatiar ou revisar histórias, tasks ou bugs, em qualquer produto e em qualquer board (Azure DevOps, Jira ou outro). Para triar, priorizar ou decidir o tipo da demanda, use a skill po-copiloto."
---

# po-historias-de-usuario — Histórias, Tasks e Bugs

**Versão:** 1.0.0 — histórico em `CHANGELOG.md` · Créditos em `referencias/fontes.md`

## 0. Adaptar ao seu time (uma vez)
Preencha `referencias/glossario-modelo.md` com produtos, personas, termos, tags, estados e campos do seu board. Sem ele, a skill usa os padrões desta página e pergunta o que faltar.

## 1. Antes de escrever
- **Tipo da demanda:** se não estiver claro se é História, Bug, Spike, Débito Técnico ou Parametrização — ou se um "bug" pode ser escopo novo —, faça a triagem (skill **po-copiloto**, módulo 01) antes de escrever.
- **Perguntar ou gerar:** se faltar a **persona** ou o **valor de negócio**, pergunte ao PO antes. As demais lacunas viram *Perguntas em Aberto* e o item é entregue.
- **Nunca suponha regra de negócio:** regras, parâmetros, metas e valores não informados vão para *Perguntas em Aberto*. O critério que depender deles cita a pergunta (ex.: *"período padrão a definir — ver Perguntas em Aberto"*).
- **Trava anti-invenção técnica:** tabelas, campos, rotinas de sistemas legados ou ERPs e endpoints ou limites de APIs de terceiros só entram quando informados pelo PO, presentes na demanda, lidos no board ou na documentação, ou listados no glossário do time. O resto recebe **(a confirmar)** e vai para *Perguntas em Aberto* do Time Técnico.

## 2. Hierarquia no board (modos)
Escolha o modo pelo tipo de trabalho. Os nomes são sugestões; se o board já tem padrão, **o padrão do board prevalece** — siga-o e aponte ao PO o que divergir.

| Modo | Quando usar | Épico | Features |
|--|--|--|--|
| **Cliente — Implantação** (numerado) | Implantar o produto num cliente | `<Cliente> - Implantação` | `01: Planejamento` · `02: Desenvolvimento / Parametrização` (termina na homologação interna) · `03: Implantação e Go-Live` (começa na homologação com o cliente) |
| **Cliente — Sustentação** (sem número) | Atendimento contínuo após o go-live | `<Cliente> - Sustentação / Atendimento` | `Sustentação` (erros em produção) · `Melhorias / Solicitações` (pedidos de mudança) |
| **Produto** (sem número) | Evolução que vale para todos os clientes | Iniciativa do produto | `Evolução do Produto` |
| **Projeto Pontual / Evento** (numerado por fase) | Entrega com data ou janela fixa (evento, campanha, reativação) | `<Ação> - <Evento/Cliente>` | Fases no formato `N: <Fase> (<Dono>)`, Dono = `Fornecedor`, `<Cliente>` ou `Mista`; uma História por Feature |

**Detalhes do Modo Projeto Pontual / Evento**
- Fases de referência (adaptar): 1 Infraestrutura e Integrações · 2 Produto · 3 Acessos e Ambiente · 4 Homologação · 5 Validação em Produção · 6 Operação · 7 Encerramento. Cada fase fecha pelo seu **critério de saída** (ver `templates/historia.md`).
- Tasks numeradas em sequência no Épico inteiro, com o responsável no título: `N [Fornecedor | <Cliente>]: <ação>. (Meta: DD/MM)`.
- A entrega do fornecedor fecha na validação em homologação. Todo teste em produção traz o bloco **PLANO DE REVERSÃO**.
- A Task fica na fase em que é validada, não no componente que toca.

**Sustentação sem burocracia:** dúvidas e orientações resolvidas no próprio atendimento não viram item. Só entra no board o que precisa de ação do time, uma História (ou Bug) por demanda. Estimativa e data são definidas por demanda com o time.

## 3. Regras de escrita
1. **3 Cs e elaboração progressiva:** o cartão (`Eu como… quero… para…`) é simples, conciso e negociável. Telas, parâmetros, tabelas e integrações **nunca entram no cartão**: vão para o Contexto, os Critérios e as Tasks.
2. **Travas do cartão:**
   - **Persona real:** nunca "usuário" (exceto no termo "História de Usuário"). Uma persona por cartão; outras visões (ex.: supervisor) entram nos critérios.
   - **"Para" verdadeiro:** um benefício real — de preferência *Redução, Aumento, Melhoria ou Acesso* — sem repetir o `quero`.
   - **Sem ruído:** sem `e`/`ou` unindo ações ou benefícios; sem advérbios vagos (*rapidamente, facilmente, automaticamente, em tempo real*). "Somente" e "apenas" podem. Tempos vão nos critérios.
   - **Sem solução no cartão:** nada de nome de tela, componente visual (popup, modal) ou sistema.
3. **Fatiamento** (quando não cabe na Sprint): 1º por fluxo de trabalho → 2º por papel ou visão → 3º por regra de negócio ou variação. Se uma fatia criar dependência que trave o valor, aplique **Aglutinação** ou reescreva.
4. **Critérios de aceite:** **sentenças simples** na História e nas Tasks — presente do indicativo, uma regra por sentença, testáveis, sem "ou" ambíguo. **Gherkin** só no bloco `VALIDAÇÃO (QA)` das Tasks e dos Bugs, ou quando pedirem roteiro de homologação.
5. **Visibilidade e permissão:** toda História e toda Task de desenvolvimento explicita quem vê o quê (ex.: o vendedor vê só a própria carteira; o supervisor vê a equipe; o identificador vem da sessão, nunca de parâmetro). Visão não definida vira pergunta.
6. **Rastreabilidade com a especificação:** se o produto tem especificação com códigos (RF/RN/RNF), a linha `Cobre: RFxx / RNxx` entra na História e em cada Task, e o critério cita a regra pelo código, sem copiar o texto. Nunca crie um código.
7. **Simples primeiro:** prefira cartão curto, poucos critérios e uma Task por pessoa quando o time trabalha assim. Detalhe só o que o dev precisa para não perguntar.

## 4. Tasks autossuficientes
- **Uma Task por camada** (`- front`, `- back`, `- banco`) **ou uma Task por pessoa** (ex.: `- fullstack`), conforme o time trabalha.
- **Cada card é autossuficiente:** traz o contexto da História, os critérios do bloco e a execução de todas as camadas, com a do card em destaque. O dev trabalha olhando o card.
- **Ordem entre camadas:** diga o que fica pronto primeiro e o que corre em paralelo (ex.: *1º Banco → 2º Back → 3º Front*).
- **Critérios:** cópia fiel (ou subconjunto) dos da História. A Task não cria escopo.
- **Título:** `<Funcionalidade> - <nº do bloco>: <descrição> - <camada>`.
- **Evidências esperadas:** o que anexar para passar no Code Review e no QA.
- **Homologação do PO:** o que o PO vai testar na prática quando o card chegar em QA.
- **Task do PO** (sem código) só quando o trabalho do PO vem antes do dev, depende do cliente (agendar teste, massa de dados, aceite) ou o PO pede.
- **Time sem QA dedicado:** o bloco `VALIDAÇÃO (QA)` precisa ser executável por qualquer revisor (dev, tech lead ou PO), com massa de teste concreta.

## 5. Tipos de item
| Tipo | Card | Marcação sugerida |
|--|--|--|
| História | Template 1 + Tasks (Modelo B) | Tags do produto e `Origem <Cliente>` quando houver |
| Bug | Modelo C (por camada quando envolver mais de uma) | Severidade no campo e no texto |
| Spike | Modelo A com pergunta, prazo máximo e entregável | Tag `Em Análise` |
| Débito Técnico | Modelo A com *risco se não fizermos / prazo limite / impacto* | Tag `Débito Técnico` |
| Parametrização | Task do PO (Modelo A); se surgir código, vira História | Tag `Parametrização` |

**Prioridade:** urgente → prioridade mais alta do board + tag `PRIORIDADE`; demais → prioridade padrão.
**Item bloqueado:** estado de impedimento com o motivo registrado.

## 6. Registro no board (opcional, via integração)
- **Azure DevOps:** Description e Acceptance Criteria em HTML limpo (`<p>`, `<b>`, `<ul>`, `<ol><li>`); Task filha da User Story; Bug em Repro Steps + Severity. **Jira:** mesmo conteúdo em descrição e critérios; subtarefas ligadas à História.
- **Gravar somente após confirmação explícita do PO.** Por padrão, entregue o texto para revisão.
- **Campos exigidos variam por board:** se a ferramenta recusar a gravação, informe ao PO o campo que faltou — nunca preencha por suposição.
- **Responsável:** sempre informado pelo PO.
- **Conexão instável:** grave um item por vez; se falhar, leia o item antes de reenviar e reenvie só o que faltou.

## 7. Fluxos
**Escrever:** tipo, modo e hierarquia → História (`templates/historia.md`) → Tasks → valide com `referencias/checklist.md` → calibre por `exemplos/boa.md` e `exemplos/ruim.md`.
**Revisar:** avalie contra o checklist e mostre cada falha como *"texto atual" / "texto proposto"*, com o porquê; depois reescreva no padrão.

## 8. Resposta
1. No topo: tipo, Épico e Feature.
2. História com critérios, Dependências/Riscos e Perguntas em Aberto (PO/Cliente e Time Técnico).
3. Cards das Tasks (ou do Bug) prontos para colar.
4. Termine com: `"Gerado com a skill po-historias-de-usuario"`
