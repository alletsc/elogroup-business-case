# Protótipos Visuais

[Voltar ao Resumo do projeto](../README.md)

## **Design System:**

- **Mobile-first**: Interface otimizada para mobile, responsiva para web
- **Minimalismo funcional**: Apenas ações críticas visíveis
- **Feedback imediato**: Loading states, confirmações visuais
- **Acessibilidade**: Contraste, tamanhos de fonte, navegação por teclado

**Cores:**

![alt text](../assets/imgs/paleta-cores.png)

---

## Mobile - Colaborador

Versão Mermaid — Dashboard Mobile (Colaborador)

```mermaid
flowchart TB
    subgraph MOBILE["Mobile · Colaborador"]
        HEADER["☰  Minhas Solicitações    👤"]

        CTA["＋ Nova Solicitação"]

        subgraph ANDAMENTO["Em Andamento (3)"]
            S1["Sol. #1234<br/>🟡 Aguardando Validação<br/>3 itens · R$ 450,00 →"]
        end

        subgraph CONCLUIDAS["Concluídas (12)"]
            EXP["Expandir ▼"]
        end

        NAV["Home · Histórico · Perfil"]
    end

    HEADER --> CTA
    CTA --> ANDAMENTO
    ANDAMENTO --> CONCLUIDAS
    CONCLUIDAS --> NAV
```
### Criar Solicitação - Adicionar Item

```mermaid
flowchart TB
    subgraph MOBILE["Mobile · Colaborador · Nova Solicitação"]
        HEADER["← Nova Solicitação   ?"]

        STEP["Item 1 de 1"]

        DESC["Descrição *<br/>Ex: Uber – Reunião Cliente"]

        subgraph VALDATA["Valor e Data"]
            VAL["Valor *<br/>R$ 45,00"]
            DATA["Data *<br/>15/01/2026"]
        end

        CC["Centro de Custo *<br/>Projeto Alpha ▼"]

        subgraph COMP["Comprovante"]
            UP["Anexar Foto / PDF"]
            WARN["⚠️ Obrigatório"]
        end

        ADD["+ Adicionar Outro Item"]
        SUBMIT["Submeter"]
    end

    HEADER --> STEP
    STEP --> DESC
    DESC --> VALDATA
    VALDATA --> CC
    CC --> COMP
    COMP --> ADD
    ADD --> SUBMIT
```

---

## Mobile - Gestor

### Dashboard de Aprovações

```mermaid
flowchart TB
    subgraph MOBILE["Mobile · Gestor · Aprovações"]
        HEADER["☰ Aprovações   👤"]

        FILTER["Centro de Custo: Todos ▼"]

        ALERT["⚠ 12 itens aguardando"]

        subgraph TODAY["Hoje (5)"]
            A1["João Silva · Sol. #1234<br/>R$ 295,00 · 2 itens<br/>Uber + Almoço Cliente<br/>Revisar Itens →"]
        end

        subgraph OUTROS["Outros Pendentes"]
            A2["Maria Santos · Sol. #1230<br/>R$ 450,00 · 3 itens<br/>Revisar Itens →"]
        end

        BULK["Aprovar Tudo em Lote"]
    end

    HEADER --> FILTER
    FILTER --> ALERT
    ALERT --> TODAY
    TODAY --> OUTROS
    OUTROS --> BULK
```

### Aprovar Item (Swipe Interface)

```mermaid
flowchart TB
    subgraph MOBILE["Mobile · Gestor · Aprovar Item"]
        HEADER["← João Silva · Sol. #1234"]

        STEP["Item 1 de 2"]

        ITEM["Uber – Reunião Cliente ABC<br/>R$ 45,00 · 15/01/2026<br/>CC: Projeto Alpha"]

        STATUS["🟢 Validado Técnico-Adm"]

        COMP["Ver Comprovante →"]

        ACTION["Swipe para ação"]

        subgraph DECISION["Decisão"]
            NO["❌ Não Aprovar"]
            YES["✓ Aprovar"]
        end
    end

    HEADER --> STEP --> ITEM --> STATUS --> COMP --> ACTION --> DECISION
```

### Modal de Rejeição

```mermaid
flowchart TB
    subgraph MODAL["Modal · Rejeitar Item"]
        TITLE["Rejeitar Item"]

        REASON["Motivo da rejeição *<br/>Fora do orçamento · Projeto · Comprovante · Valor · Outro"]

        JUST["Justificativa (texto livre)"]

        ACTIONS["Cancelar | Confirmar"]
    end

    TITLE --> REASON --> JUST --> ACTIONS
```
---

