# Exemplo — documentação de produto com parceiro

*(Caso fictício, construído a partir de padrões comuns. Produto de exemplo: "Módulo de Crédito", um add-on de ERP construído com a parceira "Nexo Fintech".)*

## Contexto
A parceira trabalhava em Trello. O PO criou no board um processo próprio, com o backlog **espelhando o Trello** como lista plana de itens, e passou a conduzir o dia a dia pelo board. A documentação da Wiki virou referência para os dois lados.

## 1. O que funcionou (vira padrão)
| Prática | Por que funcionou | Módulo |
|--|--|--|
| Backlog plano, um item por cenário, título `ID: NN - GRUPO: <grupo> - <cenário>` | A parceira reconheceu o próprio Trello; cada card é um cenário testável | 05 §8 |
| Estados que dizem **com quem está a bola** (Em progresso - nós / Em progresso - parceira → Teste ajustes → Teste OK) | Na daily, a coluna mostra quem deve a próxima ação | 05 §8 |
| Board para o andamento; Wiki como fonte da verdade | Andamento se discute no board; regra, na Wiki | 10 |
| Especificação com RF, RN consolidadas, RNF, telas, glossário, FAQ e manual | Respostas iguais para todo mundo | 10 §1–2 |
| Questionário de implantação enviado antes do kick-off | Levanta o necessário antes da reunião | templates/questionario-implantacao.md |
| Memória técnica (autoria, linha do tempo, fluxo) | Registra o porquê para quem chegar depois | templates/memoria-tecnica.md |

## 2. O que a auditoria encontrou (vira checklist)
| # | Achado | Lição | Regra |
|--|--|--|--|
| 1 | Páginas citando um código de RN cujo conteúdo na tabela era outro | Citar `código + nome curto`; auditar depois de renumerar | 10 §5 |
| 2 | Regra descrita em páginas, mas fora da tabela consolidada | Regra nova sobe para a tabela primeiro | 10 §4 |
| 3 | Duas RNs com o mesmo conteúdo | Manter uma; a outra vira "Revogada — ver RNxx" | 10 §4 |
| 4 | Numeração de RNF diferente entre páginas | Uma numeração por prefixo no produto inteiro | 10 §3 |
| 5 | Contradições técnicas entre páginas | Não resolver sozinho: perguntar ao tech lead com as duas citações | 10 §6 |
| 6 | Página-índice vazia | Seção vazia recebe "Em construção — responsável, previsão" | 10 §2 |
| 7 | Itens do board sem ligação com RF/RN | Cada item cita os códigos que cobre | 10 §9 |

## 3. Como corrigir bem
- Mostrar cada divergência como **"texto citado" / "texto da fonte"**, para o PO decidir sem abrir a Wiki.
- Antes de criar uma regra nova, conferir se a ideia já existe em outro código — senão nasce uma terceira cópia.
- Cada item do board com `Cobre: RFxx / RNxx`, para responder "o que falta para a regra X estar testada?" direto do board.
