# Fluxo AS-IS - Processo Atual de Reembolsos

Este diagrama representa o processo atual de reembolsos, baseado em planilhas Excel e e-mails.

## Fluxo Principal

```mermaid
flowchart LR
    A[Colaborador<br/>Preenche planilha<br/>Anexa comprovantes] --> B[E-mail]
    B --> C[Técnico-Adm<br/>Verifica conformidade]
    C -->|Ajustes| A
    C -->|OK| D[Gestor<br/>Avalia]
    D -->|Ajustes| A
    D -->|Aprova| E[Técnico-Adm<br/>Informa e encaminha]
    E --> F[Financeiro<br/>Paga e arquiva]
```

## Pontos de Dor

```mermaid
flowchart LR
    P1[E-mails dispersos] --> R1[Sem rastreabilidade]
    P2[Verificação manual 90 dias] --> R2[Retrabalho]
    P3[Conhecimento tácito] --> R3[Risco operacional]
    P4[Multiplos gestores] --> R4[Ciclo longo]
    P5[Sem trilha de auditoria] --> R1
```

## Comparativo: AS-IS vs TO-BE

```mermaid
flowchart LR
    subgraph AS-IS
        direction TB
        AS1[Planilha] --> AS2[E-mail] --> AS3[E-mail] --> AS4[E-mail] --> AS5[Arquiva]
    end

    subgraph TO-BE
        direction TB
        TO1[App] --> TO2[Sistema] --> TO3[Sistema] --> TO4[Sistema] --> TO5[Pago]
    end
```
