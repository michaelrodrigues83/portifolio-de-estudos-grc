# 📈 Análise de Impacto de Negócios (BIA) em Cenário de Isolamento de Rede Hospitalar Total
**Frameworks de Referência:** ISO 22301:2019 (Segurança e Resiliência) & NIST SP 800-34 Rev. 1 (Contingency Planning)

Este documento estabelece a Análise de Impacto de Negócios (BIA) para o **Alpha Health Group S.A.** operando em condições de degradação severa de infraestrutura: indisponibilidade crônica da internet global (Ataque Zero-Day de Infraestrutura) e colapso energético regional parcial (Efeitos colaterais do Super El Niño).

---

## 1. Classificação de Processos Críticos e Limites de Tolerância

Em condições normais, o ecossistema de saúde depende de validação síncrona em nuvem para acessar prontuários e históricos clínicos. Sob isolamento de rede, os parâmetros de tempo de recuperação foram reajustados para garantir a soberania das unidades de pronto atendimento locais e a manutenção do suporte à via.

### A. Processo: Triagem e Admissão de Pacientes (Pronto-Socorro)
*   **Criticidade:** Mapeado como **Processo de Missão Crítica (MCR)**.
*   **RTO Isolado (Recovery Time Objective):** **2 horas.** Tempo máximo aceitável para que as unidades ativem os servidores de borda locais (*Edge Servers*) e iniciem a visualização de leitos e históricos clínicos sem comunicação central.
*   **RPO Isolado (Recovery Point Objective):** **24 horas.** Limite tolerável de perda de dados de novas admissões e evoluções clínicas locais. Os logs offline devem ser persistidos em cache local redundante a cada fechamento de turno médico.
*   **MTPD (Maximum Tolerable Period of Disruption):** **12 horas.** Período máximo em que a unidade hospitalar consegue operar de forma isolada em modo digital local antes que o atraso na sincronização de prontuários complexos comece a gerar riscos sistêmicos ao fluxo de pacientes.

### B. Processo: Dispensação de Medicamentos Controlados (Farmácia Central)
*   **Criticidade:** Alta.
*   **RTO Isolado:** **1 hora.** Ativação da base de dados estática local para consulta de alergias e restrições de pacientes antes da entrega de fármacos.
*   **RPO Isolado:** **0 horas.** Exigência de integridade absoluta do último estado conhecido das prescrições médicas antes do isolamento.

---

## 2. Estratégias de Recuperação e Redundância

Para cumprir os prazos do BIA sem o suporte de redes WAN, a governança de TI do Alpha Health Group S.A. adota as seguintes contramedidas:

1.  **Soberania de Dados de Borda (Edge Autonomy):** Cada complexo hospitalar mantém um servidor local sincronizado em condições normais. Em isolamento, o servidor local torna-se a *Autoridade Única de Prontuários* para aquela zona geográfica.
2.  **Trava Humana na Triagem (Teto de Risco):** Para mitigar o risco de decisões incorretas do algoritmo desconectado, é ativada a validação humana obrigatória para casos de alta gravidade (Protocolo de Manchester).

---

## 3. Critérios de Ativação do Plano de Continuidade (PCN)

O Gatilho de Ativação (*Trigger*) ocorre quando:
*   A perda de conectividade com a nuvem central do Alpha Health Group persistir por mais de **10 minutos contínuos** sem resposta dos links redundantes.
*   Houver confirmação física ou lógica de falha generalizada nos roteadores de infraestrutura locais.

---
[⬅️ Voltar ao Módulo de Resiliência](./README.md) | [🏡 Voltar ao Painel Geral](../README.md)
