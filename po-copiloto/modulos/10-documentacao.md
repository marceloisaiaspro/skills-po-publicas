# Módulo 10 — Documentação de produto

**Objetivo:** escrever e manter a documentação que vira **referência** do produto: o lugar que cliente, time, suporte e parceiro consultam antes de perguntar. Documentação boa responde a mesma pergunta do mesmo jeito para todo mundo; documentação ruim cria duas versões da verdade.

**Papel aplicado:** Documentador (SKILL.md §1). A skill escreve, organiza e audita; o PO valida o conteúdo de negócio e o time técnico valida o conteúdo técnico.

## 1. Tipos de documento e para quem é cada um
| Documento | Público | Pergunta que responde | Quem valida |
|--|--|--|--|
| Visão do produto | Liderança, comercial, parceiro | Para que serve, para quem, o que é e o que não é | PO + liderança |
| Especificação funcional (RF, RN, RNF, UC, fluxos) | Time, QA, parceiro | O que o sistema faz e com quais regras | PO |
| Interface e telas (campo a campo) | Time, suporte, QA | O que aparece em cada tela e de onde vem cada campo | PO + dev |
| Personas | Time, comercial | Quem usa e o que precisa | PO |
| Especificação técnica / API | Devs, integradores | Como funciona por dentro: arquitetura, banco, endpoints | Tech lead |
| Configuração e manual de uso | Cliente, suporte, implantação | Como configurar e como usar, passo a passo | PO + suporte |
| Glossário e FAQ | Todos | O que significa cada termo; dúvidas que se repetem | PO |
| Questionário para implantação | Cliente (antes do kick-off) | O que precisamos saber do cliente para implantar | PO + implantação |
| Memória técnica / gênese | Time futuro, liderança | Por que o produto é assim: autoria, linha do tempo, decisões | PO + tech lead |

**Regra:** cada documento tem um público principal. Se uma página tenta servir a todos, ela não serve bem a ninguém — divida.

## 2. Estrutura padrão (11 seções)
Para produto novo ou add-on, use esta ordem na Wiki (template em `templates/documentacao-produto.md`):
1. Visão do Produto
2. Especificação Funcional (RF e fluxos)
3. Regras de Negócio (tabela consolidada)
4. Casos de Uso
5. Interface e Telas
6. Personas
7. Especificação Técnica
8. API / Integrações
9. Configuração e Manual de Uso
10. Glossário
11. FAQ
Mais duas páginas de apoio quando houver implantação ou histórico relevante: **Questionário para Implantação** (`templates/questionario-implantacao.md`) e **Memória Técnica** (`templates/memoria-tecnica.md`).
Seção sem conteúdo ainda **não fica vazia**: recebe uma linha "Em construção — responsável: <cargo>, previsão: <data>". Página-índice lista e linka as filhas.

## 3. Códigos e numeração
| Prefixo | O que é | Exemplo |
|--|--|--|
| RF | Requisito funcional — o que o sistema faz | RF03 — Enviar pedido ao fornecedor |
| RN | Regra de negócio — condição, limite, cálculo | RN07 — Intervalo mínimo entre concessões |
| RNF | Requisito não funcional — desempenho, segurança, disponibilidade | RNF02 — Tempo de resposta |
| UC | Caso de uso — o passo a passo de um ator | UC01 — Configurar fornecedor |
| MF | Macrofluxo — visão ponta a ponta (opcional) | MF02 — Do pedido ao retorno |
- Numere com dois dígitos e **nunca reaproveite** um código: regra extinta fica na tabela como "Revogada em <data>", para as referências antigas continuarem fazendo sentido.
- **Uma única numeração por prefixo no produto inteiro.** Se duas páginas numeram RNF por conta própria, os códigos colidem.

## 4. Tabela consolidada = fonte da verdade
- Toda RN mora **uma vez** na tabela consolidada (seção 3): código, regra, exemplo, origem (quem definiu e quando), status.
- As demais páginas (telas, casos de uso, manual, FAQ) **citam o código** e, se precisarem, resumem em meia linha — não reescrevem a regra.
- Regra descoberta em outra página (num fluxo, numa tela, no FAQ) **sobe para a tabela** antes de qualquer outra coisa.
- Duas linhas com o mesmo conteúdo = duplicidade: mantenha uma e transforme a outra em "Revogada — ver RNxx".

