# 📂 Módulo 04: Gestão de Riscos e Resposta a Incidentes

Neste módulo, abordamos a identificação, avaliação e mitigação de riscos associados ao tratamento de dados pessoais, além da estruturação de um Plano de Resposta a Incidentes de Segurança Cibernética na **CrediTech Soluções Financeiras S.A.**, em conformidade com a LGPD e com a regulamentação da ANPD.

> ℹ️ A CrediTech é uma empresa **fictícia**, criada para fins de estudo. Prazos internos, níveis de severidade e pontuações de risco citados são hipóteses do cenário.

## 🎯 Objetivos de Conformidade
* **LGPD:**
  * Art. 5º, XVII e Art. 38: Relatório de Impacto à Proteção de Dados Pessoais (RIPD), sua definição e a possibilidade de a ANPD determinar sua elaboração.
  * Art. 48: comunicação de incidentes de segurança à ANPD e aos titulares, regulamentada pela **Resolução CD/ANPD nº 15/2024** (Regulamento de Comunicação de Incidente de Segurança, o RCIS).
  * Art. 6º, VII (segurança) e X (responsabilização e prestação de contas).
* **ISO/IEC 27001:2022:**
  * Cláusulas 6.1.2 e 6.1.3: avaliação e tratamento de riscos de segurança da informação.
  * A.5.24 a A.5.28: gestão de incidentes (planejamento, avaliação, resposta, aprendizado e coleta de evidências).
  * A.6.8: reporte de eventos de segurança. A.8.15 e A.8.16: registro de logs e monitoramento.

---

## 📑 [Projeto Prático] Gestão de Incidentes e Mitigação de Riscos na CrediTech

Para garantir a resiliência operacional da nossa fintech perante ameaças cibernéticas e eventuais auditorias da ANPD, estruturamos os seguintes entregáveis estratégicos:

### 1. Relatório de Impacto à Proteção de Dados Pessoais (RIPD / DPIA)

**Escopo do Tratamento:** Análise dos riscos envolvidos na coleta de biometria facial para autenticação e no processamento automatizado de score por IA (veja os Módulos 01 e 03).

**Estrutura do RIPD**
1. **Identificação:** controlador, encarregado de dados e operadores.
2. **Descrição do tratamento:** natureza, escopo, contexto, finalidade e tipos de dados coletados.
3. **Necessidade e proporcionalidade:** bases legais (Módulo 01) e minimização dos dados.
4. **Metodologia de coleta e de garantia da segurança das informações** (Módulo 02).
5. **Identificação e avaliação dos riscos** aos titulares.
6. **Medidas, salvaguardas e mecanismos de mitigação** adotados e risco residual.
7. **Aprovação** pelo Comitê de GRC e pelo Encarregado, com data de revisão.

**Matriz de Riscos (probabilidade × impacto, escala de 1 a 3)**

| ID | Risco | Prob. | Impacto | Nível inicial | Medidas de mitigação | Risco residual |
|---|---|---|---|---|---|---|
| R1 | Vazamento de templates biométricos | 2 | 3 | Alto (6) | Criptografia, base segregada, VPC privada, MFA e monitoramento via SIEM | Médio (3) |
| R2 | Acesso indevido de colaboradores a dados cadastrais | 2 | 2 | Médio (4) | RBAC, mascaramento de dados e logs de acesso imutáveis | Baixo (2) |
| R3 | Decisão automatizada discriminatória | 2 | 3 | Alto (6) | AIIA, testes de justiça e canal de revisão humana (Módulo 03) | Médio (3) |
| R4 | Retenção de dados além do necessário | 2 | 2 | Médio (4) | Tabela de temporalidade e rotinas de eliminação (Módulo 01) | Baixo (2) |
| R5 | Uso de dados reais em ambiente de homologação | 2 | 2 | Médio (4) | Anonimização e separação entre desenvolvimento e produção | Baixo (2) |
| R6 | Perda do prazo de comunicação de incidente | 2 | 3 | Alto (6) | Plano de resposta, meta interna de triagem e simulados periódicos | Médio (3) |

*Nível = probabilidade × impacto: 1 a 2 (baixo), 3 a 4 (médio), 6 a 9 (alto).*

**Medidas de Mitigação:** anonimização em ambientes de homologação e segmentação das bases de dados em sub-redes privadas (VPC), com isolamento do ambiente de produção.

### 2. Plano de Resposta a Incidentes de Segurança (Vazamentos)

**Papéis**

| Papel | Responsabilidade |
|---|---|
| SOC / Segurança | Detecta, analisa e contém o incidente |
| Encarregado de Dados (DPO) | Avalia o risco aos titulares e conduz a comunicação à ANPD |
| Jurídico | Avalia as obrigações legais e revisa as comunicações |
| Comunicação | Prepara o aviso aos titulares, em linguagem simples |
| Diretoria | Aprova decisões críticas e acompanha o incidente |

**Fases do plano**

