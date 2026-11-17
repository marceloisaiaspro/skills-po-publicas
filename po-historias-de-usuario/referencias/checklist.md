# Checklist — INVEST, Travas, DoR e DoD

## Antes de escrever
- [ ] Tipo definido (História, Bug, Spike, Débito Técnico, Parametrização). Em caso de dúvida ou "bug" com cara de escopo novo, a triagem (skill po-copiloto) foi acionada.
- [ ] Modo e hierarquia corretos (Implantação numerada; Sustentação e Produto sem numeração; Projeto Pontual numerado por fase, com o Dono no título da Feature e o responsável no título da Task).
- [ ] Em projeto já em andamento, o padrão do board (títulos, áreas, estados) foi seguido.

## INVEST (História)
- [ ] **Independente:** sem dependência que trave o valor (dúvidas técnicas isoladas em Spike; fatias dependentes aglutinadas ou reescritas).
- [ ] **Negociável:** cartão curto, foca no porquê, sem tela, componente ou sistema.
- [ ] **Valorosa:** benefício real para a persona.
- [ ] **Estimável:** o time entende domínio e tecnologia.
- [ ] **Sob Medida:** cabe na Sprint (fatiamento: Fluxo → Papel → Regra/Variação).
- [ ] **Testável:** critérios em sentenças simples e Gherkin na validação QA das Tasks/Bugs.

## Travas
- [ ] Nenhum "usuário" no item (exceto "História de Usuário"); uma persona por cartão.
- [ ] "Para" com um benefício real, sem repetir o "quero".
- [ ] Cartão sem `e`/`ou` unindo ações ou benefícios e sem advérbios vagos.
- [ ] Nenhuma regra, parâmetro, meta ou valor suposto; pendências em Perguntas em Aberto.
- [ ] Rotinas, tabelas, colunas e APIs informadas pelo PO ou marcadas "(a confirmar)".
- [ ] Termos e tags conforme `referencias/glossario-modelo.md`.

## Definition of Ready
- [ ] Origem registrada (linha "Origem:" + tag `Origem <Cliente>` quando houver cliente).
- [ ] Prioridade: prioridade mais alta + tag `PRIORIDADE` se urgente; prioridade padrão nos demais.
- [ ] Critérios no presente, uma regra por sentença, sem "ou" ambíguo.
- [ ] Regra de visibilidade/permissão explícita ou registrada como pergunta.
- [ ] Cada bloco de entrega tem critérios e Tasks por camada.
- [ ] Cada Task de camada é autossuficiente, traz a **Ordem entre camadas** e copia os critérios da História sem criar escopo (também no campo Acceptance Criteria, quando existir).
- [ ] O bloco VALIDAÇÃO (QA) pode ser executado por qualquer revisor (dev, tech lead ou PO) sem precisar perguntar nada.
- [ ] Card de dev e Bug com **Evidências esperadas** e **Homologação do PO**; Task do Modelo A com **Evidências esperadas**; Task PO criada somente nos casos previstos (antes do dev, depende do cliente ou pedido do PO).
- [ ] Bug com severidade (campo e texto), passos, regra quebrada, ordem entre camadas e homologação do PO.
- [ ] Linha `Cobre: RFxx / RNxx` quando o produto tiver especificação; critérios citam a regra pelo código; nenhum código criado.
- [ ] Teste em produção com o bloco **PLANO DE REVERSÃO**.
- [ ] Campos exigidos pelo board conferidos (glossário do time); responsável informado pelo PO.
- [ ] Riscos com ação definida; perguntas registradas.

## Definition of Done (alinhada ao fluxo do board)
- [ ] **Code Review** aprovado (outro dev ou tech lead).
- [ ] **QA** executado com o roteiro do card (dev, tech lead ou PO), incluindo os cenários Gherkin.
- [ ] Teste prático de uso realizado pelo PO no cenário do cliente (perfis e isolamento de permissão).
- [ ] Aprovação para o deploy e publicação em produção.
- [ ] Wiki atualizada quando aplicável → estado de concluído do projeto.
