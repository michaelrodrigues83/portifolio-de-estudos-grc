# 📂 Módulo 01: Mapeamento de Dados e Inventário de Atividades (RoPA)

Neste módulo, estruturamos o inventário de operações de tratamento de dados pessoais (Registro de Operações de Tratamento - RoPA) da **CrediTech Soluções Financeiras S.A.**, mapeando o ciclo de vida dos dados desde a coleta até o descarte definitivo.

## 🎯 Objetivos de Conformidade
* **LGPD:** Atendimento ao Artigo 37 (obrigação de manter o registro das operações).
* **ISO 27001:** Alinhamento com o controle de Inventário de Ativos e Manipulação de Ativos.

---

## 📑 [Projeto Prático] Registro de Operações de Tratamento (RoPA) - Análise de Crédito

### 1. Processo de Tratamento: Análise Preditiva e Concessão de Crédito Digital
* **Finalidade Principal:** Avaliar o perfil de risco de crédito do solicitante e automatizar a tomada de decisão para aprovação ou recusa de financiamento.
* **Volume Estimado:** Tratamento massivo de dados (escala nacional, plataforma 100% digital).

### 2. Mapeamento e Classificação dos Dados Coletados
* **Dados Pessoais Comuns:** Nome completo, CPF, e-mail, telefone, endereço residencial, profissão e dados bancários para depósito.
* **Dados Geolocalizacionais:** Coleta de geolocalização do dispositivo móvel para mitigação de fraudes e validação de identidade (KYC - Know Your Customer).
* **Dados Pessoais Sensíveis:** Biometria facial coletada no aplicativo para autenticação de segurança e prevenção à fraude de identidade.

### 3. Base Legal Vinculada (Artigos 7º e 11 da LGPD)
* **Dados Comuns (Score e Cadastro):** **Execução de Contrato ou procedimentos preliminares** (Art. 7º, V) e **Legítimo Interesse** (Art. 7º, IX) para cruzamento de dados de mercado.
* **Dados Biométricos (Prevenção à Fraude):** **Garantia da prevenção à fraude e à segurança do titular** (Art. 11, II, "g" da LGPD).

### 4. Ciclo de Vida e Retenção do Dado
* **Armazenamento:** Servidores em nuvem criptografados.
* **Tempo de Retenção:** **5 anos** após o encerramento do contrato (para atendimento à Resolução do Banco Central e Código de Defesa do Consumidor) ou **90 dias** para propostas recusadas por suspeita de fraude.
* **Descarte:** Exclusão lógica com sobreescrita segura de dados e descarte físico dos logs de servidores obsoletos.

---

## 🚀 Status dos Entregáveis
* [x] **Inventário de Dados de RH e Operações (CrediTech):** Fluxo de análise de score de crédito mapeado.
* [x] **Matriz de Classificação de Dados:** Divisão entre dados cadastrais, biométricos e geolocalização documentada.
* [ ] **Mapeamento do Ciclo de Vida do Dado:** Definição das tabelas de temporalidade jurídica (Banco Central/CLT).

---
👉 [Voltar para a página principal do projeto](../README.md)
