# 📋 Procedimentos Operacionais Padrão (POPs) Analógicos e Gestão de Crise Local
**Frameworks de Referência:** ISO 22301:2019 (Operação de Continuidade) & Diretrizes de Resposta a Incidentes Hospitalares

Este documento estabelece as rotinas manuais de contingência para as unidades do **Alpha Health Group S.A.** durante o isolamento total de conectividade sistêmica (Ataque Zero-Day) e estresse de infraestrutura regional (Super El Niño).

---

## 1. Ativação do Modo de Operação Desconectada (Air-Gapped)

Imediatamente após o gatilho de ativação do Plano de Continuidade (10 minutos sem rede WAN), a equipe de segurança e TI hospitalar local deve realizar os seguintes passos:

1.  **Isolamento de Rede Físico:** Desconexão física dos cabos de rede externa dos switches centrais para evitar qualquer contaminação lateral das redes IoT médicas (monitores cardíacos, bombas de infusão).
2.  **Inicialização do Servidor de Borda:** Ativação do servidor local em modo *Stand-Alone*, carregando a última base de dados de prontuários disponível (Snapshot das últimas 24 horas).
3.  **Habilitação do Livro de Evolução Clínica:** Distribuição de formulários físicos de prontuário de contingência para as equipes de enfermagem.

---

## 2. Triagem Manual de Incidentes e Controle de Acessos

### A. Fluxo de Controle de Acesso Físico Emergencial
*   **Perímetro Externo:** Bloqueio das portas eletrônicas das alas de isolamento e salas de servidores. Ativação do acesso controlado manual pela equipe de vigilância técnica.
*   **Controle de Fluxo no Pronto-Socorro:** Limitação estrita de acompanhantes nas salas de triagem para evitar tumultos decorrentes do pânico sistêmico ou falta de luz na região.
*   **Identificação Física:** Obrigatoriedade de preenchimento do livro de registro físico de GRC para cada entrada na sala de medicamentos controlados e servidores, coletando nome, registro profissional (CRM/COREN) e assinatura.

### B. Protocolo de Atendimento e Triagem de Contingência (Trava de Segurança)
Para garantir a continuidade dos atendimentos de emergência sem gerar erros graves de medicação ou diagnóstico por falta de dados históricos, a recepção e o corpo clínico operarão sob as seguintes diretrizes:

*   **Validação de Identidade e Alergias:** O paciente (ou responsável) deve apresentar documento de identificação. O enfermeiro cross-referenciará os dados com a base estática do servidor de borda local para checar alergias graves crônicas.
*   **Registro de Evolução Clínica:** Todas as medicações ministradas e procedimentos realizados devem ser anotados obrigatoriamente no formulário de papel autocopiativo de contingência.
*   **Dupla Validação de Receitas:** Nenhuma medicação controlada sai da farmácia do hospital sem receita assinada fisicamente em duas vias pelo médico plantonista, com carimbo e CRM legíveis.

---

## 3. Custódia Física de Ativos Críticos e Backups

*   **Prontuários Físicos de Contingência:** Todos os formulários de papel preenchidos durante o apagão devem ser arquivados em um malote de segurança física lacrado ao fim do plantão.
*   **Proteção do Malote:** O malote deve ser armazenado temporariamente dentro do cofre da administração hospitalar, sob dupla custódia (Diretor Clínico + Chefe de Segurança), protegido contra inundações ou umidade extrema decorrentes das falhas de infraestrutura do El Niño.

---
[⬅️ Voltar ao Módulo de Resiliência](./README.md) | [🏡 Voltar ao Painel Geral](../README.md)
