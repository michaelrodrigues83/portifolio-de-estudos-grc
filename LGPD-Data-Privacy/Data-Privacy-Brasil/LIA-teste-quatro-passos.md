# ⚖️ Relatório Técnico: Avaliação de Legítimo Interesse (LIA) - Teste dos Quatro Passos

**Framework Base:** Art. 7º, IX e Art. 10 da LGPD (Lei nº 13.709/2018)  
**Autor:** Michael Hernandes Rodrigues  
**Finalidade:** Demonstrar a aplicação prática do Teste de Proporcionalidade (Balancing Test) para validar o uso do Legítimo Interesse como base legal.

---

## 📋 Cenário Prático Simulado
Uma empresa do setor de tecnologia deseja tratar dados de comportamento de uso em sua plataforma para **prevenção a fraudes e melhoria de segurança nos acessos dos usuários**, sem a necessidade de coletar consentimento para cada nova atualização de segurança.

---

## 🧠 Aplicação do Teste dos Quatro Passos (LIA)

### 1️⃣ Passo 1: Legitimidade do Interesse (Legitimate Interest)
*   **Análise do Art. 10, caput:** O objetivo é apoiar e aprimorar a segurança dos ativos da empresa e dos próprios titulares.
*   **Situação Concreta:** Mitigação de riscos de invasão de contas e engenharia social. A finalidade é totalmente lícita e atende a um propósito comercial e de segurança real.
*   **Veredito do Passo 1:** ✅ Aprovado. A finalidade é lícita e concreta.

### 2️⃣ Passo 2: Teste de Necessidade (Necessity Test)
*   **Análise do Art. 10, § 1º:** O tratamento dos dados de comportamento de login (IP, horário, geolocalização aproximada) é estritamente necessário para identificar anomalias no padrão de acesso.
*   **Minimização de Dados:** Não serão coletados dados sensíveis ou informações desnecessárias para o algoritmo de segurança. Não há outro meio menos intrusivo de garantir a proteção em tempo real das contas.
*   **Veredito do Passo 2:** ✅ Aprovado. Respeita o princípio da minimização.

### 3️⃣ Passo 3: Teste de Balanceamento (Balancing Test)
*   **Análise do Art. 6º, I (Adequação) e Art. 7º, IX:** O interesse econômico e de segurança da empresa se choca com os direitos do titular?
*   **Legítima Expectativa Objetiva:** O usuário possui a legítima expectativa de que a plataforma monitore acessos suspeitos para proteger a sua própria conta e os seus dados financeiros. 
*   **Impacto nos Direitos Fundamentais:** Baixo. O monitoramento é restrito ao ambiente logado e não invade a privacidade externa do cidadão.
*   **Veredito do Passo 3:** ✅ Aprovado. Há equilíbrio e a expectativa do titular é respeitada.

### 4️⃣ Passo 4: Salvaguardas e Mitigação de Riscos (Safeguards)
*   **Análise do Art. 10, § 2º e § 3º:** Medidas técnicas adotadas para garantir a segurança e os direitos:
    *   **Transparência:** Atualização expressa na Política de Privacidade informando sobre o monitoramento automatizado para segurança.
    *   **Direito de Oposição (Opt-out):** Sendo um mecanismo crítico de segurança da plataforma, caso o usuário se oponha, ele é informado sobre a impossibilidade de manter a conta ativa devido aos riscos de conformidade.
    *   **Técnicas de Proteção:** Aplicação de criptografia nos logs de acesso e restrição de acesso apenas ao time de SOC (Controle de Acessos).
*   **Veredito do Passo 4:** ✅ Aprovado. Salvaguardas devidamente implementadas.

---

## 🎯 Conclusão de Governança
Com base no preenchimento satisfatório dos quatro passos do LIA, o tratamento de dados para prevenção a fraudes está **autorizado e respaldado juridicamente** sob a base legal do Legítimo Interesse, garantindo conformidade e proteção jurídica perante a ANPD (Autoridade Nacional de Proteção de Dados).

## 🔄 Governança Contínua e Ciclo de Vida do LIA

O Teste de Legítimo Interesse não é um documento estático e deve acompanhar todo o ciclo de vida do tratamento de dados. Para garantir a governança contínua e evitar o desalinhamento da operação ao longo do tempo, este LIA será reaberto e revisado imediatamente diante dos seguintes **gatilhos de alteração (Trigger Events)**:

* **Novas Fontes de Dados:** Caso sejam integradas novas bases de dados ou ferramentas de coleta que não faziam parte do escopo inicial deste relatório.
* **Mudança na Segmentação ou Perfilamento:** Se os critérios de cruzamento de dados, criação de perfis comportamentais (profiling) ou direcionamento forem modificados.
* **Alteração na Expectativa do Titular:** Se houver mudanças no contexto do relacionamento com o cliente ou nas práticas de mercado que alterem o que o titular razoavelmente espera em termos de privacidade.
* **Desvio de Finalidade:** Qualquer alteração no objetivo principal que justificou o início do tratamento de dados.

### 📅 Revisão Periódica
Mesmo na ausência de gatilhos de alteração disparados pela operação, este relatório passará por uma auditoria e revisão preventiva a cada **12 meses** para validar se as salvaguardas e mitigações propostas continuam eficazes.


---
⬅️ [Voltar para a Trilha de LGPD](./README.md)