## 5. Referências cruzadas
- Ao citar um código, confira se o texto ao lado bate com o que a tabela diz desse código. O erro mais comum é a numeração mudar e as citações ficarem apontando para a regra errada.
- Depois de renumerar, inserir ou revogar regras, faça a **auditoria de documentação** (módulo 08, seção 2) antes de publicar.
- Cite sempre `código + nome curto` (ex.: "RN07 — intervalo entre concessões"), nunca só o número: o nome denuncia a citação trocada.
- Ao relatar uma divergência, mostre os dois textos lado a lado: **"texto citado" / "texto da fonte"** (formato da auditoria, módulo 08).
- Antes de comparar, confira o **tipo** de cada código (RF × RN × RNF, seção 3). Duas frases iguais em tipos diferentes (ex.: uma RN que repete um RF) não são erro de citação, e sim de classificação: a correção é apontar para o código existente ("ver RN06 e RF07.1"), não criar outra cópia.

## 6. Fato × "a confirmar"
- Só entra como fato o que veio do PO, do cliente por escrito, do código lido pelo time ou de teste realizado. O resto leva **"(a confirmar — <com quem>)"**.
- **Contradições técnicas** (ex.: uma página diz "somente leitura" e outra descreve gravações; dois bancos ou dois frameworks diferentes citados) não são resolvidas pela skill: viram pergunta ao tech lead, com as duas citações lado a lado.
- Especificação técnica sem validação do time técnico recebe no topo: "Versão não validada pelo time técnico".

## 7. Cabeçalho e versão de cada página
Toda página de referência começa com:
```
Autor: <cargo/nome> · Validado por: <cargo/nome> · Versão: <x.y> · Atualizado em: <DD/MM/AAAA>
Fonte da verdade para: <o que esta página define> · Ver também: <links>
```
Mudança de regra = nova versão + linha no histórico da página (data, o que mudou, quem pediu).

## 8. Acessos e dados sensíveis
- **Decisão do time:** se o time decidiu guardar acessos (logins e senhas de ambientes) na Wiki para que todos possam usá-los, a skill **respeita a decisão**: não remove esses dados nem recomenda removê-los.
- Ao editar uma página que contém acessos, reproduza-os **exatamente** e confira depois da gravação que não mudou nenhum caractere.
- Antes de uma página ir em cópia para terceiros (cliente, parceiro), avise o PO se ela contém acessos, para ele decidir se vão junto.
- Dados de cartão e endereço de pessoas não entram na Wiki.

## 9. Ligação entre backlog e documentação
- Cada item do board cita os códigos que cobre, na descrição, no formato `Cobre: RF03 / RN07, RN08` — o mesmo da po-historias-de-usuario.
- Cada RF da especificação lista os itens do board que o cobrem ("Coberto por: #1234, #1240"), ou "Sem item no board".
- Com isso o PO responde, sem abrir card por card: "o que falta para a RN07 estar testada?" e "este cenário cobre qual regra?".
- Mudou a regra → os itens ligados a ela são revistos (podem precisar de reteste).

## 10. Rotina de manutenção
| Quando | O que fazer |
|--|--|
| Regra nova ou alterada | Atualizar a tabela consolidada → as citações → os itens do board ligados |
| Antes de entregar a documentação ao cliente ou parceiro | Auditoria de documentação (módulo 08) |
| Fim de cada fase ou marco | Revisar placeholders, FAQ (dúvidas novas) e Memória Técnica |
| Pergunta repetida no suporte ou no grupo do cliente | Vira item do FAQ |

## 11. Saída
- Páginas na Wiki, na estrutura da seção 2, com cabeçalho da seção 7.
- Lista de **perguntas em aberto** (contradições, "a confirmar") com dono.
- Quando for revisão: relatório no formato do módulo 08 com o checklist de auditoria de documentação.
- Calibração: `exemplos/documentacao-parceiro.md`.
