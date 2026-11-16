# 🔒 03. Blindagem Física, Controle de Perímetro e Fator Humano (Anexo A.6 e A.7)

**Framework de Referência:** ISO/IEC 27001:2022 (Controles de Pessoas A.6 e Controles Físicos A.7)

> **Visão de Defesa em Profundidade:** De nada adianta investir em *firewalls* de última geração e criptografia se um invasor puder cruzar a portaria sem identificação, conectar um dispositivo malicioso em um terminal de logística ou furtar um servidor local. A segurança da informação começa no perímetro físico e no comportamento humano.

---

## 1. Zoneamento Físico e Círculos Concêntricos (Controles A.7.1 e A.7.2)

Aplicando técnicas profissionais de **gestão de riscos patrimoniais e proteção de ativos críticos**, a planta da *NexusLog S.A.* foi dividida em quatro zonas progressivas de restrição:

* **Nível 1 — Zona Pública (Portaria Externa e Recepção):** Triagem inicial obrigatória com validação de documento oficial, cadastro fotográfico e emissão de crachá de visitante de cor diferenciada.
* **Nível 2 — Zona Controlada (Pátio Logístico e Docas):** Acesso restrito a motoristas e operadores homologados mediante leitura individual de crachá e conferência documental.
* **Nível 3 — Zona Restrita (Escritórios Administrativos e CCO):** Acesso exclusivo via catracas biométricas com bloqueio anti-carona (*Anti-Tailgating*). Visitantes e prestadores de manutenção só circulam mediante **escolta presencial obrigatória** de um colaborador autorizado.
* **Nível 4 — Zona Crítica (Sala de Servidores, Sala de CFTV e Cofre de Mídias):** Acesso restrito exclusivamente ao núcleo de Infraestrutura e GRC, protegido por porta blindada com fechadura eletromagnética em modo *Fail-Secure*, autenticação física em dois fatores (biometria + credencial física) e registro manual auditável em livro de controle.

---

## 2. Proteção Ambiental, Cabeamento e Ativos (Controles A.7.4 a A.7.14)

* **Monitoramento Ativo Sem Pontos Cegos (A.7.4):** Cobertura integral por CFTV de alta definição nas entradas, corredores técnicos, docas críticas e interior da sala de servidores, com gravação redundante e retenção protegida por 90 dias.
* **Resiliência Ambiental (A.7.5):** Climatização redundante com sensores de temperatura e umidade na sala de servidores, sistema de supressão de incêndio por gás limpo (preservando os equipamentos eletrônicos) e banco de nobreaks conectado a gerador diesel automático.
* **Blindagem de Cabeamento e Portas (A.7.12):** Passagem de cabos de rede e energia em eletrodutos metálicos fechados para impedir interceptação física (*wiretapping*) ou sabotagem, combinada ao bloqueio físico de portas USB em todos os terminais operacionais.
* **Política de Mesa Limpa e Tela Limpa (A.7.7):** Bloqueio automático de tela após 3 minutos de inatividade e proibição estrita de manifestos de carga, senhas ou dados pessoais impressos expostos sobre as bancadas.
* **Cadeia de Custódia e Descarte Seguro (A.7.10 e A.7.14):** Controle rigoroso de saída de equipamentos portáteis e destruição física certificada (desmagnetização e trituração mecânica) de discos rígidos e mídias descartadas.

---

## 3. Fator Humano e Simulações de Intrusão (Controles A.6.1 a A.6.8)

* **Triagem e Compromisso Legal (A.6.1 e A.6.2):** Verificação rigorosa de antecedentes conforme a legislação vigente para cargos críticos (TI, GRC, CCO e Segurança) e assinatura de Termo de Confidencialidade (NDA).
* **Conscientização e *Physical Red Teaming* (A.6.3):** Além de simulações mensais de *phishing* por e-mail, o programa de conscientização realiza **testes práticos de intrusão física** (tentativa de acesso sem crachá simulando técnico terceirizado ou entregador), treinando recepcionistas, vigilantes e analistas a desafiarem qualquer presença não identificada.

---

[⬅️ Voltar ao Módulo 02](./README.md) | [🏠 Voltar ao Painel Geral](../README.md)
