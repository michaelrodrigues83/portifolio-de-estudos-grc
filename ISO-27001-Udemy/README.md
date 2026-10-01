# 📜 Trilha de Segurança da Informação: ISO/IEC 27001 (Udemy)

Este diretório centraliza os registros práticos, análises de conformidade e avaliações de segurança estruturados com base nos controles internacionais da norma **ISO/IEC 27001:2022**.

---

## 🛠️ Laboratório Prático 01: Análise de Lacunas (Gap Analysis) — GRC & SOC

Este projeto documenta o diagnóstico analítico de um cenário corporativo simulado, mapeando vulnerabilidades operacionais e propondo planos de remediação eficientes alinhados às melhores práticas de Governança.

### 🏢 1.0 O que é este Projeto?
Uma simulação prática baseada na resolução de um incidente crítico de segurança em uma organização que não possuía processos consolidados. O objetivo foi realizar uma auditoria interna rápida para identificar falhas organizacionais e técnicas, propondo soluções estruturadas com base nos controles da ISO 27001.

### 🗺️ 2.0 Cenário Analisado & Quebra da Tríade CIA
* **Empresa:** Fabricante de peças automotivas.
* **Incidente Crítico:** Vazamento de dados em massa após um ataque de phishing bem-sucedido.
* **Causa Identificada:** Ausência de uma equipe de SOC estruturada e falta de governança de identidades.
* **Impacto na Tríade CIA:** 
  * 🔴 **Quebra da Confidencialidade:** Dados confidenciais e restritos da organização foram expostos e exfiltrados para agentes maliciosos não autorizados.
  * 🔴 **Quebra da Integridade:** O comprometimento de credenciais administrativas permitiu o acesso não autorizado a sistemas centrais, gerando o risco de adulteração, exclusão ou manipulação de informações corporativas críticas.

---

## 🔍 3.0 Lacunas Encontradas (Gaps) e Planos de Remediação

### 🛑 Problema 1: Falta de Monitoramento Centralizado (SOC)
* **Impacto:** O ataque ocorreu sem que nenhum alerta de segurança fosse disparado ou correlacionado em tempo real.
* **Controle Violado (ISO 27001):** Controle A.8.16 (Monitoramento de Eventos).
* **Solução Proposta:** Implementação de uma ferramenta centralizada de gerenciamento de logs (SIEM) e contratação de serviços de monitoramento contínuo (SOC 24/7).

### 🛑 Problema 2: Credenciais Fracas e Ausência de Segundo Fator (MFA)
* **Impacto:** O invasor obteve acesso aos sistemas administrativos comprometendo uma única senha estática de usuário.
* **Controle Violado (ISO 27001):** Controle A.8.5 (Gerenciamento de Autenticação Segura).
* **Solução Proposta:** Implantação obrigatória de Autenticação de Múltiplos Fatores (MFA) para todos os acessos remotos e privilégios administrativos.

### 🛑 Problema 3: Falta de Conscientização da Equipe
* **Impacto:** Colaboradores internos clicaram em links maliciosos por não saberem identificar vetores clássicos de engenharia social.
* **Controle Violado (ISO 27001):** Controle A.6.3 (Conscientização, Educação e Treinamento em Segurança da Informação).
* **Solução Proposta:** Desenvolvimento de campanhas contínuas de conscientização e testes simulados periódicos de phishing.

---

## 🧠 4.0 Conclusão e Aprendizados
A execução desta Análise de Lacunas consolidou a compreensão de que a Segurança da Informação não se limita a barreiras tecnológicas, mas sim ao equilíbrio entre **Pessoas, Processos e Tecnologia**. Programas eficientes de GRC utilizam os controles da ISO 27001 como um roteiro estratégico para garantir a resiliência operacional do negócio.

---
⚡ *Portfólio em constante andamento. Novas análises de controles serão publicadas conforme o avanço nos módulos da Udemy.*

[⬅️ Voltar para o Portal de GRC](../README.md)
