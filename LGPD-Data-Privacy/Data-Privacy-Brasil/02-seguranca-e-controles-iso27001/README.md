# 📂 Módulo 02: Segurança da Informação e Controles Relevantes (ISO 27001)

Neste módulo, estabelecemos as salvaguardas e controles de segurança da informação implementados na **CrediTech Soluções Financeiras S.A.** baseados na norma ISO/IEC 27001, visando a proteção ativa dos dados coletados na esteira de crédito digital.

## 🎯 Objetivos de Conformidade
* **LGPD:** Atendimento ao Artigo 46 (medidas de segurança, técnicas e administrativas aptas a proteger os dados de acessos não autorizados).
* **ISO 27001:** Alinhamento com os controles de Controle de Acesso, Criptografia e Segurança nas Operações.

---

## 📑 [Projeto Prático] Controles de Segurança Aplicados à Esteira de Crédito

Para proteger o fluxo massivo de dados (incluindo biometria e dados bancários), estruturamos os seguintes controles técnicos e administrativos pautados na Tríade CID:

### 1. Política de Controle de Acesso (Confidencialidade)
* **Princípio do Menor Privilégio:** Implementação do modelo RBAC (Role-Based Access Control). Analistas de suporte N1 possuem acesso estritamente limitado a dados mascarados. 
* **Acesso Técnico:** Desenvolvedores e engenheiros de dados não possuem acesso direto ao ambiente de produção contendo dados biométricos em texto claro, mitigando riscos internos.
* **Autenticação:** Exigência de duplo fator de autenticação (MFA) em todas as credenciais corporativas.

### 2. Criptografia e Proteção dos Dados (Integridade)
* **Dados em Trânsito:** Todo o tráfego de dados entre o aplicativo do cliente e os servidores da API ocorre via protocolo seguro TLS 1.3.
* **Dados em Repouso:** Os bancos de dados relacionais que armazenam os CPFs, scores e logs de auditoria utilizam criptografia robusta AES-256 bits.
* **Dados Sensíveis (Biometria):** Vetores de características biométricas são hashificados individualmente, impossibilitando a reconstrução reversa da face do cliente em caso de vazamento da base de dados.

### 3. Gestão de Vulnerabilidades (Disponibilidade e Resiliência)
* **Monitoramento Ativo:** Varreduras automáticas semanais em busca de portas expostas ou pacotes desatualizados nos servidores.
* **Trilha de Auditoria:** Logs de acesso imutáveis registram toda e qualquer consulta feita por colaboradores aos dados cadastrais dos clientes, garantindo a rastreabilidade exigida pela ANPD.

---

## 🚀 Status dos Entregáveis
* [x] **Política de Controle de Acesso (CrediTech):** Regras de privilégio baseadas no princípio do menor privilégio definidas.
* [x] **Plano de Criptografia de Dados:** Diretrizes técnicas para AES-256 e TLS 1.3 estabelecidas.
* [ ] **Gestão de Vulnerabilidades:** Desenho do ciclo de correção de falhas em ativos de produção.

---
👉 [Voltar para a página principal do projeto](../README.md)
