# LAB-VLANs-Virtuais
Laboratório de VLANs, roteador e switch – portfólio

Laboratório de VLANs – Rede Simulada
Descrição

Este projeto consiste em um laboratório de redes com VLANs, roteador e switch, criado para fins de estudo e prática em redes de computadores. O objetivo é consolidar conhecimentos em:
Configuração de VLANs
Subinterfaces em roteadores
Roteamento entre redes diferentes
Conectividade entre dispositivos


Topologia
2 PCs
1 Switch (ou mais, conforme evolução do lab)
1 Roteador


Estrutura:
PC1 --- Switch --- Roteador
PC2 --- 

VLAN 10 → PCs da rede interna 10
VLAN 20 → PCs da rede interna 20
Roteador → Comunicação entre VLANs e gateway para internet


Configurações
Roteador
enable
configure terminal

# Interface principal
interface gig0/0
no ip address
no shutdown
exit

# Subinterfaces VLANs
interface gig0/0.10
encapsulation dot1Q 10
ip address 192.168.10.1 255.255.255.0
no shutdown
exit

interface gig0/0.20
encapsulation dot1Q 20
ip address 192.168.20.1 255.255.255.0
no shutdown
exit

Switch
VLAN 10 e VLAN 20 criadas e atribuídas às portas correspondentes

Conexão trunk para o roteador

Cabos conectados corretamente: PCs → Switch → Roteador


Testes de Conectividade
Ping do PC1 para o gateway 192.168.10.1 → ✅ Sucesso

Ping do PC2 para o gateway 192.168.20.1 → ✅ Sucesso

Ping entre PCs de VLANs diferentes → ✅ Sucesso após configuração de subinterfaces no roteador


Aprendizados
Cada VLAN precisa de uma subinterface do roteador para comunicação entre redes
VLANs funcionam como redes internas separadas
Switch organiza e separa as VLANs, enquanto o roteador fornece roteamento
Conectividade depende de cabos corretos, trunk ativo e interfaces do roteador no no shutdown