## Web - Técnico-Administrativo

### Dashboard de Validação

```mermaid
flowchart TB
    subgraph WEB["Web · Técnico-Adm · Validação"]
        HEADER["Validação de Solicitações"]

        FILTERS["Filtros<br/>Status · Data · Colaborador · Centro de Custo"]

        LIST["Aguardando Validação (24 itens)<br/>Sol. #1234 · João · 3 itens · R$ 450 → Revisar"]

        ACTIONS["Selecionar Todos · Aprovar em Lote · Exportar CSV"]
    end

    HEADER --> FILTERS --> LIST --> ACTIONS
```
### Validar Itens (Modal)

```mermaid
flowchart TB
    subgraph MODAL["Modal · Validar Solicitação"]
        ITEM1["Item 1<br/>Uber – Reunião Cliente<br/>R$ 45 · 15/01 · Projeto Alpha<br/>Regra 90 dias ✓ OK"]

        COMP1["Ver Comprovante →"]

        DEC1["Decisão<br/>Aprovar | Solicitar Ajuste"]

        ITEM2["Item 2<br/>Almoço – Cliente XYZ<br/>R$ 150 · 14/01"]

        JUST2["Justificativa<br/>Comprovante ilegível"]

        ACTIONS["Cancelar | Salvar Validação"]
    end

    ITEM1 --> COMP1 --> DEC1
    DEC1 --> ITEM2 --> JUST2 --> ACTIONS
```
---

## Web - Financeiro

### Dashboard de Pagamentos

```mermaid
flowchart TB
    subgraph WEB["Web · Financeiro · Pagamentos"]
        HEADER["Pagamentos"]

        SUMMARY["Resumo<br/>Aguardando · Agendados · Pagos"]

        FILTERS["Filtros<br/>Status · Período · CC · Colaborador"]

        LIST["João Silva · Sol. #1234<br/>2 itens · R$ 195<br/>Aprovado em 16/01 → Agendar"]

        ACTIONS["Selecionar Todos · Agendar em Lote · Exportar ERP"]
    end

    HEADER --> SUMMARY --> FILTERS --> LIST --> ACTIONS
```
### Agendar Pagamento (Modal)
```mermaid
flowchart TB
    subgraph MODAL["Modal · Agendar Pagamento"]
        INFO["Colaborador: João Silva<br/>Valor: R$ 195"]

        BANK["Dados Bancários<br/>Banco · Agência · Conta · CPF"]

        DATE["Data de Pagamento<br/>20/01/2026"]

        METHOD["Forma<br/>PIX · TED · DOC"]

        AUDIT["Trilha de Aprovação<br/>✓ Técnico-Adm<br/>✓ Gestor"]

        ACTIONS["Cancelar | Confirmar Agendamento"]
    end

    INFO --> BANK --> DATE --> METHOD --> AUDIT --> ACTIONS
```

---
### Detalhes da Solicitação

```mermaid
flowchart TB
    subgraph MOBILE["Mobile · Colaborador · Detalhes da Solicitação"]
        HEADER["← Solicitação #1234   ⋮"]

        STATUS["🟡 Aguardando Validação"]
        TOTAL["Total: R$ 450,00"]

        subgraph TL["Timeline"]
            T1["✓ Criada (15/01 14:30)"]
            T2["✓ Submetida (15/01 14:35)"]
            T3["○ Validação Técnica"]
            T4["○ Aprovação Gestor"]
            T5["○ Pagamento"]
        end

        subgraph ITENS["Itens (3)"]
            I1["1. Uber – Reunião Cliente<br/>R$ 45,00 · 15/01/2026<br/>CC: Projeto Alpha<br/>Ver Comprovante →"]
        end

        CANCEL["Cancelar Solicitação"]
    end

    HEADER --> STATUS --> TOTAL --> TL --> ITENS --> CANCEL
```

---

## Respresentação de telas via ASCII

## Mobile - Colaborador

### Dashboard / Minhas Solicitações

