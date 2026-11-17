# Contexto da empresa — modelo para preencher

*(Único arquivo específico da empresa. Preencha uma vez e mantenha atualizado. O que estiver vazio, a skill pergunta.)*

## Empresa e produtos
- **Empresa:** <nome> — <segmento, ex.: software B2B integrado a ERP>
- **Produtos sob responsabilidade do PO:** <produto: o que faz, quem usa>
- **Glossário completo:** skill **po-historias-de-usuario**, `referencias/glossario-modelo.md`.

## Candidatas a North Star (a validar com a liderança)
| Produto | Candidata | Por quê |
|--|--|--|
| <produto> | <ex.: pedidos aceitos no ERP sem recusa, por semana> | <o que mostra sobre o valor entregue> |

## Pessoas e papéis (por cargo)
<ex.: diretoria · coordenação de desenvolvimento · tech lead · POs · comercial>. **QA dedicado?** <sim / não — quem revisa>

## Board (resumo)
- **Ferramenta:** <Azure DevOps | Jira | outra>
- **Modos usados:** <Implantação, Sustentação, Produto, Projeto Pontual — ver po-historias-de-usuario>
- **Prioridade:** <como marcar urgente>
- **Origem do pedido:** <ex.: tag `Origem <Cliente>`>
- **Estados da Task:** <ex.: New → In Progress → Code Review → QA → Closed>
- **Gravar no board somente após confirmação do PO.**

## Wiki
```
<WIKI DO PRODUTO>/Clientes/
├── Em Produção/<Cliente>/
│   ├── Status Report      (índice + um relatório por data)
│   ├── Solicitações Consolidadas
│   ├── Datas e Prazos
│   └── Acessos            (se o time decidir guardar)
└── Cancelados/<Cliente>/
```

## Lições registradas
1. <lição — o que aconteceu, o que muda daqui para frente>
