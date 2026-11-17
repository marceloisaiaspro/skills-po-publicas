# Exemplo — implantação com lacuna de expectativa

*(Caso fictício, construído a partir de padrões comuns em implantações B2B. Empresa de exemplo: "Vale Alimentos", cliente de um portal de pedidos integrado ao ERP.)*

## Linha do tempo
| Momento | Fato | Módulo que teria ajudado |
|--|--|--|
| Semana 1 | Início da implantação | 05 — kick-off com "É / Não é / Faz / Não faz" e Matriz CSD |
| Semana 2 | Levantamento de requisitos | 05 — fluxo atual × futuro; regras por escrito |
| Semana 8 | Go-live | 07 — status report com semáforo |
| Semana 9 | Entrega validada em chamada, confirmada por mensagem, **sem documento assinado**; 15 pontos de feedback | 07 — forma do aceite; 01 — triagem |
| Semana 10 | Escalonamento; a liderança decide **atender tudo**; regras recebidas por escrito | 06 — decisão e registro |
| Semana 11 | 23 solicitações consolidadas | 02 — consolidação; 03 — priorização |
| Semana 12 | Cancelamento do contrato | 06 — registro retroativo honesto |

## 1. Triagem (módulo 01)
- **"Havia uma promessa?"** O cliente tratava "cancelar pedido" como defeito, mas o escopo contratado não incluía cancelamento → **capacidade ausente**, não bug.
- **Lacuna de expectativa:** um pedido era algo que o produto já fazia → orientar o cliente e registrar o sinal, sem abrir história.
- **Não reproduzido:** antes de classificar como defeito, pedir evidência (passo a passo, data, perfil, print).

## 2. Consolidação (módulo 02)
- Página única com a origem de cada lote, resumo por situação e lista completa com o ID do board.
- Agrupar por problema revelou o tema principal: **o cliente esperava um sistema completo de força de vendas** (cancelar e editar pedidos, metas, nota fiscal). Esse achado valia mais que qualquer item isolado.

## 3. Priorização (módulo 03)
- Com a decisão "atender tudo", a pergunta deixou de ser "fazer ou não" e virou **ordem e corte por fase**: primeiro o que travava a operação.
- **Compre uma funcionalidade** teria ajudado: com 100 pontos para distribuir, o próprio cliente mostraria a ordem real.
- Itens que valem para todos os clientes foram para **Evolução do Produto**, para não ficarem presos ao contrato.

## 4. Decisão (módulo 06)
- **Opções:** A) atender tudo em duas fases; B) renegociar o escopo; C) só o contratado (risco alto de cancelamento).
- **O que mudaria a decisão:** o cliente aceitar contorno para cancelamento, ou as regras por escrito mostrarem esforço muito maior.
- **Registro honesto:** a decisão foi A; o cancelamento veio duas semanas depois. A lacuna nasceu no kick-off, não na decisão.

## 5. Cinco lições
1. "É / Não é / Faz / Não faz" no kick-off.
2. Registrar e formalizar o aceite.
3. Partir do problema, não do sistema de referência.
4. Regras de negócio por escrito antes de desenvolver.
5. Registrar as decisões da liderança com impacto e seguir priorizando dentro delas.
