# 📋 Procedimentos Operacionais Padrão (POPs) Analógicos e Gestão de Crise Local
**Frameworks de Referência:** ISO 22301:2019 (Operação de Continuidade) & Diretrizes de Resposta a Incidentes

Este documento estabelece as rotinas manuais de contingência para as agências físicas do **Apex Bank S.A.** durante o isolamento total de conectividade sistêmica (Ataque Zero-Day) e estresse de infraestrutura regional (Super El Niño).

---

## 1. Ativação do Modo de Operação Desconectada (Air-Gapped)

Imediatamente após o gatilho de activation do Plano de Continuidade (15 minutos sem rede WAN), a equipe de segurança e TI local deve realizar os seguintes passos:

1.  **Isolamento de Rede Físico:** Desconexão física dos cabos de fibra ótica de uplink dos roteadores de borda para evitar qualquer infecção lateral do *Zero-Day* caso a rede oscile.
2.  **Inicialização do Servidor de Borda:** Ativação do servidor local em modo *Stand-Alone*, carregando a última base de dados de saldos disponível (Snapshot imutável das últimas 24 horas).
3.  **Habilitação do Log Local Histórico:** Inicialização de gravação local redundante (armazenamento físico conectado diretamente e fichas de controle manual de papel para dupla checagem).

---

## 2. Triagem Manual de Incidentes e Controle de Acessos
*Controles adaptados com base em práticas rigorosas de segurança patrimonial e mitigação de vulnerabilidades.*

### A. Fluxo de Controle de Acesso Físico Emergencial
*   **Perímetro Externo:** Bloqueio das portas automáticas de vidro/giratórias por falta de energia central. Ativação do acesso controlado manual pela equipe de vigilância técnica.
*   **Controle de Ocupação:** Limitação estrita de clientes dentro do estabelecimento para evitar tumultos decorrentes do pânico sistêmico (máximo de 5 clientes por vez próximos aos caixas).
*   **Identificação Física:** Obrigatoriedade de preenchimento do livro de registro físico de GRC para cada entrada na sala de contingência, coletando nome, CPF, RG e assinatura com caneta esferográfica.

### B. Protocolo de Atendimento e Saque Emergencial (Teto de Contingência)
Para garantir a subsistência da comunidade local frente ao cenário de calamidade sem gerar colapso financeiro por fraude, o caixa operará sob as seguintes diretrizes:

[Cliente Apresenta Documento] ──> [Gerente Consulta Base Local] ──> [Registro em Livro Físico] ──> [Liberation do Dinheiro]

*   **Validação de Identidade:** O cliente deve apresentar documento original com foto. O gerente da agência cross-referenciará os dados com a base estática do servidor de borda local.
*   **Teto Emergencial:** Fixado o limite máximo de saque de **R$ 1.000,00 por CPF** a cada 48 horas durante o período de isolamento.
*   **Assinatura de Termo de Ciência:** O correntista assinará um recibo físico de débito em contingência. O documento será arquivado em malote de segurança física para posterior conciliação bancária quando a internet for restabelecida.

---

## 3. Custódia Física de Ativos Críticos e Backups

*   **Mídias de Backup Locais:** Os logs de transações gerados offline nas últimas 24 horas devem ser exportados para um HD externo criptografado de forma local (padrão AES-256).
*   **Proteção do Malote:** Este dispositivo deve ser armazenado fisicamente dentro do cofre central da agência, sob dupla custódia (Gerente Geral + Chefe de Segurança), blindado contra variações térmicas extremas decorrentes de falhas de ar-condicionado causadas pelo El Niño.

---
[⬅️ Voltar ao Módulo de Resiliência](./README.md) | [🏡 Voltar ao Painel Geral](../README.md)