```
┌───────────────────────────────────────┐
│ ☰  Minhas Solicitações            👤 │
├───────────────────────────────────────┤
│                                       │
│   [+ Nova Solicitação]                │
│                                       │
│   Em Andamento (3)                    │
│   ┌───────────────────────────────┐  │
│   │ Sol. #1234                    │  │
│   │ 🟡 Aguardando Validação       │  │
│   │ 3 itens • R$ 450,00           │  │
│   │                       Ver →   │  │
│   └───────────────────────────────┘  │
│                                       │
│   Concluídas (12)                     │
│   ┌───────────────────────────────┐  │
│   │ Expandir ▼                    │  │
│   └───────────────────────────────┘  │
│                                       │
├───────────────────────────────────────┤
│   Home        Histórico        Perfil │
└───────────────────────────────────────┘
```

### Criar Solicitação - Adicionar Item

```
┌─────────────────────────────────┐
│ <  Nova Solicitação        [?] │
├─────────────────────────────────┤
│                                 │
│ Item 1 de 1                     │
│                                 │
│ ┌─────────────────────────────┐│
│ │ Descrição *                 ││
│ │ [Ex: Uber - Reunião Cliente]││
│ └─────────────────────────────┘│
│                                 │
│ ┌──────────┐  ┌───────────────┐│
│ │ Valor *  │  │ Data *        ││
│ │ R$ 45,00 │  │ 15/01/2026    ││
│ └──────────┘  └───────────────┘│
│                                 │
│ Centro de Custo *               │
│ [Projeto Alpha ▼]               │
│                                 │
│ ┌─ Comprovante ───────────────┐│
│ │                             ││
│ │   [ Anexar Foto/PDF ]       ││
│ │                             ││
│ └─────────────────────────────┘│
│                                 │
│ ⚠️ Comprovante obrigatório      │
│                                 │
│ [+ Adicionar Outro Item]        │
│                                 │
│          [Submeter]             │
│                                 │
└─────────────────────────────────┘
```

### Detalhes da Solicitação

```
┌─────────────────────────────────┐
│ <  Solicitação #1234       ⋮   │
├─────────────────────────────────┤
│                                 │
│ 🟡 Aguardando Validação         │
│                                 │
│ Total: R$ 450,00                │
│                                 │
│ ┌─ Timeline ──────────────────┐│
│ │ ✓ Criada (15/01 14:30)      ││
│ │ ✓ Submetida (15/01 14:35)   ││
│ │ ○ Validação Técnica         ││
│ │ ○ Aprovação Gestor          ││
│ │ ○ Pagamento                 ││
│ └─────────────────────────────┘│
│                                 │
│ ┌─ Itens (3) ─────────────────┐│
│ │                             ││
│ │ 1. Uber - Reunião Cliente   ││
│ │    R$ 45,00 • 15/01/2026    ││
│ │    CC: Projeto Alpha        ││
│ │    [Ver Comprovante >]      ││
│ │                             ││
│ └─────────────────────────────┘│
│                                 │
│     [Cancelar Solicitação]      │
│                                 │
└─────────────────────────────────┘
```

---

## Mobile - Gestor

### Dashboard de Aprovações

```
┌─────────────────────────────────┐
│ ☰  Aprovações             👤   │
├─────────────────────────────────┤
│                                 │
│ Centro de Custo: [Todos ▼]      │
│                                 │
│ ⚠ 12 itens aguardando           │
│                                 │
│ ┌─ Hoje (5) ──────────────────┐│
│ │                             ││
│ │ João Silva - Sol. #1234     ││
│ │ R$ 295,00 • 2 itens         ││
│ │ Uber + Almoço Cliente       ││
│ │                             ││
│ │    [Revisar Itens →]        ││
│ └─────────────────────────────┘│
│                                 │
│ ┌───────────────────────────┐  │
│ │ Maria Santos - Sol. #1230 │  │
│ │ R$ 450,00 • 3 itens       │  │
│ │    [Revisar Itens →]      │  │
│ └───────────────────────────┘  │
│                                 │
│    [Aprovar Tudo em Lote]       │
│                                 │
└─────────────────────────────────┘
```

### Aprovar Item (Swipe Interface)

