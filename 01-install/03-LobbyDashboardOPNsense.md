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
Data de atualização: 03/10/2024<br>
Versão: 0.02<br>
Testado e homologado para a versão do OPNsense 24.7

Conteúdo estudado nessa instalação:<br>
#01_ Autenticando no WebGUI (Web Graphical Unit Interface) do OPNsense<br>
#02_ Conhecendo Lobby e o Dashboard do OPNsense<br>
#03_ Personalizando o Dashboard do OPNsense<br>

OBSERVAÇÃO IMPORTANTE: COMENTAR NO VÍDEO DO LOBBY DO OPNSENSE SE VOCÊ CONSEGUIU FAZER A CONFIGURAÇÃO COM A SEGUINTE FRASE: Configuração do Lobby Dashboard do OPNsense realizado com sucesso!!! #BoraParaPrática

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
```bash
A) (CHANGE)  = Configuração alterada o seu valor = VALUE ou TEXT
B) (DEFAULT) = Configuração padrão do OPNsense = ON ou OFF, Value OU None
C) (DISABLE) = Desabilitado nessa configuração = OFF
D) (ENABLE)  = Habilitado nessa configuração = ON
E) (REMOVE)  = Removido dessa configuração = Sem valor ou opção
F) <***>     = Botão de confirmação ou de aplicar as configurações
```

Lobby do OPNsense: https://docs.opnsense.org/lobby.html<br>
Guia do Usuário do OPNsense: https://docs.opnsense.org/manual/gui.html<br>
Interface de Usuário Geral: https://docs.opnsense.org/manual/gui.html#<br>
Dashboard do OPNsense: https://docs.opnsense.org/manual/dashboard.html<br>
Senha de Usuário: https://docs.opnsense.org/manual/lobby_password.html<br>

#01_ Autenticando no WebGUI (Web Graphical Unit Interface) do OPNsense<br>
```bash
#utilizar os navegadores para acessar o GUI do OPNsense
firefox ou google chrome: https://192.168.1.1

01. OPNsense
  Username: root
  Password: pti@2018
  <Login>
```

#02_ Conhecendo Lobby e o Dashboard do OPNsense<br>
```bash
01. Lobby
  Dashboard.: Dashboard (Painel) e Widget (Pequeno Programa) padrão do OPNsense
  License...: Licença Padrão do OPNsense e Sistemas Base (FreeBSD, pfSense e m0n0wall)
  Password..: User Settings (Configurações do Usuário) troca de senha (Password) e Linguagem (Language)
  Logout....: Sair (Logout) do WebGUI do OPNsense

02. Lobby/Dashboard
  Toggle Sidebar: (Alternar barra lateral) pra facilitar o uso do Dashboard
  + Add Widget: Adicionar no Dashboard Widgets personalizados
  Restore default layout: Voltar as configurações do Layout do Dashboard
  Padlock (Cadeado): Travar o Layout do Dashboard para mudanças
```

#03_ Personalizando o Dashboard do OPNsense<br>
```bash
<+ Add Widget>
  Coluna 01               Coluna 02               Coluna 03               Coluna 04
  01) System Information  01) Interface           01) Gateways            01) Firewall
  02) CPU                 02) Interface Statics   02) Services            02) Firewall States
  03) Memory              03) Traffic Graph
  04) Disk
<Padlock>
<Save>
```