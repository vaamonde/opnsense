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
Data de criação: 16/09/2024<br>
Data de atualização: 18/09/2024<br>
Versão: 0.02<br>
Testado e homologado OPNsense 24.7

Site Oficial do OPNSense: https://opnsense.org/<br>
Releases do OPNsense: https://docs.opnsense.org/releases.html<br>
Roadmap do OPNsense: https://opnsense.org/about/road-map/<br>
Blog Oficial do OPNsense: https://opnsense.org/blog/

Conteúdo estudado nessa instalação:<br>
#01_ Download da ISO do OPNsense 24.x do Site Oficial<br>
#02_ Criação da Máquina Virtual no Oracle VirtualBOX<br>
#03_ Configurações da Máquina Virtual OPNsense<br>
#04_ Iniciando a Máquina Virtual do OPNsense 24.x (localizar a ISO)<br>
#05_ Instalação e Configuração do OPNsense 24.x via CLI (Command Line Interface)<br>
#06_ Se autenticando no Menu CLI (Command Line Interface) do OPNsense 24.x<br>
#07_ Acessando o OPNsense via GUI (graphical user interface) via Navegador<br>

Versão 24.7 do OPNsense: https://forum.opnsense.org/index.php?topic=42787.msg212371#msg212371

Começando com o OPNsense: https://opnsense.org/users/get-started/<br>
Documentação Oficial do OPNsense: https://docs.opnsense.org/

OPNSense é um firewall de licença BSD baseado no FreeBSD e desenvolvido pela Decisio, uma empresa da Holanda que constrói hardware e vende pacotes do OPNsense embarcado. Ele é um fork do pfSense, e este também é do m0n0wall, e todos estes são baseados no FreeBSD. Foi lançado em Janeiro de 2015

