# 🔄 06. Plano de Continuidade de Negócios e Resiliência (ISO 22301 & Anexo A.5.30)

**Framework de Referência:** ISO/IEC 27001:2022 (Controle A.5.30) & ISO 22301:2019 (SGCN)

Um SGSI completo precisa garantir que a operação crítica sobreviva a desastres físicos, falhas elétricas ou ataques cibernéticos graves sem perda de integridade.

---

## 1. Análise de Impacto nos Negócios (BIA) e Métricas de Recuperação

| Processo Crítico | RTO (Tempo Máximo de Parada) | RPO (Perda Máxima de Dados) | Estratégia de Contingência Implementada |
| :--- | :---: | :---: | :--- |
| **Centro de Controle Operacional (CCO)** | **1 hora** | **15 minutos** | Link redundante via satélite, gerador diesel automático e *failover* em nuvem Multi-AZ. |
| **Sistemas TMS / WMS e Banco de Dados** | **2 horas** | **0 horas (Síncrono)** | Replicação contínua em zona isolada e backups imutáveis (regra 3-2-1-1-0) contra *ransomware*. |
| **Controle de Acesso e Docas Críticas** | **Imediato (0 min)** | **N/A** | Comutação imediata para Procedimento Operacional Padrão (POP) analógico com livro de registro físico e escolta patrimonial. |

---

## 2. Testes de Simulação e Exercícios de Crise

* **Simulados Semestrais de Mesa (*Tabletop Exercises*):** Treinamento prático envolvendo TI, Segurança Patrimonial, Jurídico e Operações simulando cenário de ataque *ransomware* combinado com queda de energia no centro de distribuição.

---

[⬅️ Voltar ao Módulo 02](./README.md) | [🏠 Voltar ao Painel Geral](../README.md)
