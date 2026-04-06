# 🌐 Enterprise Multi-Office Network Design & Automation (CCNA Level)

Este projeto consiste no design e implementação de uma infraestrutura de rede empresarial multi-site, simulada no Cisco Packet Tracer. A topologia foi desenhada para garantir **alta disponibilidade, segurança e escalabilidade**, cobrindo os tópicos fundamentais e avançados do currículo CCNA/CCNP.


## 🚀 Funcionalidades Principais

* [cite_start]**Redundância L2/L3:** Implementação de EtherChannels (PAgP e LACP) e HSRPv2 para failover de gateway. [cite: 5, 6, 36, 44]
* [cite_start]**Encaminhamento Dinâmico:** Configuração de OSPFv2 (Área 0) com otimização de interfaces passivas e tipos de rede. [cite: 56, 59, 60]
* [cite_start]**Segurança Avançada:** Proteção contra ataques de Camada 2 (DHCP Snooping, DAI, Port Security com Sticky MACs) e ACLs Estendidas para controlo de tráfego inter-office. [cite: 105, 109, 115, 118]
* [cite_start]**Serviços de Rede:** Configuração completa de DHCP, DNS, NTP Autenticado, SNMP, Syslog e NAT/PAT com failover de link. [cite: 65, 73, 75, 81, 94]
* [cite_start]**Infraestrutura Wireless:** Gestão centralizada via WLC (Wireless LAN Controller) com segurança WPA2-PSK. [cite: 126, 131]
* [cite_start]**Preparação IPv6:** Migração dual-stack utilizando endereçamento EUI-64 e rotas estáticas flutuantes. [cite: 120, 121, 125]

---

## 🛠️ Detalhes da Implementação

### 1. Camada de Acesso e Distribuição (L2/L3)
* [cite_start]**VLANs & VTP:** Organização da rede em VLANs específicas para Dados, Voz, Wi-Fi e Gestão, propagadas via VTPv2. [cite: 11, 13, 16]
* [cite_start]**Spanning Tree:** Otimização do Rapid PVST+ alinhando o Root Bridge com o router HSRP Ativo para evitar caminhos sub-ótimos. [cite: 51, 52]
* [cite_start]**PortFast & BPDU Guard:** Ativados em todas as portas de acesso para garantir convergência rápida e proteção contra loops externos. [cite: 54]

### 2. Conectividade e Routing
* [cite_start]**HSRPv2:** Configurado para redundância de primeiro salto, com preempção e prioridades ajustadas para balanceamento de carga entre switches de distribuição. [cite: 36, 40, 48]
* [cite_start]**OSPF:** Processo ID 1, utilizando Router-IDs manuais baseados em interfaces Loopback para estabilidade do plano de controlo. [cite: 56]
* [cite_start]**NAT/PAT:** Pool dinâmico (POOL1) configurado no Router R1 para acesso à Internet com verificação de failover via floating static routes. [cite: 94, 97, 63]

### 3. Gestão e Segurança (L2 Security)
* [cite_start]**SSHv2:** Acesso remoto seguro restringido por ACLs standard, permitindo apenas acessos provenientes da rede de gestão. [cite: 88, 90]
* [cite_start]**DHCP Snooping & DAI:** Implementados para mitigar ataques de Rogue DHCP e ARP Spoofing. [cite: 115, 119]
* [cite_start]**Port Security:** Limitação de MAC addresses por porta e modo de violação 'restrict' com logging via SNMP/Syslog. [cite: 109, 112]

---

## 📂 Estrutura do Repositório

* `/projeto-ccna.pka`: Ficheiro do Cisco Packet Tracer com a configuração final.
* `/docs`: Prints de validação (tabelas de routing, adjacências OSPF, pings).
* `README.md`: Documentação do projeto.

## 💻 Como utilizar
1.  Transfira o ficheiro `.pka`.
2.  Abra no **Cisco Packet Tracer (v8.x ou superior)**.
3.  Utilize as credenciais configuradas:
    * **User:** `cisco`
    * **Secret:** `ccna`
    * [cite_start]**Enable Secret:** `jeremysitlab` [cite: 2, 3]

---
*Projeto desenvolvido como parte dos estudos para a certificação Cisco CCNA.*