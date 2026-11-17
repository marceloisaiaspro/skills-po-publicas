# Exemplos bons

*(Casos fictícios, construídos a partir de padrões reais de trabalho. Empresa de exemplo: "Aurora Distribuidora", que usa um portal de pedidos para vendedores externos integrado ao ERP.)*

---

# EXEMPLO 1 — História

## [H-01] Acompanhar clientes da carteira próximos de ficarem inativos
- **Tipo:** História · **Épico:** Carteira de Clientes · **Feature:** Evolução do Produto
- **Produto / Tela:** Portal de Pedidos — Visão Geral
- **Tags:** Portal de Pedidos; Carteira; Evolução do Produto

### Cartão da História
**Eu como** vendedor externo
**quero** acompanhar quais clientes da minha carteira estão próximos de ficarem inativos
**para** agir sobre os clientes em risco antes que deixem de comprar

### Descrição e Contexto de Negócio
A Visão Geral já mostra o total da carteira. Falta oficializar as faixas de inatividade, limitar a lista inicial para não pesar a tela e criar um atalho para a carteira completa.
- **Blocos de entrega:** Carteira - 1: card com gráfico, faixas, lista limitada e atalho.
- **Fora do escopo:** a tela completa da carteira (história própria).

### Critérios de Aceite (Sentenças Simples)
1. A Visão Geral exibe o card "Carteira de clientes" com gráfico de rosca e total ao centro.
2. Clientes com até 60 dias sem comprar são classificados como *Ativos*.
3. Clientes com 61 a 90 dias sem comprar são classificados como *Próximos de Inativos*.
4. Clientes com 91 dias ou mais sem comprar, ou sem compras, são classificados como *Inativos*.
5. O vendedor visualiza somente os clientes da sua carteira, identificado pela sessão.
6. O supervisor visualiza o consolidado da carteira da sua equipe.
7. A lista exibe até 10 clientes, do maior para o menor número de dias sem comprar.
8. O link "Ver carteira completa" abre a tela da carteira.
9. O card carrega em até 2 segundos.

### Dependências e Riscos
- **Risco:** lentidão em bases grandes → ação: lista limitada (critério 7) e pergunta sobre cache.

### Perguntas em Aberto
- **[Para o Time Técnico]:** Os totais serão calculados a cada acesso ou com cache?

> **Por que é boa:** uma persona no cartão (o supervisor foi para o critério 6); cada faixa é um critério; "91 dias ou mais" não deixa nenhum dia sem classificação; o tempo de resposta está nos critérios, não no cartão.

---

# EXEMPLO 2 — História simples, uma Task por pessoa

*(Time pequeno: um dev fullstack e um dev de banco. O PO pediu simplicidade.)*

## [H-02] Exibir preço especial como preço normal para um cliente
- **Tipo:** História · **Épico:** Mercado Sul - Sustentação / Atendimento · **Feature:** Melhorias / Solicitações
- **Origem:** Mercado Sul — pedido no grupo do projeto — 16/11 *(tag `Origem Mercado Sul`)*

### Cartão da História
**Eu como** vendedor do Mercado Sul
**quero** ver o preço especial vigente como o preço normal do produto
**para** reduzir dúvidas do cliente sobre promoções que não existem

### Descrição e Contexto de Negócio
O Mercado Sul usa a tabela de preços especiais para precificar, não para promoção. O preço continua o mesmo; só a apresentação de promoção sai, e só para este cliente.

### Critérios de Aceite
1. O preço exibido é o preço especial vigente; sem preço especial vigente, vale o preço da tabela padrão.
2. A tag de promoção não aparece na listagem de produtos.
3. A tag de promoção não aparece nos detalhes do produto.
4. Preço antigo, preço novo e data de vigência não são exibidos.
5. O atalho e as seções de promoção ficam ocultos.
6. Os demais clientes continuam como hoje.

**Tasks:** `Preço Especial - 1: Ocultar promoção - banco` (dev de banco) · `Preço Especial - 1: Ocultar promoção - fullstack` (dev fullstack). Cada card traz o contexto e os 6 critérios; a seção "ESTA TASK" diz o que cabe a cada um.

> **Por que é boa:** cartão curto, critérios que qualquer um testa, uma Task por pessoa porque é assim que o time trabalha, e a regra "só para este cliente" está explícita (critério 6).

---

# EXEMPLO 3 — Task de camada autossuficiente

