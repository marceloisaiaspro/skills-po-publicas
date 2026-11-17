# Template — Documentação de produto (estrutura de 11 seções)

*(Uso: módulo 10. Cada seção vira uma página-filha na Wiki. Seção sem conteúdo recebe "Em construção — responsável, previsão".)*

```markdown
# <Produto> — Documentação Oficial
Autor: · Validado por: · Versão: 1.0 · Atualizado em: DD/MM/AAAA
Acessos: <ambientes, logins e senhas conforme decisão do time — ver módulo 10 §8; avisar o PO antes de enviar cópia a terceiros>

| Seção | Página | Status |
|--|--|--|
| 1 | Visão do Produto | ✅ / 🚧 |
| 2 | Especificação Funcional | |
| 3 | Regras de Negócio | |
| 4 | Casos de Uso | |
| 5 | Interface e Telas | |
| 6 | Personas | |
| 7 | Especificação Técnica | |
| 8 | API / Integrações | |
| 9 | Configuração e Manual de Uso | |
| 10 | Glossário | |
| 11 | FAQ | |
| Apoio | Questionário para Implantação · Memória Técnica | |
```

## 1. Visão do Produto
```markdown
**Problema:** <de quem, qual dor, como resolvem hoje>
**Para quem:** <personas — ver seção 6>
**Proposta:** <o que o produto faz, em uma frase>
| O produto É | O produto NÃO É |
|--|--|
| O produto FAZ | O produto NÃO FAZ |
**Indicador de sucesso:** <métrica + como medir>
**Dependências:** <ERP, integrações, parceiros>
```

## 2. Especificação Funcional
```markdown
| Código | Requisito | Prioridade | Regras ligadas | Coberto por (board) |
|--|--|--|--|--|
| RF01 | | Must/Should/Could | RN01, RN03 | #____ / Sem item |

### Macrofluxos
MF01 — <nome>: <diagrama Mermaid ou passos numerados, com atores e sistemas>
```

## 3. Regras de Negócio (tabela consolidada — fonte da verdade)
```markdown
| Código | Regra | Exemplo | Origem (quem, quando) | Status |
|--|--|--|--|--|
| RN01 | | | | Vigente / Revogada em DD/MM — ver RNxx / A confirmar |

### Requisitos não funcionais
| Código | Requisito | Meta medível | Status |
|--|--|--|--|
| RNF01 | | | |
```

## 4. Casos de Uso
```markdown
### UC01 — <nome>
**Ator:** · **Pré-condição:** · **Gatilho:**
**Fluxo principal:** 1. … 2. …
**Fluxos alternativos / exceções:** 
**Regras aplicadas:** RN__ — <nome curto>
**Pós-condição:**
```

## 5. Interface e Telas
```markdown
### Tela: <nome>
<print ou wireframe>
| Campo | Tipo | Obrigatório | Origem do dado (tabela/rotina — ou "a confirmar") | Regra |
|--|--|--|--|--|
**Ações (botões):** <ação → resultado → regra>
**Mensagens de erro:** <texto exato → quando aparece>
```

## 6. Personas
```markdown
| Persona | Quem é | O que precisa | Como mede sucesso | Telas que usa |
|--|--|--|--|--|
```

## 7. Especificação Técnica
```markdown
> Versão não validada pelo time técnico (remover após validação do tech lead).
**Arquitetura:** · **Banco(s):** · **Front-end:** · **Back-end:** · **Hospedagem:**
**Acesso ao ERP:** leitura / gravação — em quais tabelas (a confirmar com o tech lead)
**Rotinas agendadas:** <nome, frequência, o que faz>
**Logs e monitoramento:**
```

## 8. API / Integrações
```markdown
| Endpoint / integração | Método | Entrada | Saída | Erros | Regra |
|--|--|--|--|--|--|
Autenticação: <tipo — sem credenciais>
```

## 9. Configuração e Manual de Uso
```markdown
### Configuração (implantação)
1. <passo> — quem faz — pré-requisito
### Uso no dia a dia
1. <passo com print>
```

## 10. Glossário
```markdown
| Termo | Significado | Onde aparece |
|--|--|--|
```

## 11. FAQ
```markdown
**<pergunta como o usuário faz>**
<resposta curta> — Regra: RN__ · Atualizado em DD/MM
```

## Histórico da documentação
```markdown
| Data | Versão | O que mudou | Quem pediu |
|--|--|--|--|
```
