# 🏢 Estudo de Caso Final: Plano de Auditoria de Contingência por Isolamento de Infraestrutura Crítica de Saúde (Alpha Health Group S.A.)
**Framework Integrado:** ISO 22301:2019, ISO/IEC 27001:2022, ISO/IEC 42001:2023, LGPD (Dados Sensíveis) e NIST SP 800-34

**Status do Documento:** RELATÓRIO TÉCNICO DE AUDITORIA INTERNA DE GRC
**Classificação:** Confidencial / Uso Restrito do Comitê de Resiliência Hospitalar
**Autor:** Michael Hernandes Rodrigues (Analista de GRC)

---

## 1. Diretriz do Cenário de Isolamento Total (Cisne Negro)
Este documento estabelece o plano estratégico de GRC para o **Alpha Health Group S.A.** diante de cenários extremos de perda total de conectividade externa em suas unidades de pronto atendimento. O plano responde a duas causas geradoras de isolamento sistêmico:

1. **Impacto Climático Absoluto (Super El Niño):** Tempestades severas destruindo backbones físicos de fibra ótica terrestres e interrompendo as comunicações WAN da rede de saúde com data centers centralizados.
2. **Ataque Zero-Day de Infraestrutura:** Exploração de vulnerabilidade em switches de borda que cause o isolamento lógico imediato das unidades hospitalares da internet externa.

**O Problema Auditado:** O complexo hospitalar encontra-se com fornecimento elétrico interno ativo (suportado por geradores a diesel locais), porém **completamente ilhado ciberneticamente**. Não há acesso a prontuários em nuvem, sistemas de prescrição eletrônica centralizados ou contato digital entre alas e unidades.

---

## 2. Inventário de Ativos Críticos e Classificação (ISO/IEC 27001)

Para garantir a proteção adequada de vidas e dados sensíveis durante o isolamento, os ativos locais do hospital foram classificados na tríade de segurança (Escala de 1 a 3, onde 3 é crítico):

| Ativo de Informação | Tipo de Ativo | C | I | D | Classificação de Segurança / Regulamentação |
| :--- | :--- | :---: | :---: | :---: | :--- |
| **Servidor de Borda (Triage Edge AI)** | Hardware / S.O. Local | 3 | 3 | 3 | Altamente Confidencial (ISO 42001) |
| **Banco de Prontuários Locais (Snapshot)** | Dado Lógico Sensível | 3 | 3 | 2 | Dados Médicos Sensíveis (Art. 5º, LGPD) |
| **Logs de Dispensação de Medicamentos** | Registro Digital WORM | 2 | 3 | 3 | Confidencial / Rastreabilidade RDC Anvisa |
| **Prontuários e Fichas de Triagem Físicas** | Físico (Papel) | 3 | 3 | 2 | Restrito / Retenção Obrigatória |

---

## 3. Matriz de Controles e Status de Conformidade de Crise

A tabela abaixo detalha os controles internacionais auditados durante o exercício de simulação e o nível de eficácia operacional atingido em ambiente médico desconectado:

| Framework | Código do Controle | Descrição do Objetivo | Status Operacional | Eficácia |
| :--- | :--- | :--- | :--- | :---: |
| **ISO 22301** | Controle 8.4.4 | Ativação do Plano de Continuidade (RTO Hospitalar < 2h). | Ativado em 01h15m via Servidores de Borda. | **100%** |
| **NIST 800-34** | CP-9 (Information Backup) | Acesso local a snapshots imutáveis de prontuários. | Executado localmente via cache local seguro. | **100%** |
| **ISO 27001** | Controle A.7.4 | Proteção física da sala de servidores e farmácia central. | Comutado para Fail-Secure (Acesso por Chaves). | **100%** |
| **ISO 27001** | Controle A.8.20 | Isolamento lógico de redes internas (*Air-Gapping*). | Redes de IoT médicas isoladas da internet externa. | **100%** |
| **ISO 42001** | Objetivo B.7.2 | Mitigação de desvios algorítmicos (*Data Drift*). | Ativada a trava *Human-in-the-loop* de triagem. | **98%** |
| **LGPD** | Art. 20 (Direitos) | Garantia de revisão humana para decisões da IA. | Fluxo manual de atendimento médico em contingência. | **100%** |

