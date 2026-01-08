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
