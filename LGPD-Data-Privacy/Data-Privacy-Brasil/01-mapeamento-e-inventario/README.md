# 📂 Módulo 01: Mapeamento de Dados e Inventário de Atividades (RoPA)

Neste módulo, estruturamos o inventário de operações de tratamento de dados pessoais (Registro de Operações de Tratamento - RoPA) da **CrediTech Soluções Financeiras S.A.**, mapeando o ciclo de vida dos dados desde a coleta até o descarte definitivo.

> ℹ️ A CrediTech é uma empresa **fictícia**, criada para fins de estudo. Prazos, políticas internas e parceiros citados são hipóteses do cenário.

## 🎯 Objetivos de Conformidade
* **LGPD:**
  * Art. 37: obrigação de manter o registro das operações de tratamento.
  * Art. 16: eliminação dos dados após o término do tratamento, com as hipóteses de conservação.
* **ISO/IEC 27001:2022 (Anexo A):**
  * **A.5.9** Inventário de informações e outros ativos associados.
  * **A.5.12** Classificação da informação e **A.5.13** Rotulagem da informação.
  * **A.5.34** Privacidade e proteção de dados pessoais (PII).
  * **A.5.33** Proteção de registros, **A.8.10** Exclusão de informações e **A.7.14** Descarte seguro de equipamentos.

---

## 📑 [Projeto Prático] Registro de Operações de Tratamento (RoPA) - Análise de Crédito

### 1. Processo de Tratamento: Análise Preditiva e Concessão de Crédito Digital
* **Controlador:** CrediTech Soluções Financeiras S.A.
* **Finalidade Principal:** Avaliar o perfil de risco de crédito do solicitante e automatizar a tomada de decisão para aprovação ou recusa de financiamento.
* **Titulares:** Solicitantes de crédito e clientes da plataforma.
* **Volume Estimado:** Tratamento massivo de dados (escala nacional, plataforma 100% digital).
* **Operador:** Provedor de infraestrutura em nuvem (armazenamento e processamento).

### 2. Mapeamento e Classificação dos Dados Coletados
* **Dados Pessoais Comuns:** Nome completo, CPF, e-mail, telefone, endereço residencial, profissão e dados bancários para depósito.
* **Dados Geolocalizacionais:** Coleta de geolocalização do dispositivo móvel para mitigação de fraudes e validação de identidade (KYC - Know Your Customer).
* **Dados Pessoais Sensíveis:** Biometria facial coletada no aplicativo para autenticação de segurança e prevenção à fraude de identidade (Art. 5º, II da LGPD).

**Matriz de Classificação (ISO/IEC 27001 - A.5.12 e A.5.13)**

| Categoria de dado | Exemplos | Nível de classificação | Rotulagem |
|---|---|---|---|
| Cadastrais | Nome, CPF, e-mail, telefone, endereço | Confidencial | `CONFIDENCIAL` |
| Financeiros | Dados bancários, renda, score | Confidencial | `CONFIDENCIAL` |
| Geolocalização | Localização do dispositivo | Confidencial | `CONFIDENCIAL` |
| Biométricos (sensíveis) | Template de biometria facial | Restrito | `RESTRITO - SENSÍVEL` |

### 3. Base Legal Vinculada (Artigos 7º e 11 da LGPD)
* **Dados Comuns (Cadastro):** **Execução de contrato ou procedimentos preliminares** (Art. 7º, V).
* **Dados Comuns (Score):** **Proteção do crédito** (Art. 7º, X), base específica para a análise de risco de crédito.
* **Dados Comuns (Cruzamento de dados de mercado):** **Legítimo interesse** (Art. 7º, IX), com teste de proporcionalidade (LIA) documentado.
* **Dados Biométricos (Prevenção à Fraude):** **Garantia da prevenção à fraude e à segurança do titular, nos processos de identificação e autenticação de cadastro** (Art. 11, II, "g").

### 4. Ciclo de Vida e Retenção do Dado
* **Armazenamento:** Servidores em nuvem com dados criptografados em repouso e em trânsito.
* **Retenção:** Veja a tabela de temporalidade abaixo.
* **Descarte:** Eliminação lógica com sobrescrita segura (A.8.10) e destruição segura de mídias de servidores obsoletos (A.7.14).

**Tabela de Temporalidade (versão inicial)**

| Dado / Situação | Prazo de retenção | Fundamento | Observação |
|---|---|---|---|
| Dados cadastrais e operações de contratos encerrados | 5 anos após o término da relação | Art. 16, I da LGPD (obrigação legal ou regulatória), Lei nº 9.613/1998 (PLD/FT) e prazo prescricional do CDC (art. 27) | Prazo a confirmar com a regulamentação aplicável do Banco Central |
| Propostas recusadas por suspeita de fraude | 90 dias | Política interna da CrediTech | Definição do cenário fictício |
| Logs de acesso aos dados dos clientes | Prazo definido pela política de logs | A.8.15 (Registro de logs) | A detalhar no Módulo 02 |

---

## 🔗 Conexão com os Demais Módulos
* **Módulo 02:** controles de segurança aplicados aos dados mapeados aqui.
* **Módulo 03:** governança da decisão automatizada de crédito.
* **Módulo 04:** RIPD e plano de resposta a incidentes, que dependem deste inventário.

---

## 🚀 Status dos Entregáveis
* [x] **Inventário de Dados de Operações (CrediTech):** Fluxo de análise de score de crédito mapeado.
* [x] **Matriz de Classificação de Dados:** Divisão entre dados cadastrais, financeiros, biométricos e geolocalização documentada.
* [ ] **Mapeamento do Ciclo de Vida do Dado:** 🔄 Em andamento. Tabela de temporalidade inicial criada, com prazos a validar junto à regulamentação do Banco Central.

---
👉 [Voltar para a página principal do projeto](../README.md)