---

## 4. Detalhamento da Resolução do GRC por Pilar

Na ausência completa de rede externa, a governança hospitalar migra instantaneamente para o modo **Autônomo Local (Offline-First)**, operando sob salvaguardas regulatórias rígidas:

### A. Ativação de Soberania de Borda (ISO 22301 / NIST SP 800-34)
*   **Ação de Resolução:** O comitê de GRC e a TI ativam o cache local do servidor de borda. Os médicos passam a acessar os históricos clínicos dos pacientes internados através de snapshots atualizados nas últimas 24 horas, rodando em rede local fechada.
*   **Métricas Atendidas:** Restabelecimento do sistema de triagem e visualização de leitos em 1 hora e 15 minutos, cumprindo o RTO agressivo exigido para suporte à vida.

### B. Protocolos de Contingência e Custódia de Dados Sensíveis (ISO/IEC 27001)
*   **Ação de Resolução:** Com a perda de autenticação central em nuvem, o controle de acesso lógico é substituído por Procedimentos Operacionais Padrão (POPs) analógicos. A entrada nas UTIs, farmácias de medicamentos controlados e salas de servidores exige assinatura física em livro de registros de GRC.
*   **Métricas Atendidas:** Novas admissões e evoluções clínicas são registradas manualmente em formulários de papel autocopiativos de contingência. Os prontuários físicos são catalogados e transportados em malotes de segurança física sob custódia direta do Diretor Clínico e do Chefe de Segurança Patrimonial, evitando perdas ou acessos não autorizados.

### C. Ética e Salvaguardas em IA de Triagem e Privacidade (ISO/IEC 42001 & LGPD)
*   **Análise de Risco de IA:** O hospital utiliza uma IA local (*Edge AI*) para classificação de risco de pacientes no pronto-socorro. Diante do estresse do cenário de catástrofe (aumento repentino de traumas devido à tempestade do El Niño), o algoritmo sofre com desvios de dados (*data drift*), elevando o risco de alucinações e erros na priorização de atendimento.
*   **Ação de Resolução:** Aplicação imediata da diretriz *Human-in-the-loop*. Fica revogada qualquer decisão automatizada da IA para classificação de risco de pacientes (Protocolo de Manchester). O algoritmo funciona estritamente em modo consultivo, e a decisão final de triagem passa a ser obrigatoriamente referendada por um enfermeiro ou médico plantonista, assegurando o direito de revisão humana de dados sensíveis de saúde previsto no Art. 20 da LGPD.

---

## 5. Conclusão da Auditoria Interna e Recomendações
O teste de estresse provou que o **Alpha Health Group S.A.** possui uma governança de GRC resiliente e focada na proteção da vida humana e da privacidade. A arquitetura descentralizada manteve a integridade das operações médicas essenciais e a confidencialidade dos dados clínicos sensíveis, mesmo sob isolamento digital e físico extremo.

### Próximas Ações de Melhoria Contínua (Sprints de GRC):
1. Homologar exercícios de simulação de blecaute de rede WAN em ambiente hospitalar a cada quadrimestre.
2. Garantir redundância física de baterias (Nobreaks hospitalares de Grau Médico) com autonomia mínima de 12 horas para manter os servidores de Borda e equipamentos de suporte à vida operando antes do acionamento dos geradores a diesel.

---
[Subir ao Topo](#-estudo-de-caso-final-plano-de-auditoria-de-contingência-por-isolamento-de-infraestrutura-crítica-de-saúde-alpha-health-group-sa) | [⬅️ Voltar ao Módulo de Resiliência](./README.md) | [🏡 Voltar ao Painel Geral](../README.md)
