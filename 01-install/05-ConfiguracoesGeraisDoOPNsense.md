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
Data de criação: 06/10/2024<br>
Data de atualização: 07/10/2024<br>
Versão: 0.02<br>
Testado e homologado para a versão do OPNsense 24.7

Conteúdo estudado nessa instalação:<br>
#01_ Autenticando no WebGUI (Web Graphical Unit Interface) do OPNsense<br>
#02_ Configurações Básicas de Administração do OPNsense<br>
#03_ Configurações Básicas Gerais do OPNsense<br>
#04_ Configurações Básicas Variadas/Diversos do OPNsense<br>

OBSERVAÇÃO IMPORTANTE: COMENTAR NO VÍDEO DO UPDATE DO OPNSENSE SE VOCÊ CONSEGUIU FAZER A ATUALIZAÇÃO COM A SEGUINTE FRASE: Configurações Gerais do OPNsense realizado com sucesso!!! #BoraParaPrática

#boraparapratica #boraparaprática #vaamonde #robsonvaamonde #procedimentosemti #opnsense #firewall #desafiovaamonde #desafioboraparapratica #desafioopnsense #migracaoopnsense

Site Oficial do OPNSense: https://opnsense.org/<br>
Releases do OPNsense: https://docs.opnsense.org/releases.html<br>
Roadmap do OPNsense: https://opnsense.org/about/road-map/<br>
Blog Oficial do OPNsense: https://opnsense.org/blog/

Versão 24.7 do OPNsense: https://forum.opnsense.org/index.php?topic=42787.msg212371#msg212371

Começando com o OPNsense: https://opnsense.org/users/get-started/<br>
Documentação Oficial do OPNsense: https://docs.opnsense.org/

[![Configurações OPNsense](http://img.youtube.com/vi//0.jpg)]( "Configurações OPNsense")

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

Configurações do Sistema do OPNsense: https://docs.opnsense.org/system.html<br>

#01_ Autenticando no WebGUI (Web Graphical Unit Interface) do OPNsense<br>
```bash
#utilizar os navegadores para acessar o GUI do OPNsense
firefox ou google chrome: https://192.168.1.1

01. OPNsense
  Username: root
  Password: pti@2018
  <Login>
```

#02_ Configurações Básicas de Administração do OPNsense<br>
```bash
01. System
  Settings
    Administration
      #configurações básicas do Web GUI
      Web GUI
        Protocol: HTTPS (Default)
        SSL Certificate: Web GUI TLS certificate (Default)
        SSL Ciphers: System defaults (Default)
        HTTP Strict Transport Security: (OFF) Enable HTTP Strict Transport Security (Default)
        TCP port: 10443 (Change)
        HTTP Redirect: (OFF) Disable web GUI redirect rule (Default)
        Login Messages: (OFF) Disable logging of web GUI successful logins (Default)
        Session Timeout: 240s (Default)
        DNS Rebind Check: (OFF) Disable DNS Rebinding Checks (Default)
        Alternate Hostnames: (Default)
        HTTP Compression: (OFF) (Default)
        Access log: (ON) Enable access log (Enable)
        Server Log (ON) Log server erros (Default)
        Listen Interfaces: All (recommended) (Default)
        HTTP_REFERER enforcement: (OFF) Disable HTTP_REFERE enforcement check (Default)
      #configurações básicas do Secure Shell
      Secure Shell
        Secure Shell Server: (ON) Enable Secure Shell (Enable)
        Login Group: wheel, admins (Default)
        Root Login: (ON) Permit root user login (Enable)
        Authentication Method: (ON) Permit password login (Enable)
        SSH Port: 10222 (Change)
        Listen Interfaces: LAN (Change)
      #configurações básicas do Console
      Console
        Console driver: (ON) Use the virtual terminal driver (vt) (Default)
        Primary Console: VGA Console (Default)
        Secondary Console: Serial Console (Enable)
        Serial Speed: 115200 (Default)
        USB-based serial: (ON) Use USB-based serial ports (Enable)
        Console menu: (ON) Password protect the console menu (Default)
      #configurações básicas do Shell
      Shell
        Inactivity timeout: 5m (Enable)
      #configurações básicas de Autenticação
      Authentication
        Server: Local database (Change)
                (OFF) Disable integrated authentication (Default)
        Sudo: Ask password (Change)
              wheels, admins (Change)
        User OTP seed: admins (Change)
      #configurações básicas de Implantação
      Deployment
        Deployment type: Production (Default)
    <Save>
```

#03_ Configurações Básicas Gerais do OPNsense<br>
```bash
01. System
  Settings
    General
      #configurações básicas de Sistema
      System
        Hostname: fwvaamonde (Default)
        Domain: pti.intra (Default)
        Time zone: America/Sao_Paulo (Default)
        Language: English (Default)
        Theme: opnsense (Default)
        Picture: vaamonde (Default)
      #configurações básicas de Confiança
      Trust
        Store intermediate: (OFF) (Default)
      #configurações básicas de Rede
      Networking
        Prefer IPv4 over IPv6: (OFF) Prefer to use IPv4 even if IPv6 is available (Default)
        DNS servers
          DNS server 01: 8.8.8.8 - Use gateway: none (Default)
          DNS server 02: 8.8.4.4 - USe gateway: nome (Default)
        DNS search domain: (Default)
        DNS server options:
          (OFF) Allow DNS server list to be overridden by DHCP/PPP on WAN (Default)
          (OFF) Do not use the local DNS service as a nameserver for this system (Default)
          (OFF) Allow default gateway switching (Default)
    <Save>
```

#04_ Configurações Básicas Variadas/Diversos do OPNsense<br>
```bash
01. System
  Settings
    Miscellaneous
      #configurações básicas de Criptografia
      Cryptography settings
        Hardware acceleration: Nome (Default)
      #configurações básicas de Sensores de Temperatura
      Thermal Sensors
        Hardware: Nome/ACPI (Default)
      #configurações básicas de Período de Backup
      Periodic Backups
        Periodic RRD Backup: Disabled (Default)
        Periodic DHCP Leases Backup: Power off (Default)
        Periodic NetFlow Backup: (Default)
        Periodic Captive Portal Backup: Power off (Default)
      #configurações básicas de Economia de Energia
      Power Savings
        Use PowerD: (OFF) (Default)
        On AC Power Mode: Hiadaptive (Default)
        On Battery Power Mode: Hiadaptive (Default)
        On Normal Power Mode: Hiadaptive (Default)
      #configurações básicas de HD e Memória
      Disk / Memory Settings (reboot to apply changes)
        Swap file: (OFF) Add a 2 GB swap file to the system (Default)
        /var/log RAM disk (OFF) Use memory file system for /var/log (Default)
        /var/log RAM usage: 50 (Default)
        /tmp RAM disk: (OFF) Use memory file system for /tmp (Default)
        /tmp RAM usage: 50 (Default)
      #configurações básicas de Alertas Sonoros
      System Sounds
        Startup/Shutdown Sound: (OFF) Disable the startup/shutdown beep (Default)
    <Save>