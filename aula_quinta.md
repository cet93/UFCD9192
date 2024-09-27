
![analise_vulnerabilidade_init](./assets/images/analise_vulnerabilidade_init_00.webp)

---

# RED HAT

> Red Hat é uma empresa de tecnologia que desenvolve soluções de software de código aberto, conhecida principalmente por seu sistema operacional Red Hat Enterprise Linux (RHEL). A empresa oferece produtos e serviços voltados para infraestrutura de TI, nuvem, virtualização e containers, com um forte foco em soluções baseadas em Linux.

# PFSENSE

> O pfSense é um firewall de código aberto e uma distribuição de roteamento baseada no sistema operacional FreeBSD. Ele oferece uma solução completa para gerenciamento de rede.

[__Documentação pfSense__](https://docs.netgate.com/pfsense/en/latest)

## Instalação

- Init

![pfSense init](./assets/images/pfsense_images/pfsense_00.png)

- Install

![pfSense install](./assets/images/pfsense_images/pfsense_01.png)

- Auto UFS

![pfSense auto ufs](./assets/images/pfsense_images/pfsense_02.png)

- Entire Disk

![pfSense entire disk](./assets/images/pfsense_images/pfsense_03.png)

- MBR DOS Partition

![pfSense mbr dos partition](./assets/images/pfsense_images/pfsense_04.png)

- Finish

![pfSense finish](./assets/images/pfsense_images/pfsense_05.png)

- Commit

![pfSense commit](./assets/images/pfsense_images/pfsense_06.png)

- Installer Progress

![pfSense installer progress](./assets/images/pfsense_images/pfsense_07.png)

- Installation Complete Reboot

![pfSense installation complete reboot](./assets/images/pfsense_images/pfsense_08.png)

- Screen Init

![pfSense screen init](./assets/images/pfsense_images/pfsense_09.png)

> __WAN__: WAN (Wide Area Network) é uma rede de comunicação que cobre uma grande área geográfica, como um país, continente ou até o mundo. Ela conecta várias redes locais (LANs) em diferentes locais, permitindo que dispositivos em regiões distantes se comuniquem.

> __LAN__: LAN (Local Area Network) é uma rede de comunicação que conecta dispositivos, como computadores e impressoras, em uma área geográfica limitada, como uma casa, escritório ou escola. Ela permite o compartilhamento de recursos e a comunicação rápida entre os dispositivos conectados.

- Interface Configuration

__option 2__

![pfSense interface configuration](./assets/images/pfsense_images/pfsense_10.png)

- LAN Configuration

__option 2__

__DHCP no__

__ip: 172.20.27.254/24__

> Observação: É necessário colocar a máscara subnet (como /24) junto ao ip, pois se faltar o pfsense irá perguntar qual é o subnet mask.

![pfSense lan configuration 00](./assets/images/pfsense_images/pfsense_11.png)

__For a lan ENTER for none enter__

__Configuration IPv6/DHCP6 no__

__LAN IPv6 ENTER for none enter__

__Enable DHCP for LAN no__

__Revert to HTTP yes__

![pfSense lan configuration 01](./assets/images/pfsense_images/pfsense_12.png)

![pfSense lan configuration 02](./assets/images/pfsense_images/pfsense_13.png)

__Enter para finalizar enter__

![pfSense lan configuration 03](./assets/images/pfsense_images/pfsense_14.png)

_LAN configurada._

- Teste ping do Windows Server para o pfSense

![ping win server pfsense](./assets/images/pfsense_images/pfsense_15.png)

> Observação: Ambos devem estar na mesma rede, nesse cenário temos o pfsense com 2 placas de rede (1 NAT e 1 LAN Segment), e o Windows Server temos 1 placa de rede (1 LAN Segment) na mesma rede do pfsense.

- Página web do pfSense

![pfsense web page](./assets/images/pfsense_images/pfsense_16.png)

_log in padrão pfSense_

![pfsense login padrão](./assets/images/pfsense_images/pfsense_17.png)

- Setup pfSense

![pfsense setup](./assets/images/pfsense_images/pfsense_18.png)

_Support pfSense_

![pfsense support](./assets/images/pfsense_images/pfsense_19.png)

_General Information pfSense_

![pfsense general information](./assets/images/pfsense_images/pfsense_20.png)

> Observação: Configure o __Hostname__, __Domain__, Primary/Secondary __DNS__ e __Override DNS__ de acordo com a __sua__ rede, é de __sua__ responsabilidade saber sobre a rede em que estar a trabalhar.

_Time Server Information pfSense_

![pfsense ntp](./assets/images/pfsense_images/pfsense_21.png)

> __NTP__: Network Time Protocol é um protocolo utilizado para sincronizar o relógio de dispositivos em uma rede. Ele garante que todos os computadores, servidores e outros dispositivos estejam com a mesma hora exata.

_Configure WAN Interface_

![pfsense wan interface](./assets/images/pfsense_images/pfsense_22.png)

> Observação: Nessa página nada foi feito, nada configurado/alterado. Scroll para baixo e clicar no botão `Next`.
> Pois essa página é de rede pública, ISP é responsável.

>__ISP__: Internet Service Provider é a empresa que fornece acesso à internet para indivíduos e organizações, fornecem a conexão à internet por meio de diferentes tecnologias.

_Configure LAN Interface_

![pfsense lan interface](./assets/images/pfsense_images/pfsense_23.png)

> IP da LAN e Máscara da subrede configurados.

_Configure Password Admin_

![pfsense password admin](./assets/images/pfsense_images/pfsense_24.png)

_Reload Configuration_

![pfsense reload configuration](./assets/images/pfsense_images/pfsense_25.png)

_Reload Progress_

![pfsense reload progress](./assets/images/pfsense_images/pfsense_26.png)

_Finish_

![pfsense finish](./assets/images/pfsense_images/pfsense_27.png)

> Observação: Caso a página web do pfsense estiver offline após essa etapa, faça o reboot do pfsense, clicar __option 8__ para acessar ao __shell__ e digite o comando __reboot__.

![pfsense reboot](./assets/images/pfsense_images/pfsense_29.png)

_Copyright_

![pfsense copyright](./assets/images/pfsense_images/pfsense_28.png)

- Dashboard pfSense

![pfsense dashboard](./assets/images/pfsense_images/pfsense_30.png)

> __FQDN__: Fully Qualified Domain Name é o nome de domínio completo, que inclui o nome do host e o nome de domínio.
> __TLD__: Top-Level Domain é a parte final de um nome de domínio na internet.

_Exemplo_:
- __pfsense__ é o __hostname__.
- __hacking.local__ é o __nome de domínio__.
- __com__ é o __TLD__.
 
---
---

- Windows Server 2022 Preferred/Alternade DNS

> Verifique na placa de rede do Windows Server se a configuração do __Preferred DNS Server__ e __Alternate DNS Server__ ou mantiveram as configurações feitas para os DNS ou foi feito o override automaticamente voltando para o __IP Loopback__ `127.0.0.1`. Se tiver feito o override, reconfigure os DNS (novamente) de acordo com a __sua__ rede, em `Internet Protocol Version 4 (TCP/IPv4)` acessando suas propriedades.

![windows server dns loopback](./assets/images/windows_server_2022_images/windows_server_2022_00.png)

> __IP Loopback 127.0.0.1__: é um endereço IP especial que aponta para o próprio dispositivo em que ele é usado, chamado de "localhost", ele é utilizado para testar e diagnosticar a conectividade de rede local, sem precisar de uma rede externa.

<!-- - Windows Server 2022 Configurando __DHCP__

> __DHCP__: Dynamic Host Configuration Protocol é um protocolo que automaticamente atribui endereços IP e outras configurações de rede a dispositivos em uma rede. -->










### DNS

> DNS (Domain Name System) é o sistema que traduz nomes de domínio legíveis (como www.exemplo.com) em endereços IP numéricos (como 192.168.1.1) que os computadores usam para se comunicar entre si, funciona como uma "agenda telefônica" da internet.

### ACTIVE DIRECTORY AD

> Active Directory (AD) é um serviço da Microsoft que gerencia e organiza redes de computadores em ambientes corporativos. Ele permite que administradores controlem o acesso a recursos. O AD usa um banco de dados centralizado para armazenar informações sobre contas de usuário, computadores e outros objetos da rede, facilitando a gestão e segurança de grandes redes empresariais.

##### DOMAIN/FOREST

> __Domain__ é o grupo básico de objetos como usuários, computadores e recursos que compartilham uma mesma política de segurança e autenticação. É o nível mais comum de organização no AD.

> __Forest__ é o conjunto de um ou mais domains que compartilham uma mesma estrutura de diretório, mas podem ter políticas e regras diferentes. Um forest pode conter vários domains e serve como o nível mais alto de organização no AD.


### DOMAIN CONTROLLER OPTIONS

### FOREST FUNCTIONAL LEVEL

### DOMAIN FUNCTIONAL LEVEL

### FAILOVER

### LOAD BALANCING

### DOMAIN CONTROLLER