```
┌─────────────────────────────────┐
│ <  João Silva - Sol. #1234      │
├─────────────────────────────────┤
│                                 │
│ Item 1 de 2                     │
│                                 │
│ ┌─────────────────────────────┐│
│ │ Uber - Reunião Cliente ABC  ││
│ │                             ││
│ │ R$ 45,00                    ││
│ │ Data: 15/01/2026            ││
│ │ CC: Projeto Alpha           ││
│ │                             ││
│ │ 🟢 Validado Técnico-Adm     ││
│ │                             ││
│ │ [Ver Comprovante]           ││
│ └─────────────────────────────┘│
│                                 │
│ ← Swipe para ação              │
│                                 │
│ ┌──────────┐     ┌────────────┐│
│ │  ❌ NÃO  │     │  ✓ SIM     ││
│ │ APROVAR  │     │  APROVAR   ││
│ └──────────┘     └────────────┘│
│                                 │
│ [❌ Rejeitar] [✓ Aprovar]       │
│                                 │
└─────────────────────────────────┘
```

### Modal de Rejeição

```
┌─────────────────────────────────┐
│ Rejeitar Item                   │
├─────────────────────────────────┤
│                                 │
│ Motivo da rejeição: *           │
│                                 │
│ ( ) Fora do orçamento           │
│ ( ) Não relacionado ao projeto  │
│ ( ) Comprovante inválido        │
│ ( ) Valor acima do permitido    │
│ ( ) Outro                       │
│                                 │
│ ┌─────────────────────────────┐│
│ │ Justificativa:              ││
│ │ [Campo de texto]            ││
│ └─────────────────────────────┘│
│                                 │
│   [Cancelar]  [Confirmar]       │
│                                 │
└─────────────────────────────────┘
```

---

## Web - Técnico-Administrativo

### Dashboard de Validação

```
┌────────────────────────────────────────────────────────────────────┐
│ [Logo]  Validação de Solicitações                    João ▼ [Sair] │
├────────────────────────────────────────────────────────────────────┤
│                                                                    │
│  Filtros: [Pendentes ▼] [Data ▼] [Colaborador] [Centro Custo]     │
│                                                                    │
│  ┌──────────────────────────────────────────────────────────────┐ │
│  │ ☐  Aguardando Validação (24 itens)                          │ │
│  ├──────────────────────────────────────────────────────────────┤ │
│  │                                                              │ │
│  │ ☐ Sol. #1234 | João Silva    | 15/01 | 3 itens | R$ 450    │ │
│  │                                                    [Revisar] │ │
│  │                                                              │ │
│  │ ☐ Sol. #1230 | Maria Santos  | 15/01 | 2 itens | R$ 300    │ │
│  │   ✓ Todos comprovantes OK                        [Revisar] │ │
│  │                                                              │ │
│  │                                        [< 1 2 3 ... 8 >]     │ │
│  └──────────────────────────────────────────────────────────────┘ │
│                                                                    │
│  [☐ Selecionar Todos]  [Aprovar em Lote]  [Exportar CSV]          │
│                                                                    │
└────────────────────────────────────────────────────────────────────┘
```

### Validar Itens (Modal)

```
┌────────────────────────────────────────────────────────────────────┐
│ Validar Solicitação #1234 - João Silva                        [X] │
├────────────────────────────────────────────────────────────────────┤
│                                                                    │
│  ┌─ Item 1 de 3 ──────────────────────────────────────────────┐   │
│  │                                                             │   │
│  │  Uber - Reunião Cliente ABC                                │   │
│  │  R$ 45,00 | 15/01/2026 | Projeto Alpha                     │   │
│  │                                                             │   │
│  │  Regra 90 dias: ✓ OK (0 dias atrás)                        │   │
│  │                                                             │   │
│  │  Comprovante: [Ver PDF/Imagem →]                           │   │
│  │                                                             │   │
│  │  Decisão: ( ) Aprovar  ( ) Solicitar Ajuste                │   │
│  │                                                             │   │
│  └─────────────────────────────────────────────────────────────┘   │
│                                                                    │
│  ┌─ Item 2 de 3 ──────────────────────────────────────────────┐   │
│  │                                                             │   │
│  │  Almoço - Cliente XYZ                                      │   │
│  │  R$ 150,00 | 14/01/2026 | Projeto Alpha                    │   │
│  │                                                             │   │
│  │  Decisão: ( ) Aprovar  (•) Solicitar Ajuste                │   │
│  │                                                             │   │
│  │  ┌───────────────────────────────────────────────────────┐ │   │
│  │  │ Justificativa:                                        │ │   │
│  │  │ Comprovante ilegível. Favor anexar nova imagem.       │ │   │
│  │  └───────────────────────────────────────────────────────┘ │   │
│  │                                                             │   │
│  └─────────────────────────────────────────────────────────────┘   │
│                                                                    │
│                            [Cancelar]  [Salvar Validação]         │
│                                                                    │
└────────────────────────────────────────────────────────────────────┘
```

