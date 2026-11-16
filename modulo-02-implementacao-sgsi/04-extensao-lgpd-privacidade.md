# ⚖️ 04. Extensão Legal: Adequação à LGPD e Mapeamento de Dados (RoPA)

**Framework de Referência:** Lei Geral de Proteção de Dados (Lei nº 13.709/2018) & ISO/IEC 27001:2022 (Controle A.5.34)

A segurança da informação é o alicerce técnico da privacidade. Na **NexusLog Soluções Inteligentes S.A.**, os controles do SGSI foram mapeados diretamente para atender aos requisitos legais da LGPD.

---

## 1. Registro das Operações de Tratamento (RoPA — Art. 37 da LGPD)

| Processo de Negócio | Dados Tratados | Categoria (LGPD) | Base Legal (Art. 7º / 11) | Controle ISO 27001 Aplicado |
| :--- | :--- | :--- | :--- | :--- |
| **Cadastro e Biometria de Motoristas** | Nome, CPF, CNH, biometria facial e geolocalização. | Dado Pessoal & Sensível | Execução de Contrato e Prevenção à Fraude (Art. 11, II, g). | **A.8.24** (Criptografia AES-256) e **A.5.15** (Controle de Acesso). |
| **Rastreamento de Entregas (Clientes)** | Nome, endereço, telefone e histórico de pedidos. | Dado Pessoal Comum | Execução de Contrato (Art. 7º, V). | **A.8.12** (Prevenção de Vazamento de Dados - DLP). |
| **Controle de Acesso Portaria / CFTV** | Imagem facial, placa do veículo e horário de acesso. | Dado Pessoal & Sensível | Legítimo Interesse e Segurança Patrimonial (Art. 7º, IX). | **A.7.4** (Monitoramento Físico) e retenção máxima de 90 dias. |

---

## 2. Salvaguardas Técnicas e Resposta a Incidentes (Art. 46 e Art. 48)

* **Privacidade por Design (Privacy by Design):** Aplicação de mascaramento e anonimização de dados pessoais em ambientes de homologação e testes de sistemas.
* **Plano de Resposta a Incidentes com Dados Pessoais:** Fluxograma integrado entre o time de Segurança da Informação e o Encarregado (DPO) para contenção técnica imediata e comunicação formal à **ANPD** e aos titulares dentro do prazo regulatório.

---

[⬅️ Voltar ao Módulo 02](./README.md) | [🏠 Voltar ao Painel Geral](../README.md)