1. **Preparação:** plano aprovado, equipes treinadas, simulados periódicos e o formulário interno de comunicação pronto (A.5.24).
2. **Detecção e Análise:** monitoramento contínuo de logs via SIEM corporativo (A.8.15 e A.8.16) para identificar exfiltração de dados cadastrais ou acessos anômalos na esteira de crédito. Exemplos de casos de uso do SIEM: consultas em massa a dados cadastrais, exportações fora do padrão e logins de locais atípicos. Os eventos suspeitos são reportados e classificados (A.6.8 e A.5.25).
3. **Contenção:** isolamento imediato dos servidores afetados e revogação temporária de credenciais RBAC sob suspeita (A.5.26).
4. **Erradicação e Recuperação:** remoção da causa, restauração a partir de backup íntegro e monitoramento reforçado.
5. **Tratamento Jurídico e Comunicação:** avaliação do risco aos titulares e comunicação à ANPD e aos titulares dentro dos prazos abaixo.
6. **Pós-incidente:** análise da causa raiz, medidas corretivas, lições aprendidas (A.5.27) e registro interno de todos os incidentes, inclusive os não comunicados.

**Preservação de Evidências (A.5.28):** logs, imagens de sistemas e registros das decisões são preservados com cadeia de custódia, para a investigação e para eventual auditoria.

**Quando comunicar? (Art. 48 da LGPD e RCIS)**
A comunicação é obrigatória quando o incidente puder acarretar **risco ou dano relevante** aos titulares. Pelo RCIS (Art. 5º), isso ocorre quando o incidente pode afetar significativamente interesses e direitos fundamentais dos titulares e envolve, entre outros critérios, dados pessoais sensíveis, dados de crianças, adolescentes ou idosos, dados financeiros, dados de autenticação em sistemas, dados protegidos por sigilo ou dados em larga escala.

> No cenário da CrediTech, um vazamento da esteira de crédito envolve dados **sensíveis (biometria)**, **financeiros** e em **larga escala**. Portanto, a comunicação é obrigatória.

**Prazos de Comunicação (Resolução CD/ANPD nº 15/2024)**

| Etapa | Prazo | Contagem |
|---|---|---|
| Comunicar a ANPD e os titulares afetados | **3 dias úteis** | A partir do conhecimento, pelo controlador, de que o incidente afetou dados pessoais |
| Complementar a comunicação, se faltarem informações | **20 dias úteis** | A partir da data da comunicação |
| Declarar à ANPD que os titulares foram avisados, com os meios utilizados | **3 dias úteis** | A partir do fim do prazo de comunicação aos titulares |

* O prazo conta a partir do **conhecimento de que o incidente afetou dados pessoais**, e não da conclusão da investigação. A comunicação preliminar pode ser feita com informações incompletas e complementada depois.
* Os prazos são contados em **dias úteis**, e não em horas. (A referência de 72 horas é do GDPR europeu.)
* A CrediTech é uma empresa de grande porte, então não se aplica a contagem em dobro prevista para agentes de tratamento de pequeno porte.
* **Meta interna (hipótese do cenário):** triagem e decisão de comunicar em até 24 horas após a detecção, para preservar a margem do prazo legal.

### 3. Formulário de Notificação de Incidente

Modelo interno pré-configurado, usado para reunir as informações antes do envio pelo formulário de comunicação de incidente de segurança (CIS) disponibilizado pela ANPD. Os campos seguem o conteúdo exigido pelo Art. 48, § 1º da LGPD.

| Campo | Conteúdo |
|---|---|
| Identificação | Controlador, Encarregado de Dados e contatos |
| Datas | Data e hora do incidente e da ciência pelo controlador |
| Natureza e categoria dos dados | Descrição dos dados afetados (cadastrais, financeiros, biométricos etc.) |
| Titulares afetados | Número de titulares e categorias vulneráveis (crianças, adolescentes, idosos) |
| Medidas de segurança adotadas | Medidas técnicas e administrativas que já existiam (Módulo 02) |
| Riscos e impactos | Possíveis consequências aos titulares (fraude, discriminação, dano financeiro) |
| Medidas de mitigação | Ações adotadas ou previstas para reverter ou mitigar os efeitos |
| Motivos de eventual demora | Justificativa, se a comunicação passar do prazo de 3 dias úteis |
| Comunicação aos titulares | Meio utilizado, data e cópia do aviso |
| Tipo de comunicação | Preliminar ou complementar |

---

## 🧭 Matriz de Controles

| Controle da CrediTech | LGPD / Regulamentação | ISO/IEC 27001:2022 |
|---|---|---|
| RIPD e matriz de riscos | Art. 5º, XVII e Art. 38 | Cláusulas 6.1.2 e 6.1.3 |
| Plano de resposta a incidentes | Art. 48 e RCIS | A.5.24, A.5.25, A.5.26 |
| Monitoramento e detecção via SIEM | Art. 46 | A.8.15, A.8.16, A.6.8 |
| Preservação de evidências | Art. 6º, X | A.5.28 |
| Lições aprendidas e melhoria | Art. 6º, X | A.5.27 |
| Comunicação à ANPD e aos titulares | Art. 48 e Resolução CD/ANPD nº 15/2024 | A.5.26 |

---

## 🚀 Status dos Entregáveis
* [x] **Relatório de Impacto (RIPD):** Estrutura, matriz de riscos e riscos residuais definidos.
* [x] **Plano de Resposta a Incidentes:** Fases, papéis, critérios de comunicação e prazos conforme a Resolução CD/ANPD nº 15/2024.
* [x] **Formulário de Notificação:** Modelo interno com os campos do Art. 48, § 1º da LGPD, pronto para apoiar o envio à ANPD.

---
👉 [Voltar para a página principal do projeto](../README.md)