[![Instalação OPNsense](http://img.youtube.com/vi//0.jpg)]( "Instalação OPNsense")

Link da vídeo aula: 

Servidores de DNS recomendados para serem utilizados no OPNsense
DNS Google..............: Preferencial: 8.8.8.8 - Secundário: 8.8.4.4
OpenDNS Cisco...........: Preferencial: 208.67.222.222 - Secundário: 208.67.220.220
OpenDNS FamilyShield....: Preferencial: 208.67.222.123 - Secundário: 208.67.220.123
CloudFlare..............: Preferencial: 1.1.1.1 - Secundário: 1.0.0.1
CloudFlare FamilyShield.: Preferencial: 1.1.1.3 - Secundário: 1.0.0.3
UltraDNS Neustar........: Preferencial: 64.6.64.6 - Secundário: 64.6.65.6 
UltraDNS Malware........: Preferencial: 156.154.70.2 - Secundário: 156.154.71.2
UltraDNS FamilyShield...: Preferencial: 156.154.70.3 - Secundário: 156.154.71.3
Quad9 IBM...............: Preferencial: 9.9.9.9 - Secundário: 149.112.112.112
Quad9 Malware...........: Preferencial: 9.9.9.11 - Secundário: 149.112.112.11

Observações das configurações utilizadas nessa documentação
(DEFAULT) = Configuração padrão do OPNsense = ON ou OFF, Value OU None
(DISABLE) = Desabilitado nessa configuração = OFF
(ENABLE)  = Habilitado nessa configuração = ON
(REMOVE)  = Removido dessa configuração = Sem valor ou opção
<***>     = Botão de confirmação ou de aplicar as configurações

Dimensionamento e configuração de hardware: https://docs.opnsense.org/manual/hardware.html<br>
Instalação e configuração inicial: https://docs.opnsense.org/manual/install.html<br>
Instalação virtual e baseada em nuvem: https://docs.opnsense.org/manual/virtuals.html

#01_ Download da ISO do OPNsense 24.x do Site Oficial<br>
```bash
#OBSERVAÇÃO IMPORTANTE: POR PADRÃO A IMAGEM DO OPNSENSE ESTÁ COMPACTADA COM A EXTENSÃO BZ2, APÓS
#O DOWNLOAD DESCOMPACTAR A IMAGEM NO DIRETÓRIO CORRENTE: DICA: SE VOCÊ UTILIZA O MICROSOFT WINDOWS
#RECOMENDO INSTALAR O SOFTWARE 7-Zip: https://www.7-zip.org/download.html

A) Link de download do OPNsense: https://opnsense.org/download/
B) Architecture: amd64
C) Select the image type: dvd
D) Mirror Location: LeaseWeb
<Download>
```

#02_ Criação da Máquina Virtual no Oracle VirtualBOX<br>
```bash
A) Link de download do Oracle VirtualBOX: https://www.virtualbox.org/wiki/Downloads
B) Vídeo de instalação do VirtualBOX no Linux Mint: https://www.youtube.com/watch?v=yTihvAaaxpU
C) Atualização do VirtualBOX no Linux Mint: https://www.youtube.com/watch?v=DU47PLFSxpA

Oracle VirtualBOX Gerenciado (versão 7.x ou superior).

01) Ferramentas;	
<Novo>

02) Nome da Máquina Virtual e Sistema Operacional:
	Nome: OPNsense (altere conforme a sua necessidade)
	Pasta (F): #PATH_PADRÃO\OPNsense (altere conforme a sua necessidade)
	Imagem ISO: <não selecionar>
	Edição: (sem informação)
	Tipo: BSD
	Versão: FreeBSD (64-bit)
<Próximo>

03) Hardware:
	Memória Base: 4096MB (altere conforme a sua necessidade, mínimo 2048MB)
	Processadores: 02 CPU (altere conforme a sua necessidade, mínimo 2 CPU)
	Habilitar EFI (SOs especiais apenas): OFF (Desligado)
<Próximo>

04) Disco Rígido Virtual:
	Criar um novo disco rígido virtual agora: ON (Selecionar)
	  Tamanho do Disco: 16,00GB (alterar conforme a sua necessidade, mínimo 16GB)
	Pré-alocar Tamanho Total (F): OFF (Desativado) 
<Próximo>

05) Sumário
<Finalizar>
```

#03_ Configurações da Máquina Virtual OPNsense<br>
```bash
Oracle VirtualBOX Gerenciado (versão 7.x ou superior).

01) Selecionar a Máquina Virtual: OPNsense
<Configurações>

02) Sistema
	Placa-Mãe
	  Recurso Estendidos
	    Relógio da máquina retorno hora UTC: OFF (Desabilitar)
	Processador
      Recursos Estendidos: Habilitar PAE/NX
                           Habilitar VT-x/AMD-v Aninhado 

03) Monitor
	Tela (S)
	  Memória de Vídeo: 128MB
	  Recursos Estendidos: Habilitar Aceleração 3D: ON (Habilitar)

04) Áudio
	Habilitar Áudio: OFF (Desabilitar)

05) Rede
	Adaptador 1 (LAN)
	  Habilitar Placa de Rede: ON (Habilitar)
	  Conectado a: Rede Interna
	  Nome: intnet
	Adaptador 2 (WAN)
	  Habilitar Placa de Rede: ON (Habilitar)
	  Conectado a: Placa em modo Bridge
	  Nome: enp3s0 (Placa de Rede On-Board)
	  #OBSERVAÇÃO: VERIFIQUE QUAL PLACA DE REDE VOCÊ ESTÁ USANDO NO SEU EQUIPAMENTO
	  #QUE ESTÁ CONECTADO NA SUA REDE LOCAL, PODE SER PLACA DE REDE CABEADA OU PLACA
	  #DE REDE SEM-FIO (RECOMENDO SEMPRE PLACA DE REDE CABEADA, MELHOR DESEMPENHO).
<OK>
```

#04_ Iniciando a Máquina Virtual do OPNsense 24.x (localizar a ISO)<br>
```bash
Oracle VirtualBOX Gerenciado (versão 7.x ou superior).

01. Selecionar a Máquina Virtual: OPNsense: 
<Iniciar>

02. VirtualBOX VM	
	DVD: <Outro>
	LOCALIZAR A IMAGEM DA ISO DO OPNSENSE 24.x
<Montar e Tentar Novo Boot>
```

#05_ Instalação e Configuração do OPNsense 24.x via CLI (Command Line Interface)<br>
```bash
#OBSERVAÇÃO IMPORTANTE: Endereço IPv4 padrão do OPNsense: 192.168.1.1/24, Usuário padrão: root
#Senha padrão: opnsense, Interface LAN padrão (VirtualBOX): em0 e Interface WAN padrão: em1.

A) login: root
B) password: opnsense

#OBSERVAÇÃO: DIFERENTE DO PFSENSE, A ISO DO OPNSENSE INICIA VIA LIVE-CD, POR CAUSA DISSO QUE O
#MENU PADRÃO DE CONFIGURAÇÃO É MOSTRADO, RECOMENDO FAZER AS CONFIGURAÇÕES BÁSICAS DE REDE ANTES
#DE INICIAR A INSTALAÇÃO NO HARD DISK (HD).

#OBSERVAÇÃO: Você também pode utilizar o usuário: installer com a senha: opnsense para iniciar
#automaticamente a instalação do OPNsense sem passar pelo Menu de Configurações.

C) Menu: 8) Shell
  Enter an option: 8 <Enter>
    opnsense-installer <Enter>

01. Keymap Selection
  >>> Continue with default keymap
    <Select>

02. Choose one of the following taks to perform
  Install (ZFS)
    <OK>

03. ZFS Configuration
  Select Virtual Device Type
    stripe Stripe - No Redundancy
      <OK>

04. ZFS Configuration
  [X] ada0 VBOX HARDISK (PRESSIONE BARRA DE ESPAÇO PARA SELECIONAR)
    <OK>

05. ZFS Configuration
  Last Chance! Are you sure you want to destroy the current contents of the following disk:
    ada0
      <Yes>

06. Final Configuration
  Setup of your OPNsense system is nearly complete
    Root Password Change root password
      <OK>

07. Set Password
  Please select a password for the system management account (root)
    Password: pti@2018 (ALTERE CONFORME A SUA NECESSIDADE)
      <OK>
  Please confirm the password for the system management account (root)
    Confirm: pti@2018 (ALTERE CONFORME A SUA NECESSIDADE)
      <OK>

08. Final Configuration
  Setup of your OPNsense system is nearly complete
    Complete Install Exit and reboot
      <OK>

#OBSERVAÇÃO IMPORTANTE: IGUAL QUE ACONTECE NA INSTALAÇÃO DO PFSENSE, A ISO DO OPNSENSE NÃO É
#EJETADA NO FINAL DA INSTALAÇÃO, SENDO NECESSÁRIO REMOVER A ISO E REINICIAR A MÁQUINA VIRTUAL
#NOVAMENTE PARA QUE O OPNSENSE SEJA INICIALIZADO PELO HARD DISK.

A) Dispositivos
    Disco Ópticos
      Remover disco do driver virtual
        <Forçar Desmontagem>

B) Máquina
    Reinicializar
      <Reiniciar>
```

#06_ Se autenticando no Menu CLI (Command Line Interface) do OPNsense 24.x<br>
```bash
A) login: root
B) password: pti@2018 (ALTERE CONFORME A SUA NECESSIDADE)

01. Testando a conexão com a Internet e Rede Local
  7) Ping host
    Enter an option: 7 <Enter>

  Enter a host name of IP address: 8.8.8.8 <Enter>
  Enter a host name of IP address: google.com <Enter> (SÓ VAI FUNCIONAR DEPOIS DE TERMINAR A CONFIGURAÇÃO)
```

#07_ Acessando o OPNsense via GUI (Graphical User Interface) via Navegador<br>
```bash
#OBSERVAÇÃO IMPORTANTE: IGUAL AO PFSENSE, POR PADRÃO O OPNSENSE JÁ VEM HABILITADO O SERVIÇO DE
#DHCP SERVER NA REDE COM O ESCOPO PADRÃO DA SUB-REDE CLASSE C: 192.168.1.0/24

#verificando o endereço IPv4 obtido pelo OPNsense
ifconfig

#verificando o endereço IPv4 de Gateway Padrão
#opção do comando route: -n (numeric addresses)
route -n

#testando a conexão com o OPNsense
ping 192.168.1.1

#utilizar os navegadores para acessar o GUI do OPNsense
firefox ou google chrome: https://192.168.1.1

01. OPNsense
  Username: root
  Password: pti@2018
  <Login>

02. System: Wizard: General Setup
  <Next>

03. System: Wizard: General Information
  General Information
    Hostname: fwvaamonde
    Domain: pti.intra
    Language: English
    Primary DNS Server: 8.8.8.8 (ALTERE CONFORME A SUA NECESSIDADE)
    Secondary DNS Server: 8.8.4.4 (ALTERE CONFORME A SUA NECESSIDADE)
    Override DNS: (OFF) Allow DNS servers to be overridden by DHCP/PPP on WAN (DISABLE)
  Unbound DNS
    Enable Resolver: (ON) (DEFAULT)
    Enable DNSSEC Support: (ON) (ENABLE)
    Harden DNSSEC data: (OFF) (DEFAULT)
  <Next>

04. System: Wizard: Time Server Information
  Enter the hostname (FQDN) of the time server.
    Time server hostname: a.st1.ntp.br a.ntp.br (ALTERE CONFORME A SUA NECESSIDADE)
    Timezone: America/Sao_Paulo (ALTERE CONFORME A SUA NECESSIDADE)
  <Next>

05. System: Wizard: Configure WAN Interface
  IPv4 Configuration Type: DHCP (DEFAULT)
  General configuration
    MAC Address: None (DEFAULT)
    MTU: None (DEFAULT)
    MSS: None (DEFAULT)
  DHCP client configuration
    DHCP Hostname: None (DEFAULT)
  RFC1918 Networks
    Block RFC1918 Private Networks: (OFF) Block private networks from entering via WAN (DISABLE)
  Block bogon networks
    Block bogon networks: (OFF) Block non-Internet routed networks from entering via WAN (DISABLE)
  <Next>

06. System: Wizard: Configure LAN Interface
  LAN IP Address: 192.168.1.1 (ALTERE CONFORME A SUA NECESSIDADE)
  Subnet Mask: 24
  <Next>

07. System: Wizard: Set Root Password
  Root Password:
  Root Password Confirmation:
  <Next>

08. System: Wizard: Reload Configuration
  Click 'Reload' to apply the changes.
  <Reload>

09. Finished initial configuration!
  Click to continue to the dashboard
```