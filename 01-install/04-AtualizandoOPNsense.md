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
Data de criação: 21/09/2024<br>
Data de atualização: 06/10/2024<br>
Versão: 0.02<br>
Testado e homologado para a versão do OPNsense 24.7

Conteúdo estudado nessa instalação:<br>
#01_ Autenticando no WebGUI (Web Graphical Unit Interface) do OPNsense<br>
#02_ Atualizando o Firmware (Sistema) do OPNsense<br>
#03_ Autenticando no Menu CLI (Command Line Interface) do OPNsense<br>
#04_ Atualizando o OPNsense via Menu CLI (Command Line Interface) POUCO UTILIZADO<br>

OBSERVAÇÃO IMPORTANTE: COMENTAR NO VÍDEO DO UPDATE DO OPNSENSE SE VOCÊ CONSEGUIU FAZER A ATUALIZAÇÃO COM A SEGUINTE FRASE: Atualização do OPNsense realizado com sucesso!!! #BoraParaPrática

#boraparapratica #boraparaprática #vaamonde #robsonvaamonde #procedimentosemti #opnsense #firewall #desafiovaamonde #desafioboraparapratica #desafioopnsense #migracaoopnsense

Site Oficial do OPNSense: https://opnsense.org/<br>
Releases do OPNsense: https://docs.opnsense.org/releases.html<br>
Roadmap do OPNsense: https://opnsense.org/about/road-map/<br>
Blog Oficial do OPNsense: https://opnsense.org/blog/

Versão 24.7 do OPNsense: https://forum.opnsense.org/index.php?topic=42787.msg212371#msg212371

Começando com o OPNsense: https://opnsense.org/users/get-started/<br>
Documentação Oficial do OPNsense: https://docs.opnsense.org/

[![Update OPNsense](http://img.youtube.com/vi//0.jpg)]( "Update OPNsense")

Link da vídeo aula: 

Observações das configurações utilizadas nessa documentação
```bash
A) (CHANGE)  = Configuração alterada o seu valor = VALUE ou TEXT
B) (DEFAULT) = Configuração padrão do OPNsense = ON ou OFF, Value OU None
C) (DISABLE) = Desabilitado nessa configuração = OFF
D) (ENABLE)  = Habilitado nessa configuração = ON
E) (REMOVE)  = Removido dessa configuração = Sem valor ou opção
F) <***>     = Botão de confirmação ou de aplicar as configurações
```

Ferramentas do OPNsense: https://docs.opnsense.org/manual/opnsense_tools.html<br>
Atualização do OPNsense: https://docs.opnsense.org/manual/opnsense_tools.html#opnsense-update<br>
Reversão da Atualização do OPNsense: https://docs.opnsense.org/manual/opnsense_tools.html#opnsense-revert<br>
Atualização de Patch do OPNsense: https://docs.opnsense.org/manual/opnsense_tools.html#opnsense-patch

Atualização do OPNsense: https://docs.opnsense.org/manual/updates.html#<br>
Incluindo Software ao OPNsense: https://docs.opnsense.org/manual/software_included.html<br>

#01_ Autenticando no WebGUI (Web Graphical Unit Interface) do OPNsense<br>
```bash
#utilizar os navegadores para acessar o GUI do OPNsense
firefox ou google chrome: https://192.168.1.1

01. OPNsense
  Username: root
  Password: pti@2018
  <Login>
```

#02_ Atualizando o Firmware (Sistema) do OPNsense<br>
```bash
#configurando o sistema de atualização do OPNsense
01. System
  Firmware
    Settings
      (ON) advanced mode (ENABLE)
      (ON) full help (ENABLE)
      Mirror: Default (DEFAULT)
      Flavour: Default (DEFAULT)
      Type Community (DEFAULT)
      Subscription: (DEFAULT)
      Reboot (OFF) Always reboot after a successful update (DEFAULT)
      Usage: In order to apply these settings a firmware update must be performed after save, which can include a reboot of the system.
    <Save>

#verificando o status de atualização do OPNsense
02. System
  Firmware
    Status
      <Check for updates> (Run and audit)

#atualizando o sistema do OPNsense
03. System
  Firmware
    Updates
    #OBSERVAÇÃO IMPORTANTE: A PARTIR DO MOMENTO QUE VOCÊ INICIA A ATUALIZAÇÃO DO OPNSENSE
    #ESSE PROCESSO DEMORA UM POUCO DEPENDENDO DA VELOCIDADE DO LINK DE WAN QUE VOCÊ ESTÁ
    #UTILIZANDO E DO DOWNLOAD E INSTALAÇÃO DOS PACOTES A SEREM ATUALIZADOS, RECOMENDO FAZER
    #ESSA ATUALIZAÇÃO EM JANELA (PERÍODO) SEM UTILIZAÇÃO DA INTERNET.
    #
    #SE ESTIVER UTILIZANDO O VIRTUALBOX RECOMENDO HABILITAR O RECURSO DE: Informações sobre
    #a Sessão PARA MONITORAR O DESEMPENHO DA CARGA DA CPU, REDE, DISCO E SAÍDA DA VM.
    24.7.5
      <Close>
    <Update>
      The firewall will reboot directly after this firmware update. <OK>

#reiniciar o sistema após a atualização do OPNsense
04. Power
  Reboot
    Are you sure you want to reboot the system? <Yes>

#verificando os pacotes atualizados no OPNsense
05. System
  Firmware
    Changelog

#verificando os Plugins do OPNsense
06. System
  Firmware
    Plugins

#verificando os Pacotes do OPNsense
07. System
  Firmware
    Packages
```

#03_ Adicionando mais um Widget (Mini Aplicativo) no Dashboard do OPNsense<br>
```bash
#adicionando o mini aplicativo de imagem no Dashboard
<+ Add Widget>
  Coluna 04 (Firewall)
    01) Picture
<Save>

#configurando o mini aplicativo do imagem do Dashboard
01. Settings
  General
    Picture
      <Procurar>
        Selecione a imagem a ser adicionada e clique em: <Abrir>
  <Save>
```

#04_ Autenticando no Menu CLI (Command Line Interface) do OPNsense<br>
```bash
*** fwvaamonde.pti.intra (FQDN DO SERVIDOR): OPNsense 24.7 (VERSÃO DO OPNSENSE) ***

  LAN (em0)   -> v4: 192.168.1.1/24 (ENDEREÇO IPv4 PADRÃO DA INTERFACE LAN)
  WAN (em1)   -> v4/DHCP4: 172.16.1.156/24 (ENDEREÇO IPv4 PADRÃO DINÂMICO VIA DHCP4)
                 v6/DHCP6: 2804:014C:0090::3F3D/64 (ENDEREÇO IPv6 PADRÃO VIA DHCP6)

  HTTPS: sha256 (HASH SHA256 DO CERTIFICADO HTTPS DO OPNSENSE PARA ACESSO REMOTO)

FreeBSD/amd64 (SISTEMA BASE/ARQUITETURA) (fwvaamonde.pti.intra) (ttyv0)
login: root
Password: pti@2018
```

#05_ Atualizando o OPNsense via Menu CLI (Command Line Interface) POUCO UTILIZADO<br>
```bash
#OBSERVAÇÃO IMPORTANTE: IGUAL AO PROCEDIMENTO VIA WEBGUI, NO MODO CLI O PROCESSO DE 
#ATUALIZAR TAMBÉM É DEMORADO.

Enter an option: 12 <Enter>
  This update requires a reboot
    Proceed with this action? [y/N] y <Enter>
```