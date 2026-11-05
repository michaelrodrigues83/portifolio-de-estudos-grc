# 📂 Módulo 03: Governança de Inteligência Artificial (ISO 42001)

Neste módulo, estabelecemos as diretrizes de governança aplicadas ao ciclo de vida do algoritmo preditivo da **CrediTech Soluções Financeiras S.A.**, integrando os direitos de privacidade da LGPD com os requisitos de ética, explicabilidade e gestão de riscos da norma ISO/IEC 42001.

> ℹ️ A CrediTech é uma empresa **fictícia**, criada para fins de estudo. Prazos, periodicidades e níveis de severidade citados são hipóteses do cenário.

## 🎯 Objetivos de Conformidade
* **LGPD:**
  * Art. 20: direito do titular de solicitar a revisão de decisões tomadas unicamente com base em tratamento automatizado de dados, incluídas as destinadas a definir o seu perfil de crédito. O § 1º obriga o controlador a fornecer informações claras e adequadas sobre os critérios e procedimentos utilizados, observados os segredos comercial e industrial.
  * Art. 6º: princípios da transparência (VI), da não discriminação (IX) e da responsabilização e prestação de contas (X).
* **ISO/IEC 42001:2023:**
  * Cláusula 6.1.4 e Anexo A.5 (A.5.2 a A.5.5): avaliação de impacto de sistemas de IA sobre indivíduos, grupos e sociedade (*AI system impact assessment*, aqui abreviada como AIIA).
  * A.6.1.2: objetivos para o desenvolvimento responsável (justiça, segurança, privacidade, transparência e supervisão humana).
  * A.7.4 e A.7.5: qualidade e procedência dos dados usados na IA.
  * A.8.5: informação para as partes interessadas.
  * A.9.2: processos para o uso responsável, incluindo supervisão humana.

---

## 📑 [Projeto Prático] Governança Algorítmica da Esteira de Score Automatizado

Como a CrediTech utiliza IA para decidir de forma automática a aprovação ou negação de crédito, estruturamos os seguintes controles de governança:

### 0. Papéis e Responsabilidades

| Papel | Responsabilidade |
|---|---|
| Comitê de GRC e IA | Aprova modelos antes da produção, decide sobre suspensão ou retreino e revisa os casos contestados |
| Time de Ciência de Dados | Desenvolve, valida e monitora o modelo, e documenta dados e decisões de projeto |
| Encarregado de Dados (DPO) | Recebe as solicitações dos titulares e orienta sobre o Art. 20 |
| Auditoria Interna | Verifica periodicamente se os controles estão sendo cumpridos |

### 1. Framework de Avaliação de Impacto de IA (AIIA)

**Processo**
1. **Descrever** o sistema, a finalidade e os dados usados.
2. **Identificar as partes afetadas:** solicitantes de crédito e grupos mais vulneráveis.
3. **Identificar os impactos** sobre indivíduos (A.5.4) e sobre a sociedade (A.5.5).
4. **Avaliar** probabilidade e severidade de cada impacto.
5. **Definir mitigações** e responsáveis.
6. **Documentar** a avaliação (A.5.3) e **reavaliar** a cada mudança relevante do modelo.

**Matriz de impactos (exemplo)**

| Impacto possível | Quem é afetado | Severidade | Mitigação |
|---|---|---|---|
| Negação indevida de crédito essencial ou de financiamento estudantil | Solicitante | Alta | Canal de revisão, monitoramento de erros e limites de confiança do modelo |
| Discriminação indireta por variável *proxy* (como CEP) | Grupos socioeconômicos vulneráveis | Alta | Auditoria dos dados de treino e testes de justiça antes da produção |
| Decisão sem explicação compreensível | Solicitante | Média | Painel de critérios e relatório de decisão |
| Perda de desempenho do modelo ao longo do tempo (*drift*) | Solicitantes e a empresa | Média | Monitoramento contínuo e gatilhos de retreino |

