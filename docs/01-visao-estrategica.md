# Visão Estratégica

[Voltar ao Resumo do projeto](../README.md)


## 1. Definição do Problema

### Contexto Organizacional

O processo de reembolso corporativo é um **processo transversal**, que envolve colaboradores, áreas administrativas, gestores responsáveis por centros de custo e a área financeira. Trata-se de um fluxo recorrente, sensível a prazos, valores e conformidade, e que impacta diretamente a confiança interna, a eficiência operacional e a capacidade de prestação de contas da organização.

Atualmente, esse processo é conduzido de forma **predominantemente manual**, apoiado em planilhas e trocas de e-mails, o que limita sua capacidade de escala, rastreabilidade e padronização decisória.

### Problema Central

O processo atual de reembolso corporativo apresenta **fragilidades estruturais de governança, rastreabilidade e eficiência operacional**, decorrentes da:

- Ausência de um fluxo formalizado
- Dependência excessiva de esforço manual
- Falta de mecanismos sistêmicos de controle e auditoria

Essas fragilidades tornam-se **especialmente críticas** em cenários que envolvem:

- Múltiplos projetos associados a um mesmo pedido de reembolso
- Diferentes centros de custo sob responsabilidade de gestores distintos
- Necessidade de aprovações parciais por item de despesa
- Exigências de conformidade documental e auditoria posterior

### Sintomas Observáveis

| Operacionais                                                      | Institucionais                                                                    |
|-------------------------------------------------------------------|-----------------------------------------------------------------------------------|
| Alto esforço manual para consolidação de informações              | Baixa rastreabilidade das decisões (quem aprovou, quando, com base em quê)        |
| Dificuldade com aprovações parciais e múltiplos centros de custo  | Dependência de conhecimento tácito de pessoas específicas                         |
| Maior volume de devoluções para ajuste (retrabalho)               | Fragilidade na recuperação de evidências para auditoria                           |
| Erros manuais recorrentes                                         | Ausência de métricas sobre tempo de ciclo, retrabalho e gargalos                  |

### Causas Estruturais

O problema não decorre de falhas individuais, mas de **causas estruturais**:

1. Ausência de um fluxo formalizado com estados, regras e responsabilidades explícitas
2. Falta de segregação sistêmica de funções (solicitação, validação, aprovação, pagamento)
3. Tratamento de comprovantes como anexos informais, não como registros de evidência
4. Inexistência de trilha de auditoria automática para decisões e transições
5. Baixa padronização na forma como gestores avaliam e aprovam despesas

---

## 2. A Proposta: Institucionalizar, Não Digitalizar

A solução **não replica o processo atual em software**. Mas sim o **redesenha** para funcionar sob pressão, auditoria e troca de gestão.

### Pilares da Solução

**1. Responsivo-First com PWA**

- Colaborador registra o item no momento do gasto, via navegador mobile
- Captura de comprovante via câmera ou upload
- PWA instalável: ícone na home do celular, funciona offline (rascunhos)
- Redução de atrito: sem necessidade de baixar app na store

**2. Comprovante Digital**

- Upload obrigatório de comprovante fiscal para cada item
- Visualizador integrado para análise do técnico-administrativo
- Armazenamento seguro vinculado à solicitação

**3. Governança por Design**

- Trilha de auditoria imutável: todas as ações registradas (who, what, when, why)
- Gates de conformidade:
  - 1º gate: Validação automática (regra 90 dias)
  - 2º gate: Técnico-administrativo (conformidade processual)
  - 3º gate: Gestores (viabilidade orçamentária por centro de custo)
- Separação de responsabilidades

**4. Aprovação Granular**

- Aprovação parcial nativa: gestores aprovam o que é viável, rejeitam o que não couber
- Justificativas obrigatórias em rejeições
- Itens aprovados seguem para pagamento, rejeitados ficam documentados
- Flexibilidade operacional sem perder controle

**5. Resiliência Organizacional**

- Sistema projetado para sobreviver à troca de gestão
- Processo documentado no próprio sistema
- Não depende de conhecimento concentrado em pessoas específicas
- Onboarding de novos colaboradores/gestores via interface autoexplicativa

---

## 3. Impactos Esperados

### Impactos Operacionais

| Impacto | Descrição |
|---------|-----------|
| Redução de esforço manual | Validações automáticas eliminam verificações repetitivas |
| Redução de retrabalho | Erros detectados automaticamente antes da submissão |
| Aceleração do ciclo | Aprovações paralelas por centro de custo |
| Visibilidade em tempo real | Colaboradores acompanham status sem depender de e-mail |

### Impactos Institucionais

| Impacto | Descrição |
|---------|-----------|
| Rastreabilidade completa | Trilha de auditoria imutável |
| Segregação de responsabilidades | Técnico-adm valida; gestor decide; financeiro paga |
| Resiliência organizacional | Processo vive no sistema, não na cabeça das pessoas |
| Governança por design | Comprovantes organizados, decisões justificadas |

### Capacidades Institucionais Criadas

| Capacidade | Benefício |
|------------|-----------|
| Suporte a múltiplos centros de custo | Aprovações parciais sem ambiguidade de fluxo |
| Evidências organizadas | Comprovantes auditáveis e centralizados |
| Clareza decisória | Registro de quem decide, quando e com base em quê |
| Resiliência organizacional | Processo independe de pessoas específicas |

---

## 4. Mapeamento AS-IS para TO-BE

| - | Dor do Processo Atual | Como o Sistema Resolve |
|---|----------------------|------------------------|
| 1 | Planilha Excel não padronizada | Formulário digital com validações automáticas |
| 2 | E-mail não padronizado | Fluxo digital com estados claros e notificações |
| 3 | Consolidação trabalhosa | Dashboard centralizado com visão consolidada |
| 4 | Rastreio difícil | Trilha de auditoria completa |
| 5 | Colaborador em múltiplos projetos | Solicitação única com itens distribuídos por CC |
| 6 | Gestor gerencia vários CCs | Dashboard agrupa itens pendentes por CC |
| 7 | Verificar conformidade de comprovantes | Upload obrigatório + visualizador integrado |
| 8 | Regra dos 90 dias manual | Validação automática com bloqueio |
| 9 | Solicitar ajustes via e-mail | Botão "Solicitar Ajuste" com notificação |
| 10 | Aprovação tudo ou nada | Aprovação granular por item |
| 11 | Informar status via e-mail | Acompanhamento em tempo real no sistema |
| 12 | Arquivar comprovantes em pasta | Armazenamento digital vinculado à solicitação |


## 5. Diferenciais Competitivos

**O que esta solução faz que planilhas/workflows genéricos não fazem:**

1. Validação em tempo real (regra 90 dias)
2. Aprovação multi-gestor paralela (por centro de custo)
3. Gestão de parcialidade nativa (itens aprovados seguem, rejeitados ficam rastreáveis)
4. Trilha de auditoria imutável (compliance fiscal)
5. Mobile-first (captura no momento do gasto)
6. Dashboards por perfil (cada ator vê dados relevantes)
7. Notificações contextuais (só quando há ação pendente)

---

## 6. Critérios de Sucesso

A solução será considerada bem-sucedida se:

- Reduzir significativamente o esforço manual e o retrabalho
- Fornecer clareza sobre quem decide, quando e com base em quais informações
- Suportar múltiplos centros de custo e aprovações parciais sem ambiguidade
- Manter evidências organizadas e auditáveis
- Tornar o processo resiliente à troca de pessoas e gestão

---

[Voltar ao README](../README.md) | [Próximo: High Level Design](02-high-level-design.md)
