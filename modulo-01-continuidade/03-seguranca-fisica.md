# 🔒 Segurança da Informação e Blindagem Física (ISO/IEC 27001:2022)
**Framework de Referência:** Controles do Anexo A da ISO/IEC 27001:2022 aplicados à resiliência de ativos.

Na ausência de conectividade WAN para validar credenciais digitais de forma centralizada ou sincronizar logs com um SIEM em nuvem, a segurança física e o isolamento lógico (*Air-Gapping*) tornam-se os controles mais críticos do Apex Bank S.A.

---

## 1. Segurança Física e Controle de Perímetro (Controle A.7)

Sob o estresse do cenário simulado (falha elétrica parcial causada pelo Super El Niño e pânico civil por desabastecimento), os controles de acesso físico foram enrijecidos para proteger o numerário e o hardware local:

*   **Controle A.7.4 (Perímetros de Segurança Física):** Ativação de barreira física total na sala do servidor de borda (*Edge Server*). As portas automáticas com fechaduras eletromagnéticas centrais devem ser comutadas manualmente para o modo "Falha-Fechada" (*Fail-Secure*), sendo operadas apenas com chaves físicas tubulares de alta segurança.
*   **Controle A.7.2 (Controle de Acessos Físicos):** Suspensão de biometria baseada em nuvem. A entrada em áreas críticas exige autenticação em dois fatores físicos: crachá corporativo com holografia e assinatura presencial no livro de registro de GRC, acompanhado pela equipe de vigilância técnica.
*   **Controle A.7.6 (Trabalho em Áreas Seguras):** Fica proibida a permanência de qualquer colaborador desacompanhado na sala de servidores locais ou tesouraria. Aplicação estrita da política de "Duas Pessoas" (*Two-Man Rule*) para qualquer manutenção emergencial ou exportação de logs.

---

## 2. Isolamento de Rede e Engenharia de Resiliência (Controle A.8)

Para mitigar o risco de o ataque *Zero-Day* infectar sistemas internos caso a conectividade externa apresente oscilações ou retornos parciais, adota-se a estratégia de isolamento lógico absoluto:

*   **Controle A.8.20 (Segurança de Redes):** Implementação de *Air-Gapping* físico. Os switches da rede interna da agência (LAN) devem ser isolados logicamente dos roteadores de borda externos. Toda a comunicação interna entre os caixas locais e o servidor de borda operará estritamente via protocolo local com criptografia em trânsito (TLS 1.3 local).
*   **Controle A.8.24 (Uso de Programas Utilitários Privilegiados):** Bloqueio de portas USB e de diagnóstico em todas as estações de trabalho dos caixas através de chaves físicas de bloqueio e políticas locais de GPO restritas, evitando a introdução de ameaças via engenharia social ou dispositivos infectados trazidos de fora.

---

## 3. Trilhas de Auditoria e Integridade Local

*   **Controle A.8.15 (Registro de Eventos):** Os logs de segurança do servidor de borda e das estações locais devem ser gravados localmente em um storage de armazenamento imutável do tipo WORM (*Write Once, Read Many*), garantindo que os registros de saques não possam ser alterados ou apagados enquanto o sistema estiver offline.

---
[⬅️ Voltar ao Módulo de Resiliência](./README.md) | [🏡 Voltar ao Painel Geral](../README.md)
