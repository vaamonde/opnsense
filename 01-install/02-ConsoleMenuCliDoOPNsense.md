Autor: Robson Vaamonde<br>
Procedimentos em TI: http://procedimentosemti.com.br<br>
Bora para Prática: http://boraparapratica.com.br<br>
Robson Vaamonde: http://vaamonde.com.br<br>
Facebook Procedimentos em TI: https://www.facebook.com/ProcedimentosEmTi<br>
Facebook Bora para Prática: https://www.facebook.com/BoraParaPratica<br>
Instagram Procedimentos em TI: https://www.instagram.com/procedimentoem<br>
YouTUBE Bora Para Prática: https://www.youtube.com/boraparapratica<br>
LinkedIn Robson Vaamonde: https://www.linkedin.com/in/robson-vaamonde-0b029028/<br>
Github Procedimentos em TI: https://github.com/vaamonde<br>
Data de criação: 18/09/2024<br>
Data de atualização: 18/09/2024<br>
Versão: 0.01<br>
Testado e homologado OPNsense 24.7

Conteúdo estudado nessa instalação:<br>
#01_ Autenticando no Menu CLI (Command Line Interface) do OPNsense<br>
#02_ Conhecendo as Opções do Menu CLI (Command Line Interface) do OPNsense<br>
#03_ Atribuindo Interface de Rede no Menu CLI (Command Line Interface) do OPNsense<br>
#04_ Alterando os Endereços IP das Interfaces no Menu CLI (Command Line Interface) do OPNsense<br>
#05_ Testando a Conectividade no Menu CLI (Command Line Interface) do OPNsense<br>

OBSERVAÇÃO IMPORTANTE: COMENTAR NO VÍDEO DO CONSOLE DO OPNSENSE SE VOCÊ CONSEGUIU FAZER A CONFIGURAÇÃO COM A SEGUINTE FRASE: Configuração via Console do OPNsense realizado com sucesso!!! #BoraParaPrática

#boraparapratica #boraparaprática #vaamonde #robsonvaamonde #procedimentosemti #opnsense #firewall #desafiovaamonde #desafioboraparapratica #desafioopnsense #migracaoopnsense

Site Oficial do OPNSense: https://opnsense.org/<br>
Releases do OPNsense: https://docs.opnsense.org/releases.html<br>
Roadmap do OPNsense: https://opnsense.org/about/road-map/<br>
Blog Oficial do OPNsense: https://opnsense.org/blog/

Versão 24.7 do OPNsense: https://forum.opnsense.org/index.php?topic=42787.msg212371#msg212371

Começando com o OPNsense: https://opnsense.org/users/get-started/<br>
Documentação Oficial do OPNsense: https://docs.opnsense.org/