**Monitoramento Contínuo**
* Registro e auditoria periódica das métricas de desempenho do modelo (acurácia, precisão e *recall*).
* Acompanhamento de *drift* dos dados e do modelo.
* Métricas de justiça calculadas por grupo (veja o item 2).
* **Gatilhos:** desvio acima do limite definido leva à investigação, ao retreino ou à suspensão do modelo.

### 2. Matriz de Mitigação de Vieses Algorítmicos
* **Auditoria de Dados de Treino (A.7.4 e A.7.5):** Revisão regular das bases históricas, com registro da procedência dos dados, para garantir que variáveis sensíveis e variáveis *proxy* (como o CEP de regiões vulneráveis) não gerem discriminação algorítmica de perfis socioeconômicos (Art. 6º, IX da LGPD).
* **Testes de Justiça:** Aplicação de métricas como paridade demográfica e igualdade de oportunidade, com apoio de ferramentas de código aberto (por exemplo, Fairlearn e AI Fairness 360), antes de colocar novos modelos preditivos em ambiente de produção.
* **Portão de Aprovação:** Nenhum modelo vai à produção sem a aprovação do Comitê de GRC e IA, com a AIIA e os resultados dos testes anexados.

### 3. Explicabilidade e Direito de Revisão (Artigo 20 da LGPD)
* **Transparência Amigável (A.8.5):** Disponibilização de um painel claro no aplicativo informando ao usuário os critérios gerais considerados pelo sistema automatizado (como histórico de pagamentos e comprometimento de renda), sem expor segredo comercial (Art. 20, § 1º).
* **Canal de Revisão com Intervenção Humana (A.9.2):** Caso o titular conteste a decisão automatizada, a política interna da CrediTech assegura que um analista humano do Comitê de GRC revise o caso, dentro de um prazo definido (hipótese do cenário: até 15 dias).
* **Observação jurídica:** O Art. 20 garante o direito à **revisão**, mas o texto que exigia expressamente a revisão por pessoa natural (§ 3º) foi vetado. Portanto, a revisão humana adotada pela CrediTech é uma **boa prática** alinhada à supervisão humana da ISO 42001, e não uma exigência expressa da LGPD.
* **Aprendizado contínuo:** Os casos revisados alimentam a auditoria do modelo e as decisões de retreino.

**Modelo de Relatório de Decisão ao Titular (Política de Explicabilidade)**

| Campo | Conteúdo |
|---|---|
| Decisão | Aprovado ou Recusado, com data |
| Principais fatores | Os 3 a 5 critérios que mais pesaram (por exemplo, histórico de pagamentos e comprometimento de renda) |
| Categorias de dados usadas | Cadastrais, financeiros e comportamentais (sem detalhar o algoritmo) |
| Como contestar | Canal de revisão, prazo de resposta e contato do Encarregado de Dados |
| Seus direitos | Revisão da decisão e informações sobre os critérios (Art. 20 da LGPD) |

---

## 🧭 Matriz de Controles

| Controle da CrediTech | LGPD | ISO/IEC 42001:2023 |
|---|---|---|
| Avaliação de impacto do sistema de IA | Art. 6º, X | Cláusula 6.1.4, A.5.2 a A.5.5 |
| Monitoramento de desempenho e *drift* | Art. 6º, X | A.9.2 |
| Auditoria de dados de treino | Art. 6º, IX | A.7.4, A.7.5 |
| Testes de justiça antes da produção | Art. 6º, IX | A.6.1.2 |
| Painel de critérios e relatório de decisão | Art. 6º, VI e Art. 20, § 1º | A.8.5 |
| Canal de revisão com analista humano | Art. 20 | A.9.2 |

---

## 🚀 Status dos Entregáveis
* [x] **Framework de Avaliação de Impacto (AIIA):** Processo, matriz de impactos e monitoramento definidos.
* [x] **Matriz de Mitigação de Vieses:** Diretrizes para auditoria de dados históricos e testes de justiça documentadas.
* [x] **Políticas de Explicabilidade:** Modelo de relatório de decisão para os titulares e canal de revisão definidos.

---
👉 [Voltar para a página principal do projeto](../README.md)
