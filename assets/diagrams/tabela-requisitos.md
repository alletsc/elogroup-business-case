# Tabela de Requisitos - Sistema de Reembolsos

## Requisitos Funcionais (Essenciais)

| Domínio | Capacidade Funcional |
| --- | --- |
| Acesso e Perfis | Autenticação corporativa (OAuth) e perfis distintos por papel |
| Solicitação | Criação de solicitações com múltiplos itens e comprovante obrigatório |
| Regras de Negócio | Validações automáticas (ex.: regra dos 90 dias) |
| Validação Técnica | Análise de conformidade com solicitação de ajuste |
| Aprovação Gerencial | Aprovação granular por item e por centro de custo |
| Aprovação Paralela | Múltiplos gestores aprovando simultaneamente |
| Pagamentos | Agendamento individual ou em lote |
| Notificações | Atualizações automáticas de status |
| Auditoria | Registro completo de decisões e ações |
| Relatórios | Visão consolidada de status, tempo e volume |

---

## Requisitos Não-Funcionais (Essenciais)

| Pilar | Garantia |
| --- | --- |
| Performance | Respostas rápidas para operações críticas |
| Escalabilidade | Suporte a milhares de usuários e solicitações mensais |
| Disponibilidade | Alta disponibilidade com backup automático |
| Segurança | Autenticação forte, criptografia e proteção OWASP |
| Usabilidade | Interface responsiva, mobile-first |
| Manutenibilidade | Testes automatizados e CI/CD |
| Compliance | LGPD, retenção fiscal e segregação de funções |