```html
<h3>Pedidos Recusados - 2: Corrigir e reenviar o pedido - front</h3>
<p><b>CONTEXTO (USER STORY)</b><br>Eu como vendedor externo, quero corrigir um pedido recusado sem redigitá-lo, para reduzir o retrabalho de montar o pedido outra vez.</p>
<p><b>REGRAS DE NEGÓCIO / INTEGRAÇÕES</b><br>O pedido recusado pelo ERP pode ser editado e reenviado mantendo o mesmo número no portal. O vendedor edita somente pedidos da sua carteira (identificador da sessão).</p>
<p><b>CRITÉRIOS DE ACEITE</b></p>
<ol>
  <li>O botão "Editar" fica disponível para pedidos recusados.</li>
  <li>Forma de pagamento, observações e itens podem ser editados.</li>
  <li>Cliente, filial e vendedor ficam bloqueados para edição.</li>
  <li>Ao alterar a forma de pagamento, os preços são recalculados.</li>
  <li>Ao salvar, o pedido não é reenviado ao ERP e volta a exibir o botão "Gerar pedido".</li>
  <li>O status exibido após salvar segue a definição pendente (a definir — ver Perguntas em Aberto).</li>
</ol>
<p><b>ORDEM ENTRE CAMADAS</b><br>1º Banco e Back → 2º Front. O front monta a tela em paralelo e testa após o back.</p>
<p><b>O QUE PRECISA SER FEITO — ESTE CARD: FRONT-END</b></p>
<ul>
  <li>Habilitar "Editar" para pedidos recusados.</li>
  <li>Bloquear cliente, filial e vendedor; liberar os campos do critério 2.</li>
  <li>Exibir aviso de recálculo de preços ao iniciar a edição.</li>
</ul>
<p><b>VISÃO DO BLOCO — DEMAIS CAMADAS</b></p>
<ul>
  <li><b>[BACK/BANCO]</b> Manter o número do pedido, atualizar o cabeçalho e substituir os itens em transação.</li>
</ul>
<p><b>VALIDAÇÃO (QA)</b><br>Massa: um pedido recusado do vendedor de teste e um pedido recusado de outro vendedor.</p>
<pre><code>Funcionalidade: Corrigir e reenviar pedido recusado

  Cenário: Corrigir a forma de pagamento e salvar
    Dado que o vendedor tem um pedido recusado
    Quando altera a forma de pagamento e salva
    Então os preços são recalculados
    E o botão "Gerar pedido" é exibido

  Cenário: Pedido de outro vendedor
    Dado que existe um pedido recusado de outro vendedor
    Quando o vendedor consulta seus pedidos recusados
    Então o pedido do outro vendedor não é exibido
</code></pre>
<p><b>EVIDÊNCIAS ESPERADAS</b><br>Print da tela de edição; print do pedido salvo com "Gerar pedido".</p>
<p><b>HOMOLOGAÇÃO DO PO</b><br>No ambiente do cliente, corrigir um pedido recusado de teste e confirmar que ele chega ao ERP sem redigitação.</p>
<p><b>FORA DO ESCOPO</b><br>Exibição do motivo da recusa (bloco 1).</p>
```

> **Por que é boa:** o dev entende tudo sem abrir a História; a contradição sobre o status virou pergunta em vez de suposição; a validação pode ser seguida por qualquer revisor.

---

# EXEMPLO 4 — Bug

- **Tipo:** Bug · **Épico:** Aurora - Sustentação / Atendimento · **Feature:** Sustentação
- **Severidade:** 3 - Média — divergência de valor entre o portal e o ERP
- **Ambiente:** Produção · **Camadas:** card único até achar a causa

```html
<h3>Valor do pedido no ERP diverge do valor no portal</h3>
<p><b>DESCRIÇÃO DO DEFEITO</b><br>Quando o vendedor grava um pedido com itens com desconto, então o valor total no ERP diverge do valor do carrinho, quando deveria ser o mesmo em todas as etapas.</p>
<p><b>PASSOS PARA REPRODUÇÃO</b></p>
<ol>
  <li>Acessar o portal em Produção com o perfil de vendedor.</li>
  <li>Montar um pedido com itens com desconto e anotar o total.</li>
  <li>Gerar o pedido e consultar o mesmo pedido no ERP.</li>
  <li>Comparar os valores.</li>
</ol>
<p><b>VALIDAÇÃO (QA)</b></p>
<pre><code>Cenário: Mesmo valor em todas as etapas
  Dado um pedido com itens com e sem desconto
  Quando o vendedor gera o pedido
  Então o total no ERP é igual ao total do carrinho
</code></pre>
<p><b>HOMOLOGAÇÃO DO PO</b><br>Gravar um pedido com e sem desconto e conferir o mesmo valor no carrinho, no PDF e no ERP.</p>
```

> **Por que é bom:** a frase "Quando… então… quando deveria…" mostra a regra quebrada; passos numerados; severidade justificada.

---

# EXEMPLO 5 — Modo Projeto Pontual / Evento

**Épico:** Reativação do App de Captura de Pedidos - Feira de Novembro Aurora
**Features (fases):** `1: Infraestrutura e Integrações (Fornecedor)` · `2: App e Painel (Fornecedor)` · `3: Acessos e Ambiente (Mista)` · `4: Homologação (Aurora)` · `5: Validação em Produção (Mista)` · `6: Operação da Feira (Mista)` · `7: Encerramento (Mista)`

```html
<h3>14 [Aurora]: Enviar pedido de cliente bloqueado em produção e cancelar após conferência. (Meta: 10/11)</h3>
<p><b>CONTEXTO</b><br>Antes da feira, a Aurora confirma em produção que o pedido capturado chega ao ERP, sem gerar venda real.</p>
<p><b>CRITÉRIOS DE CONCLUSÃO</b></p>
<ol>
  <li>O pedido de um cliente bloqueado é enviado pelo app em produção.</li>
  <li>O pedido aparece retido no ERP.</li>
  <li>O pedido é cancelado após a conferência.</li>
</ol>
<p><b>EVIDÊNCIAS ESPERADAS</b><br>Mensagem da Aurora no grupo do projeto, com data e hora, confirmando a retenção e o cancelamento.</p>
<p><b>PLANO DE REVERSÃO</b><br>Cancelar o pedido logo após a conferência. Se o cancelamento falhar, o pedido segue retido (cliente bloqueado) e não é faturado.</p>
```

> **Por que é bom:** a Task fica na fase em que é validada; o título mostra responsável e meta; o teste em produção tem plano de reversão.
