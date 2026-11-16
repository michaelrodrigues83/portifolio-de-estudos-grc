# 🤖 05. Extensão de Inovação: Governança de IA Corporativa (ISO/IEC 42001)

**Framework de Referência:** ISO/IEC 42001:2023 (SGIA) & LGPD (Art. 20 — Revisão de Decisões Automatizadas)

A *NexusLog S.A.* utiliza algoritmos de Inteligência Artificial para otimização de rotas e análise preditiva de risco operacional. Para evitar decisões discriminatórias ou vazamento de dados, o SGSI incorpora diretrizes de governança de IA.

---

## 1. Avaliação de Impacto de IA (AIIA) e Mitigação de Vieses

* **Escopo da IA Auditada:** Modelo preditivo de alocação de rotas e classificação de risco de sinistro em transportes de carga crítica.
* **Riscos Mapeados:** Viés algorítmico penalizando motoristas injustamente por fatores externos (trânsito severo ou clima) e inserção acidental de dados confidenciais de clientes em ferramentas públicas de IA generativa.
* **Controles Aplicados:**
  * **Política de Uso Aceitável de IA:** Proibição técnica (via proxy/DLP) de envio de contratos, planilhas de clientes ou códigos internos para IAs públicas externas.
  * **Supervisão Humana (*Human-in-the-loop*):** Nenhuma penalidade administrativa ou bloqueio de motorista ocorre por decisão 100% automatizada. Todo alerta gerado pela IA passa por revisão obrigatória de um gestor operacional, assegurando o **Art. 20 da LGPD**.
  * **Auditoria de Dados de Treinamento:** Validação periódica da qualidade e integridade das bases de dados (*Data Lineage*) que alimentam os modelos locais.

---

[⬅️ Voltar ao Módulo 02](./README.md) | [🏠 Voltar ao Painel Geral](../README.md)