---

## Web - Financeiro

### Dashboard de Pagamentos

```
┌────────────────────────────────────────────────────────────────────┐
│ [Logo]  Pagamentos                                  Maria ▼ [Sair] │
├────────────────────────────────────────────────────────────────────┤
│                                                                    │
│  ┌─ Resumo ──────────────────────────────────────────────────┐    │
│  │  Aguardando Agendamento: 12 itens | R$ 3.450,00          │    │
│  │  Agendados para Hoje: 5 itens | R$ 890,00                │    │
│  │  Pagos Hoje: 3 itens | R$ 540,00                         │    │
│  └────────────────────────────────────────────────────────────┘    │
│                                                                    │
│  Filtros: [Aguardando ▼] [Período] [Centro Custo] [Colaborador]   │
│                                                                    │
│  ┌────────────────────────────────────────────────────────────┐   │
│  │ ☐ João Silva | Sol. #1234 | 2 itens | R$ 195,00           │   │
│  │   Aprovado em: 16/01/2026 14:30                           │   │
│  │   Dados bancários: Banco do Brasil - Ag 1234 - CC 56789   │   │
│  │                                      [Agendar] [Detalhes] │   │
│  └────────────────────────────────────────────────────────────┘   │
│                                                                    │
│  [☐ Selecionar Todos]  [Agendar em Lote]  [Exportar para ERP]     │
│                                                                    │
└────────────────────────────────────────────────────────────────────┘
```



```
┌────────────────────────────────────────────────────────────────────┐
│ Agendar Pagamento                                             [X] │
├────────────────────────────────────────────────────────────────────┤
│                                                                    │
│  Colaborador: João Silva                                          │
│  Valor Total: R$ 195,00                                           │
│                                                                    │
│  Dados Bancários:                                                 │
│  ┌────────────────────────────────────────────────────────────┐   │
│  │ Banco: Banco do Brasil                                     │   │
│  │ Agência: 1234-5                                            │   │
│  │ Conta: 56789-0                                             │   │
│  │ CPF: 123.456.789-00                                        │   │
│  └────────────────────────────────────────────────────────────┘   │
│                                                                    │
│  Data de Pagamento: [20/01/2026] (próximo dia útil)               │
│                                                                    │
│  Forma: ( ) TED  (•) PIX  ( ) DOC                                 │
│                                                                    │
│  ┌─ Trilha de Aprovação ───────────────────────────────────────┐  │
│  │ ✓ Validado por: Ana (Técnico-Adm) - 16/01 10:00            │  │
│  │ ✓ Aprovado por: Carlos (Gestor) - 16/01 14:30              │  │
│  └──────────────────────────────────────────────────────────────┘  │
│                                                                    │
│                            [Cancelar]  [Confirmar Agendamento]    │
│                                                                    │
└────────────────────────────────────────────────────────────────────┘
```

---

## Fluxo de Interação

```mermaid
sequenceDiagram
    actor Colaborador
    actor Técnico as Técnico-Adm
    actor Gestor
    actor Financeiro

    Note over Colaborador: Cria solicitação
    Note over Colaborador: Adiciona itens
    Note over Colaborador: Anexa comprovantes

    Colaborador->>Técnico: Submete solicitação

    Note over Técnico: Recebe notificação
    Note over Técnico: Valida itens e comprovantes

    alt Itens válidos
        Técnico->>Gestor: Encaminha para aprovação
    else Precisa ajuste
        Técnico-->>Colaborador: Solicita ajuste
        Colaborador->>Técnico: Reenvia corrigido
    end

    Note over Gestor: Recebe notificação
    Note over Gestor: Analisa itens do seu CC

    alt Aprova
        Gestor->>Financeiro: Encaminha para pagamento
    else Rejeita
        Gestor-->>Colaborador: Notifica rejeição
    end

    Note over Financeiro: Recebe notificação
    Note over Financeiro: Agenda pagamento
    Note over Financeiro: Registra pagamento

    Financeiro-->>Colaborador: Notifica pagamento realizado
```

---

[Anterior: High Level Design](02-high-level-design.md) | [Próximo: Requisitos](04-requisitos.md)
