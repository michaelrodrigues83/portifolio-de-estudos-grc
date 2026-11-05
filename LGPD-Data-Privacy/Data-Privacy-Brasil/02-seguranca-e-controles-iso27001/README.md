# 📂 Módulo 02: Segurança da Informação e Controles Relevantes (ISO 27001)

Neste módulo, estabelecemos as salvaguardas e controles de segurança da informação implementados na **CrediTech Soluções Financeiras S.A.** baseados na norma ISO/IEC 27001, visando a proteção ativa dos dados coletados na esteira de crédito digital.

> ℹ️ A CrediTech é uma empresa **fictícia**, criada para fins de estudo. Prazos e parâmetros técnicos citados são hipóteses do cenário.

## 🎯 Objetivos de Conformidade
* **LGPD:**
  * Art. 46: medidas de segurança, técnicas e administrativas aptas a proteger os dados pessoais de acessos não autorizados, e observadas desde a concepção do serviço até a sua execução.
  * Art. 6º, VII (segurança) e X (responsabilização e prestação de contas).
* **ISO/IEC 27001:2022 (Anexo A):** controles de acesso (A.5.15, A.5.18, A.8.2, A.8.3, A.8.5), mascaramento de dados (A.8.11), criptografia (A.8.24), vulnerabilidades (A.8.8), registro e monitoramento (A.8.15, A.8.16) e backup (A.8.13).

---

## 📑 [Projeto Prático] Controles de Segurança Aplicados à Esteira de Crédito

Para proteger o fluxo massivo de dados (incluindo biometria e dados bancários), estruturamos os seguintes controles técnicos e administrativos, pautados na Tríade CID (Confidencialidade, Integridade e Disponibilidade).

### 1. Política de Controle de Acesso (Confidencialidade)
* **Princípio do Menor Privilégio:** Implementação do modelo RBAC (Role-Based Access Control), com revisão periódica dos acessos (A.5.15 e A.5.18).
* **Mascaramento de Dados:** Analistas de suporte N1 possuem acesso estritamente limitado a dados mascarados (A.8.11).
* **Acesso Técnico:** Desenvolvedores e engenheiros de dados não possuem acesso direto ao ambiente de produção contendo dados biométricos em texto claro. O desenvolvimento e os testes usam dados anonimizados, em ambientes separados da produção (A.8.31 e A.8.33).
* **Acessos Privilegiados:** Contas administrativas com aprovação prévia, uso registrado em log e revisão periódica (A.8.2).
* **Autenticação:** Exigência de duplo fator de autenticação (MFA) em todas as credenciais corporativas (A.8.5).

**Matriz de Perfis de Acesso (RBAC) – exemplo**

| Perfil | Acesso a dados cadastrais | Acesso a score | Acesso a biometria | Ambiente |
|---|---|---|---|---|
| Suporte N1 | Mascarados | Não | Não | Produção (somente leitura) |
| Analista de crédito | Sim | Sim | Não | Produção |
| Engenharia de dados / Desenvolvimento | Anonimizados | Anonimizados | Não | Homologação |
| Segurança (SOC) | Não | Não | Não | Logs e monitoramento |
| Administrador de sistemas | Sob aprovação e com registro | Sob aprovação e com registro | Não | Produção (acesso privilegiado) |

### 2. Criptografia e Proteção dos Dados (Confidencialidade e Integridade)
* **Dados em Trânsito:** Todo o tráfego de dados entre o aplicativo do cliente e os servidores da API ocorre via protocolo seguro TLS 1.3 (A.5.14 e A.8.24).
* **Dados em Repouso:** Os bancos de dados relacionais que armazenam os CPFs, scores e logs de auditoria utilizam criptografia robusta AES-256 bits (A.8.24), com gestão das chaves separada dos dados.
* **Dados Sensíveis (Biometria):** Apenas o *template* biométrico (vetor de características) é armazenado, protegido por criptografia e em base segregada dos dados cadastrais. A imagem original da face é descartada após a extração do template, reduzindo o risco de reconstrução da face em caso de vazamento da base de dados.

### 3. Disponibilidade e Gestão de Vulnerabilidades
* **Monitoramento Ativo:** Varreduras automáticas semanais em busca de portas expostas ou pacotes desatualizados nos servidores (A.8.8).
* **Backup e Continuidade:** Cópias de segurança periódicas e testes de restauração, para garantir a recuperação do serviço (A.8.13).
* **Trilha de Auditoria:** Logs de acesso imutáveis registram toda e qualquer consulta feita por colaboradores aos dados cadastrais dos clientes, garantindo rastreabilidade e apoiando a prestação de contas (A.8.15, A.8.16 e Art. 6º, X da LGPD).

**Ciclo de Correção de Vulnerabilidades**

1. **Identificar:** varreduras automáticas e alertas de fornecedores.
2. **Classificar:** pontuação de severidade (CVSS) e criticidade do ativo afetado.
3. **Priorizar:** ativos expostos e que tratam dados sensíveis vêm primeiro.
4. **Corrigir:** aplicação de patch ou medida compensatória, dentro do prazo da tabela abaixo.
5. **Validar:** nova varredura para confirmar a correção.
6. **Registrar:** evidência da correção, para auditoria.

| Severidade | Prazo de correção (hipótese do cenário) |
|---|---|
| Crítica | Até 7 dias |
| Alta | Até 30 dias |
| Média | Até 90 dias |
| Baixa | No próximo ciclo de manutenção |

---

## 🧭 Matriz de Controles

| Controle da CrediTech | LGPD | ISO/IEC 27001:2022 |
|---|---|---|
| RBAC e menor privilégio | Art. 46 | A.5.15, A.5.18, A.8.3 |
| Mascaramento e anonimização em testes | Art. 46 | A.8.11, A.8.33 |
| MFA e contas privilegiadas | Art. 46 | A.8.5, A.8.2 |
| Criptografia em trânsito e em repouso | Art. 46 | A.8.24, A.5.14 |
| Separação entre desenvolvimento e produção | Art. 46, § 2º | A.8.31 |
| Gestão de vulnerabilidades | Art. 46 | A.8.8 |
| Logs e monitoramento | Art. 6º, X | A.8.15, A.8.16 |
| Backup e restauração | Art. 46 | A.8.13 |

---

## 🚀 Status dos Entregáveis
* [x] **Política de Controle de Acesso (CrediTech):** Regras de privilégio baseadas no princípio do menor privilégio definidas, com matriz de perfis.
* [x] **Plano de Criptografia de Dados:** Diretrizes técnicas para AES-256 e TLS 1.3 estabelecidas.
* [x] **Gestão de Vulnerabilidades:** Ciclo de correção de falhas em ativos de produção desenhado, com prazos por severidade.

---
👉 [Voltar para a página principal do projeto](../README.md)
