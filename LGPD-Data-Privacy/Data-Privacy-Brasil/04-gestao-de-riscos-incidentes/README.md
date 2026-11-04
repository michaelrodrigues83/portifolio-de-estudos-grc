# 📂 Módulo 04: Gestão de Riscos e Resposta a Incidentes

Neste módulo, abordamos a identificação, avaliação e mitigação de riscos associados ao tratamento de dados pessoais, além da estruturação de um Plano de Resposta a Incidentes de Segurança Cibernética na **CrediTech Soluções Financeiras S.A.** em total conformidade com as exigências da ANPD.

## 🎯 Objetivos de Conformidade
* **LGPD:** Atendimento ao Artigo 38 (determinação para elaboração do Relatório de Impacto) e Artigo 48 (comunicação de incidentes de segurança à ANPD e aos titulares).
* **ISO 27001:** Alinhamento com as diretrizes de Gestão de Riscos de Segurança da Informação e Gerenciamento de Incidentes.

---

## 📑 [Projeto Prático] Gestão de Incidentes e Mitigação de Riscos na CrediTech

Para garantir a resiliência operacional da nossa Fintech perante ameaças cibernéticas e auditorias da ANPD, estruturamos os seguintes entregáveis estratégicos:

### 1. Relatório de Impacto à Proteção de Dados Pessoais (RIPD / DPIA)
* **Escopo do Tratamento:** Análise detalhada dos riscos envolvidos na coleta de biometria facial para autenticação e no processamento automatizado de score por IA.
* **Medidas de Mitigação:** Implementação de técnicas de anonimização em ambientes de homologação e isolamento completo das bases de dados em sub-redes privadas (VPC) blindadas.

### 2. Plano de Resposta a Incidentes de Segurança (Vazamentos)
* **Fase de Detecção e Análise:** Monitoramento contínuo de logs via SIEM corporativo para identificar exfiltração de dados cadastrais ou acessos anômalos na esteira de crédito.
* **Fase de Contenção:** Isolamento imediato dos servidores afetados e revogação temporária de credenciais RBAC sob suspeita.
* **Tratamento Jurídico:** Fluxo interno estabelecido para notificação obrigatória à ANPD e aos titulares afetados em até 72 horas úteis caso o incidente gere risco ou dano relevante.

### 3. Formulário de Notificação de Incidente (Padrão ANPD)
* **Documentação Prática:** Modelo pré-configurado contendo a descrição da natureza dos dados afetados, estimativa de titulares impactados, indicação das medidas técnicas de segurança adotadas e plano de contingência para remediar os efeitos do desvio.

---

## 🚀 Status dos Entregáveis
* [x] **Relatório de Impacto (RIPD):** Riscos da esteira de IA mapeados e mitigados com salvaguardas técnicas.
* [x] **Plano de Resposta a Incidentes:** Protocolo de contenção e comunicação de 72 horas estruturado.
* [ ] **Formulário de Notificação ANPD:** Criação do template oficial de envio em andamento.

---
👉 [Voltar para a página principal do projeto](../README.md)