[![Menu CLI](http://img.youtube.com/vi//0.jpg)]( "Menu CLI")

Link da vídeo aula: 

Observações das configurações utilizadas nessa documentação
(DEFAULT) = Configuração padrão do OPNsense = ON ou OFF, Value OU None
(DISABLE) = Desabilitado nessa configuração = OFF
(ENABLE)  = Habilitado nessa configuração = ON
(REMOVE)  = Removido dessa configuração = Sem valor ou opção
<***>     = Botão de confirmação ou de aplicar as configurações

Conexão Serial: https://docs.opnsense.org/manual/how-tos/serial_access.html<br>
Configurações do Console: https://docs.opnsense.org/manual/install.html

#01_ Autenticando no Menu CLI (Command Line Interface) do OPNsense<br>
```bash
*** fwvaamonde.pti.intra (FQDN DO SERVIDOR): OPNsense 24.7 (VERSÃO DO OPENSENSE) ***

  LAN (em0)   -> v4: 192.168.1.1/24 (ENDEREÇO IPv4 PADRÃO DA INTERFACE LAN)
  WAN (em1)   -> v4/DHCP4: 172.16.1.156/24 (ENDEREÇO IPv4 PADRÃO DINÂMICO VIA DHCP4)
                 v6/DHCP6: 2804:014C:0090::3F3D/64 (ENDEREÇO IPv6 PADRÃO VIA DHCP6)

  HTTPS: sha256 (HASH SHA256 DO CERTIFICADO HTTPS DO OPNSENSE PARA ACESSO REMOTO)

FreeBSD/amd64 (SISTEMA BASE/ARQUITETURA) (fwvaamonde.pti.intra) (ttyv0)
login: root
Password: pti@2018
```

#02_ Conhecendo as Opções do Menu CLI (Command Line Interface) do OPNsense<br>
```bash
Opções do Console Menu CLI do OPNsense
 0) Logout - sair do acesso remoto via SSH ou TTY
 1) Assign Interfaces - ativação e atribuição de Interfaces de Rede
 2) Set Interface IP address - configuração do Endereço IPv4, IPv6 e DHCP Server
 3) Reset the root password - resetar para a senha padrão (opnsense) do usuário root
 4) Reset to factory defaults - resetar para as configurações padrão do OPNsense
 5) Power off system - desligar o OPNsense
 6) Reboot system - reinicializar o OPNsense
 7) Ping host - testar a conectividade de rede LAN ou WAN com o comando ping
 8) Shell - acessar o Bash/Shell (Command Line) do OPNsense
 9) pfTop - software de monitoramento de protocolo de conexões de rede LAN ou WAN
10) Firewall log - filtros dos logs referente as regras de Firewall de LAN ou WAN
11) Reload all services - reinicializar todos os serviços caso tenha falha de acesso via navegador
12) Update from console - atualização do OPNsense via console
13) Restore a backup - restauração do backup via console
```

#03_ Atribuindo Interface de Rede no Menu CLI (Command Line Interface) do OPNsense<br>
```bash
Enter an option: 1 <Enter>
  #opção para configurar o LAGG (Link Aggregation v4)
  Do you want to configure LAGGs now? [y/N]: N <Enter>
  #opção para configurar o VLAN (Virtual LAN)
  Do you want to configure VLANs now? [y/N]: N <Enter>
  
  em0 (INTERFACE PADRÃO DA LAN)
  em1 (INTERFACE PADRÃO DA WAN)

  Enter the WAN interface name or 'a' for auto-detection: em1 <Enter>
  Enter the LAN interface name or 'a' for auto-detection: em0 <Enter>
  Enter the Optional interface 1 name or 'a' for auto-detection: <Enter>

  WAN  --> em1
  LAN  --> em0

  Do you want to proceed? [y/N] y <Enter>
```

#04_ Alterando os Endereços IP das Interfaces no Menu CLI (Command Line Interface) do OPNsense<br>
```bash
Enter an option: 2 <Enter>

Available interfaces

1 - LAN (em0 - static, track6)
2 - WAN (em1 - dhcp, dhcp6)

Enter the number of the interface to configure: 1 <Enter>

Configure IPv4 address LAN interface via DHCP? [y/N] n <Enter>
  Enter the new LAN IPv4 address. Press <ENTER> for none: 
    > 192.168.1.1 <Enter>
  Enter the new LAN IPv4 subnet bit count (1 to 32):
    > 24 <Enter>
  For a WAN, enter the new LAN IPv4 upstream gateway address.
  For a LAN, press <ENTER> for none:
    > <Enter>
  Configure IPv6 address LAN interface via WAN tracking? [Y/n]: n <Enter>
  Configure IPv6 address LAN interface via DHCP6? [y/N] n <Enter>
  Enter the new LAN IPv6 address. Press <ENTER> for none:
    > <Enter>
  Do you want to enable the DHCP server on LAN? [y/N] y <Enter>
  Enter the start address of the IPv4 client address range: 192.168.1.100 <Enter>
  Enter the end address of the IPv4 client address range: 192.168.1.150 <Enter>
  Do you want to change the Web GUI protocol from HTTPS to HTTP? [y/N] n <Enter>
  Do you want to generate a new self-signed web GUI certificates? [y/N] y <Enter>
  Restore web GUI access defaults? [y/N]: n <Enter>
```

#05_ Testando a Conectividade no Menu CLI (Command Line Interface) do OPNsense<br>
```bash
Enter an option: 7 <Enter>

Enter a host name of IP address: 8.8.8.8 <Enter>
Enter a host name of IP address: google.com <Enter>
```