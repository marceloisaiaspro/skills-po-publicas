# Skills de Product Owner para o Claude

Duas skills que transformam o Claude num parceiro de trabalho de Product Owner: uma para o trabalho de co-PO (triagem, priorização, decisão, status report, documentação) e outra para escrever e refinar histórias de usuário, tasks e bugs.

Elas nasceram do uso real no dia a dia de um PO de produtos B2B integrados a ERP e foram generalizadas para servir a qualquer time.

| Skill | Para quê | Versão |
|--|--|--|
| [`po-historias-de-usuario`](po-historias-de-usuario/SKILL.md) | Escrever, fatiar e revisar Histórias de Usuário, Tasks autossuficientes, Bugs, Spikes e Débitos Técnicos, com 3 Cs, INVEST, critérios em sentenças simples e validação em Gherkin | 1.0.0 |
| [`po-copiloto`](po-copiloto/SKILL.md) | Co-PO e co-PM: triagem de demandas, consolidação de pedidos de clientes, priorização com premissas, decisão e "não" com argumento, descoberta, status report, roadmap e documentação de produto | 1.0.0 |

## O que tem de diferente
- **Nunca supõe regra de negócio:** o que falta vira pergunta em aberto, com dono.
- **Exemplos bons e ruins:** cada skill calibra o resultado com exemplos reais (anonimizados) do que funciona e do que não funciona.
- **Simples primeiro:** cartão curto, poucos critérios testáveis e tasks que o dev entende sem abrir a história.
- **Funciona com qualquer board:** Azure DevOps, Jira ou outro. Com uma integração (MCP), o Claude pode registrar os itens direto no board, sempre com a sua confirmação.

## Como usar
1. Baixe o arquivo da skill na pasta [`dist/`](dist/) (`po-copiloto.zip` e/ou `po-historias-de-usuario.zip`).
2. No Claude, envie o .zip na área de Skills das configurações (consulte a ajuda oficial do Claude se não encontrar a opção).
3. Adapte ao seu contexto preenchendo uma vez:
   - `po-historias-de-usuario/referencias/glossario-modelo.md` — produtos, personas, termos, tags e regras do seu board;
   - `po-copiloto/contexto/empresa-modelo.md` — empresa, produtos, pessoas e padrões de Wiki.
4. Peça normalmente, por exemplo: *"escreva a história para o vendedor ver a carteira de clientes inativos"* ou *"isso é bug ou melhoria?"*.

As duas funcionam juntas: a `po-copiloto` tria e decide; a `po-historias-de-usuario` escreve os itens.

## Créditos
- **Prof. Marcelo Neves** — ensinamentos sobre escrita de histórias de usuário e uso de exemplos bons e ruins, base do método.
- Referências públicas: 3 Cs (Ron Jeffries), INVEST (Bill Wake), User Stories Applied (Mike Cohn), BDD/Gherkin (Dan North), Scrum Guide 2020, entre outras listadas em `referencias/fontes.md` de cada skill.

## Autor
**Marcelo Isaías** — Product Owner B2B · [linkedin.com/in/marceloisaias](https://www.linkedin.com/in/marceloisaias)

Sugestões e melhorias são bem-vindas: abra uma *issue* neste repositório.

## Licença
[CC BY 4.0](LICENSE) — use, adapte e compartilhe, inclusive comercialmente, dando o crédito ao autor.
