# 📊 02. Gestão de Riscos Cibernéticos e Declaração de Aplicabilidade - SoA (Cláusula 6)

**Framework de Referência:** ISO/IEC 27001:2022 (Cláusulas 6.1.2, 6.1.3 e Anexo A) & ISO 31000

A gestão de riscos é o coração da ISO/IEC 27001. Nenhum controle é aplicado sem justificativa baseada em risco real ao negócio.

---

## 1. Metodologia de Avaliação de Riscos (Probabilidade × Impacto)

Os riscos foram classificados em uma matriz 5×5 (escala de 1 a 25), definindo o **Apetite ao Risco** da organização em nível **8 (Baixo/Moderado)**. Todo risco acima de 8 exige plano de tratamento obrigatório.

| ID | Ativo / Processo | Ameaça e Vulnerabilidade Mapeada | Prob. (1-5) | Imp. (1-5) | Nível Inerente | Decisão de Tratamento |
| :--- | :--- | :--- | :---: | :---: | :---: | :--- |
| **RSK-01** | Banco de Dados TMS/WMS | Ataque de *Ransomware* via *phishing* explorando ausência de MFA. | 4 | 5 | **20 (Crítico)** | **Mitigar:** MFA obrigatório, segmentação de rede e backup imutável. |
| **RSK-02** | Sala de Servidores / CCO | Acesso físico não autorizado (*tailgating*) por falha no controle de portaria. | 4 | 5 | **20 (Crítico)** | **Mitigar:** Eclusa física, biometria + crachá e CFTV sem pontos cegos. |
| **RSK-03** | Dados de Motoristas (LGPD) | Vazamento de dados biométricos e rotas por permissões excessivas no banco. | 3 | 5 | **15 (Alto)** | **Mitigar:** Controle RBAC, criptografia AES-256 e logs de auditoria. |
| **RSK-04** | Algoritmo de IA de Rotas | Desvio de decisão (*Data Drift*) ou inserção de dados corporativos em IA pública. | 3 | 4 | **12 (Alto)** | **Mitigar:** Política de IA, *Human-in-the-loop* e bloqueio de IA externa. |

---

## 2. Declaração de Aplicabilidade — SoA (Resumo Executivo)

A **Statement of Applicability (SoA)** documenta quais dos **93 controles do Anexo A (ISO/IEC 27001:2022)** são aplicáveis ao escopo da NexusLog S.A. e o status de implementação:

| Domínio do Anexo A (2022) | Total de Controles | Aplicáveis | Não Aplicáveis | Justificativa Técnica |
| :--- | :---: | :---: | :---: | :--- |
| **5. Controles Organizacionais** | 37 | 35 | 2 | Excluídos apenas controles específicos de desenvolvimento proprietário de software externo. |
| **6. Controles de Pessoas** | 8 | 8 | 0 | **100% aplicáveis:** Triagem pré-contratação, termos de confidencialidade e conscientização contínua. |
| **7. Controles Físicos** | 14 | 14 | 0 | **100% aplicáveis:** Blindagem de perímetros, docas críticas, salas técnicas e custódia de ativos. |
| **8. Controles Tecnológicos** | 34 | 31 | 3 | Excluídos controles de ambientes *mainframe* legados inexistentes na arquitetura em nuvem. |

---

[⬅️ Voltar ao Módulo 02](./README.md) | [🏠 Voltar ao Painel Geral](../README.md)
