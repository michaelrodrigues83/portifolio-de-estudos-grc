# 📈 Análise de Impacto de Negócios (BIA) em Cenário de Isolamento de Rede Total
**Frameworks de Referência:** ISO 22301:2019 (Segurança e Resiliência) & NIST SP 800-34 Rev. 1 (Contingency Planning)

Este documento estabelece a Análise de Impacto de Negócios (BIA) para o **Apex Bank S.A.** operando em condições de degradação severa de infraestrutura: indisponibilidade crônica da internet global (Ataque Zero-Day) e colapso energético regional parcial (Efeitos colaterais do Super El Niño).

---

## 1. Classificação de Processos Críticos e Limites de Tolerância

Em condições normais, os sistemas bancários dependem de validação síncrona em nuvem. Sob isolamento de rede, os parâmetros de tempo de recuperação foram reajustados para garantir a soberania das agências físicas e a manutenção da ordem civil (saques de emergência para compra de suprimentos).

### A. Processo: Fornecimento de Numerário (Saques Emergenciais em Espécie)
*   **Criticidade:** Mapeado como **Processo de Missão Crítica (MCR)**.
*   **RTO Isolado (Recovery Time Objective):** **4 horas.** Tempo máximo aceitável para que as agências chave ativem os servidores de borda locais (*Edge Servers*) e iniciem o atendimento manual/local sem comunicação central.
*   **RPO Isolado (Recovery Point Objective):** **24 horas.** Limite tolerável de perda de dados de transações locais. Os logs de saques offline devem ser persistidos localmente em mídias físicas imutáveis a cada fechamento de turno.
*   **MTPD (Maximum Tolerable Period of Disruption):** **72 horas.** Período máximo em que a agência consegue operar de forma isolada antes que o estoque físico de papel-moeda se esgote ou ocorram falhas de conciliação insolúveis.

### B. Processo: Custódia e Validação de Saldos Locais
*   **Criticidade:** Alta.
*   **RTO Isolado:** **2 horas.** Ativação da base de dados estática local (último snapshot íntegro antes do ataque Zero-Day).
*   **RPO Isolado:** **0 horas.** Exigência de integridade absoluta do último estado conhecido dos saldos dos correntistas locais antes do isolamento.

---

## 2. Estratégias de Recuperação e Redundância

Para cumprir os prazos do BIA sem o suporte de redes WAN, a governança de TI do Apex Bank S.A. adota as seguintes contramedidas:

1.  **Soberania dos Dados de Borda (Edge Autonomy):** Cada agência física mantém um servidor local sincronizado diariamente de forma incremental em condições normais. Em isolamento, o servidor local torna-se a *Autoridade Única de Saldos* para aquela zona geográfica.
2.  **Limite de Saque de Contingência (Teto de Risco):** Para mitigar o risco de saques duplos simultâneos em agências diferentes (já que não há comunicação entre elas), é estabelecido um teto de retirada emergencial por CPF baseado em regras de GRC.

---

## 3. Critérios de Ativação do Plano de Continuidade (PCN)

O Gatilho de Ativação (*Trigger*) ocorre quando:
*   A perda de conectividade com o Banco Central e nós centrais do Apex Bank persistir por mais de **15 minutos contínuos** após tentativas automáticas de roteamento de contingência.
*   Houver confirmation de falha generalizada nos protocolos de roteamento de borda (BGP) externos, indicando indisponibilidade de longo prazo.

---
[⬅️ Voltar ao Módulo 01](./README.md) | [🏡 Voltar ao Painel Geral](../README.md)
