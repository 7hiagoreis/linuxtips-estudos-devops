# Laboratório com Oracle VirtualBox e Ubuntu Server

Este guia mostra, de forma prática, o processo de instalação do Oracle VirtualBox no Windows, a criação e configuração de uma máquina virtual e a instalação do Ubuntu Server.

A proposta é montar um ambiente de laboratório usando recursos do próprio computador, permitindo rodar um sistema Linux de forma isolada dentro do Windows.

Esse tipo de ambiente é útil para estudar Linux, servidores, redes, Docker, DevOps e outras áreas ligadas à infraestrutura.

---

<br></br>

## O que é virtualização

Virtualização é uma tecnologia que permite criar computadores virtuais dentro de um computador físico.

Em vez de instalar um sistema operacional direto no hardware, usamos um software de virtualização para criar uma máquina virtual com recursos próprios, como memória RAM, processador, armazenamento e interface de rede.

Neste laboratório, o computador físico usa Windows como sistema principal. Dentro dele roda o Oracle VirtualBox, que cria e executa uma máquina virtual com Ubuntu Server.

De forma simplificada, a estrutura fica assim:

```
Computador físico
       |
       v
    Windows
       |
       v
   VirtualBox
       |
       v
Máquina Virtual
       |
       v
Ubuntu Server
```

---

<br></br>

## O que é o Oracle VirtualBox

O Oracle VirtualBox é uma plataforma de virtualização que permite criar e executar máquinas virtuais em um computador físico.

Uma máquina virtual usa recursos do computador hospedeiro para funcionar. Esses recursos podem ser distribuídos conforme a necessidade do laboratório, como quantidade de memória RAM, processadores virtuais, espaço em disco e configuração de rede.

Durante este guia, alguns conceitos aparecem com frequência:

- **Host**: computador físico onde o VirtualBox está instalado.
- **Guest**: sistema operacional que roda dentro da máquina virtual.
- **Máquina virtual**: computador virtual criado pelo VirtualBox.
- **Virtualização**: tecnologia usada para disponibilizar recursos virtuais para a máquina.

---

<br></br>

## Pré-requisitos

Antes de começar, vale conferir se o computador tem recursos suficientes para rodar uma máquina virtual.

- Windows compatível com a versão do VirtualBox utilizada.
- Processador com suporte à virtualização.
- Memória RAM disponível para o sistema convidado.
- Espaço livre em disco.
- Permissão para instalar programas no Windows.
- Conexão com a internet para baixar os instaladores e a imagem ISO do Ubuntu Server.

A máquina virtual compartilha os recursos do computador físico. Por isso, a quantidade de RAM, capacidade de processamento e espaço em disco devem ser consideradas antes de definir a configuração.

![Representação do computador físico](images/01-print-do-windows.png)
<p align="right"><i>*(Imagem 01: Representação do computador físico onde será instalado o Oracle VirtualBox)*</i>

---

<br></br>

## Obtendo o instalador do VirtualBox

O primeiro passo é baixar o instalador do Oracle VirtualBox.

A versão usada neste laboratório deve ser obtida direto na página oficial do projeto.

[Página oficial de download do Oracle VirtualBox](https://www.virtualbox.org/wiki/Downloads)

Na página de downloads, localize a opção correspondente ao Windows e faça o download do instalador.

![Site oficial do Oracle VirtualBox](images/02-obtendo-o-virtualbox.png)
*(Imagem 02: Página de download do Oracle VirtualBox)*

---

<br></br>

## Obtendo a imagem ISO do Ubuntu Server

Além do VirtualBox, será necessária uma imagem ISO do Ubuntu Server para instalar o sistema operacional na máquina virtual.

A imagem pode ser obtida direto no site oficial do Ubuntu:

[Página oficial de download do Ubuntu Server](https://ubuntu.com/download/server)

Na página, escolha a versão **Ubuntu Server 22.04 LTS** e faça o download.

Após concluir o download, mantenha o arquivo ISO em um local de fácil acesso. Ele será usado durante a criação e configuração da máquina virtual.

![Página oficial de download da ISO Ubuntu Server](images/03-obtendo-o-ubuntu.png)
*(Imagem 03: Página oficial de download da imagem ISO do Ubuntu Server)*

---

## Local onde o download do VirtualBox foi salvo

Após realizar o download, localize o arquivo de instalação e execute.

O Windows geralmente salva o arquivo na pasta "Donwloads" conforme representação da imagem abaixo.

![Pasta onde foi salvo o download do Oracle VirtualBox](images/04-print-do-local-exe-virtualbox.png)
*(Imagem 04: Local onde está o executavel do Oracle VirtualBox)*

---

## Instalando o VirtualBox

Execute o arquivo de instalação, primeiramente o Windows pode solicitar a autorização para rodar o instalador. Confirme para iniciar o processo.

![Executando o Oracle VirtualBox](images/05-print-rodando-exe-virtualbox.png)
*(Imagem 05: Executando a instalação do Oracle VirtualBox)*

---

## Tela de Boas Vindas do VirtualBox

Após confirmar a execução da etapa anterior, o instalador mostra a tela de boas vindas do Oracle VirtualBox.

Nesta tela o instalador informa que será instalado o VirtualBox no computador, é possível também ver a versão utilizada.  

Clique em "Next" para iniciar o processo de instalação.

![Termos de Licença do Oracle VirtualBox](images/06-tela-de-boas-vindas-virtualbox.png)
*(Imagem 06: Tela de Boas Vindas do Oracle VirtualBox)*

---

## Termos de licença

Nesta etapa, o instalador mostra os termos de licença do Oracle VirtualBox.

Leia os termos e marque a opção de aceite para continuar.

![Termos de Licença do Oracle VirtualBox](images/07-aceite-dos-termos-virtualbox.png)
*(Imagem 07: Termos de licença do Oracle VirtualBox)*

---

## Selecionando os componentes

O instalador mostra os componentes que serão instalados junto com o VirtualBox.

Para este laboratório, as opções padrão podem ser mantidas.

Entre os componentes estão os recursos necessários para executar as máquinas virtuais, suporte à rede virtual e integração com alguns dispositivos.


### Diretório de instalação

Nesta etapa é possível definir o diretório onde o VirtualBox será instalado.

Para este laboratório, será usado o diretório padrão sugerido pelo instalador.

Caso exista uma necessidade específica, o diretório pode ser alterado conforme a organização do sistema.

![Local de instaação do Oracle VirtualBox](images/08-local-de-instalacao-virtualbox.png)
*(Imagem 08: Definindo o diretório de instalação do Oracle VirtualBox)*

---

## Dependências ausentes (Missing Dependencies)

O instalador pode exibir um aviso sobre dependências ausentes do Python (Python Core / win32api).

Esse aviso está relacionado aos bindings Python do VirtualBox, usados para automação via linha de comando. Para este laboratório, clique em **Yes** (Sim) para continuar a instalação normalmente e ignorar o aviso.

![Aviso de dependências do Oracle VirtualBox](images/09-aviso-dependencias-virtualbox.png)
*(Imagem 09: Aviso sobre dependências do Python no Oracle VirtualBox)*

---

## Componentes de rede

O VirtualBox instala componentes necessários para disponibilizar interfaces de rede virtuais para as máquinas virtuais.

Durante essa etapa, o Windows pode informar que a conexão de rede será temporariamente interrompida enquanto os componentes são instalados.

Confirme a instalação para continuar.


![Aviso sobre a conexão de rede](images/10-aviso-desconectar-rede-virtualbox.png)
*(Imagem 10: Aviso sobre os componentes de rede virtuais)*

---

### Atalhos e associações de arquivos

O instalador permite selecionar atalhos e associações de arquivos que serão criados no Windows.

Para este laboratório, as opções padrão podem ser mantidas.

![Definindo os Atalhos](images/11-atalhos-instalacao-virtualbox.png)
*(Imagem 11: Definindo atalhos e associações de arquivos)*

---

### Pronto para instalar

Após definir as configurações do VirtualBox, o instalador aguarda a confirmação para prosseguir.

Clique em "Install" (Instalar) para iniciar este processo.

![Pronto para instalar](images/12-pronto-para-instalar-virtualbox.png)
*(Imagem 12: Tela de confirmação para iniciar a instalação do Oracle VirtualBox)*

---

### Iniciando a instalação

Depois de revisar as opções, inicie a instalação do VirtualBox.

O instalador copiará os arquivos necessários e fará as configurações.

Dependendo da configuração do Windows, o sistema pode pedir autorização para instalar drivers usados pelo VirtualBox para recursos como interfaces de rede e outros dispositivos. Caso isso ocorra, confirme a instalação.

![Pronto para instalar](images/13-instalando-virtualbox.png)
*(Imagem 13: Iniciando a instalação / barra de progresso)*


---

### Finalizando a instalação

Ao finalizar, o instalador mostra a confirmação de que o Oracle VirtualBox foi instalado.

Finalize o instalador e abra o VirtualBox para começar a configuração do ambiente.

![Finalizando a instalação](images/14-instalacao-finalizada-virtualbox.png)
*(Imagem 14: Finalizando a instalação)*

---

## Abrindo o VirtualBox

Ao abrir o VirtualBox, será apresentada a interface principal do VirtualBox Manager.

Como é uma instalação nova, inicialmente não haverá máquinas virtuais cadastradas.

![Tela Principal Oracle VirtualBox](images/15-tela-inicial-virtualbox-primeira-abertura.png)
*(Imagem 15: Abrindo o VirtualBox / criando a primeira VM)*

---

## Verificando a instalação (opcional)

Além da interface gráfica, o VirtualBox disponibiliza ferramentas de linha de comando.

Uma forma simples de verificar a versão instalada é usar o comando `VBoxManage`

Para fazer a verificação, abra o Prompt de Comando  (CMD) ou o PowerShell do Windows e acesse a pasta:

```bash
cd "C:\Program Files\Oracle\VirtualBox"
```

Após abrir o prompt, digite:

```bash
VBoxManage --version
```

Caso o comando não seja reconhecido, feche e abra novamente o Prompt para que o PATH seja atualizado.

O comando deve mostrar a versão do VirtualBox instalada.


![Tela Principal Oracle VirtualBox](images/16-verificando-a-versao-vb-via-cmd.png)
*(Imagem 16: Verificando a instalação do Oracle VirtualBox pelo Prompt de Comando)*

---

## Criando uma nova máquina virtual

Com o VirtualBox instalado, podemos criar a máquina virtual que será usada neste laboratório.

Na interface principal do VirtualBox, selecione a opção para criar uma nova máquina virtual.

![Tela Principal Oracle VirtualBox](images/17-criando-nova-maquina-virtual.png)
*(Imagem 17: Criando uma nova máquina virtual)*

---

### Definindo o nome e o sistema operacional

Na primeira etapa da criação, informe o nome da máquina virtual e selecione o sistema operacional que será instalado.

Para este laboratório, usaremos o Ubuntu Server.

Defina um nome que facilite a identificação da máquina. Usaremos `ubuntu-lab`.

```
Nome da máquina virtual: ubuntu-lab
Sistema operacional: Linux
Distribuição: Ubuntu (64-bit)
```

![Tela Principal Oracle VirtualBox](images/18-definindo-o-nome-da-vm.png)
*(Imagem 18: Definindo o nome da máquina virtual e o sistema operacional)*

---

### Selecionando a imagem ISO

O VirtualBox permite informar a imagem ISO que será usada para instalar o sistema operacional.

Neste laboratório, será usada uma imagem ISO do Ubuntu Server.

A imagem pode ser obtida direto no site oficial do Ubuntu.

[Página oficial de download do Ubuntu Server](https://ubuntu.com/download/server)

Após o download, selecione a imagem ISO no assistente de criação da máquina virtual.




![Tela Principal Oracle VirtualBox](images/19-selecionando-a-imagem-iso-no-virtualbox.png)
*(Imagem 19: Selecionando a imagem ISO no Oracle VirtualBox)*

---

### Instalação não assistida

O VirtualBox pode oferecer uma instalação automatizada do sistema convidado.

Neste laboratório, será usada a instalação manual do Ubuntu Server, permitindo acompanhar cada etapa do processo.

Caso essa opção seja apresentada, desmarque a instalação não assistida e siga com a configuração manual.


![Tela Principal Oracle VirtualBox](images/20-tela-de-instalacao-vm-instal-nao-assistida.png)
*(Imagem 20: Tela de instalação da máquina virtual, opção de instalação assistida)*

---

### Configurando a memória RAM

A memória RAM da máquina virtual será reservada a partir da memória disponível no computador físico.

Para um laboratório básico com Ubuntu Server, uma quantidade moderada de memória costuma ser suficiente. A configuração deve levar em conta a memória total disponível no computador.

Neste laboratório, usaremos:

```
Memória RAM da máquina virtual: 2048 MB
```
![Tela Principal Oracle VirtualBox](images/21-definindo-o-tamanho-da-memoria.png)
*(Imagem 21: Tela de criação da VM, definindo o tamanho da memória RAM)*

---

### Configurando os processadores

Assim como a memória, os processadores usados pela máquina virtual são recursos disponibilizados pelo computador físico.

Para este laboratório, usaremos:

```
Processadores virtuais: 2
```

![Tela Principal Oracle VirtualBox](images/22-configurando-os-processadores.png)
*(Imagem 22: Tela de criação da VM, configurando os processadores)*

---

### Definindo o tamanho do disco

A máquina virtual precisa de um dispositivo de armazenamento para instalar o sistema operacional. O VirtualBox usa arquivos no sistema hospedeiro para representar os discos virtuais.

Neste laboratório, será criado um novo disco virtual com 20 GB.

O tamanho pode ser ajustado conforme os recursos disponíveis e a finalidade do laboratório.

```
Tamanho do disco virtual: 20 GB
```

![Tela Principal Oracle VirtualBox](images/23-definindo-o-tamanho-do-disco.png)
*(Imagem 23: Tela de criação da VM, definindo o tamanho do disco)*

---

### Revisando a configuração da máquina virtual

Antes de finalizar a criação, o VirtualBox apresenta um resumo da configuração.

Revise as informações e confirme a criação.

```
Máquina virtual: ubuntu-lab
Memória: 2048 MB
Processadores: 2
Disco virtual: 20 GB
Sistema operacional: Ubuntu Server
```

![Tela Principal Oracle VirtualBox](images/24-resumo-das-configuracoes-da-maquina-virtual.png)
*(Imagem 24: Revisando as configurações da máquina virtual)*

---

## Configurando a máquina virtual

Depois de criar a máquina virtual, ainda é possível alterar várias configurações antes de iniciá-la.

![Tela Principal Oracle VirtualBox](images/25-abrindo-vb-primeiro-acesso.png)
*(Imagem 25: Painel Inicial do Oracle VirtualBox)*


Entre as configurações disponíveis estão:

- Sistema
- Processadores
- Memória
- Armazenamento
- Rede
- Áudio
- USB
- Pastas compartilhadas

Neste laboratório, o foco inicial será a configuração dos recursos necessários para executar o Ubuntu Server.

![Tela Principal Oracle VirtualBox](images/26-configuracoes-vm.png)
*(Imagem 26: Configurando a máquina virtual dentro do Oracle VirtualBox)*

---

### Configurando a rede

A configuração de rede é uma das partes mais importantes de um laboratório de máquinas virtuais.

O VirtualBox oferece diferentes modos de conexão: NAT, Bridge, Host-only e outros, cada um voltado a cenários específicos.

Para este laboratório inicial, será usada a configuração **NAT**.

O modo NAT permite que a máquina virtual use a conexão de rede do computador hospedeiro para acessar recursos externos.

![Tela Principal Oracle VirtualBox](images/27-configurando-a-rede-da-vm.png)
*(Imagem 27: Configurando a rede da máquina virtual no Oracle VirtualBox)*

---

## Iniciando a máquina virtual

Com a configuração concluída, inicie a máquina virtual.

Ao iniciar, o VirtualBox abrirá uma janela correspondente ao computador virtual e fará o processo de inicialização.

![Tela Principal Oracle VirtualBox](images/28-iniciando-a-maquina-virtual.png)
*(Imagem 28: Iniciando a máquina virtual)*

---

## Iniciando a instalação do Ubuntu Server

Com a imagem ISO montada na máquina virtual, o sistema será iniciado pelo instalador do Ubuntu Server.

O instalador apresenta as opções necessárias para configurar o sistema operacional.

![Tela Principal Oracle VirtualBox](images/29-iniciando-vm-ubuntu.png)

*(Imagem 29: Iniciando a instalação do Ubuntu Server na máquina virtual)*

---

### Selecionando o idioma

O instalador pede a escolha do idioma que será usado durante a instalação.

Selecione o idioma desejado e continue.

![Tela Principal Oracle VirtualBox](images/30-definindo-o-idioma-instalacao.png)
*(Imagem 30: Definindo o idioma padrão do sistema durante a instalação)*

---

### Configurando o teclado

Durante a instalação, o Ubuntu Server também pede informações sobre o layout do teclado.

Selecione a opção correspondente ao teclado que será usado.

![Tela Principal Oracle VirtualBox](images/31-configurando-teclado-vm.png)
*(Imagem 31: Configurando o teclado)*

---

### Escolha o tipo de instalação

Nesta etapa é possível escolher o tipo de instalação para o Ubuntu Server, para o exemplo vamos utilizar a opção padrão.

![Tela Principal Oracle VirtualBox](images/32-tipo-de-instalacao.png)
*(Imagem 32: Escolha o tipo de instalação para o Ubuntu)*

---

### Configurando a rede durante a instalação

O instalador do Ubuntu Server tenta configurar automaticamente a interface de rede da máquina virtual.

Como a máquina está usando NAT no VirtualBox, o sistema deve receber uma configuração de rede automática através do ambiente virtualizado.

![Tela Principal Oracle VirtualBox](images/33-configurando-a-rede-do-sistema.png)
*(Imagem 33: Configurando a rede do sistema durante a instalação)*

---

### Configurando o proxy

As definições de proxy podem ser ignoradas se você não usa proxy na rede local. Configure apenas se necessário.

![Tela Principal Oracle VirtualBox](images/34-tela-de-configuracao-proxy.png)
*(Imagem 34: Tela de configuração de proxy)*

---

### Configurando o espelho do repositório

O instalador pede a confirmação do espelho (mirror) do repositório que será usado.

Escolha o espelho mais próximo da sua região para baixar pacotes mais rápido.

![Tela Principal Oracle VirtualBox](images/35-configuracao-do-espelho.png)
*(Imagem 35: Tela de configuração do espelho do repositório)*

---

### Configurando o disco

O instalador pede a configuração de armazenamento. Para um laboratório inicial, o particionamento guiado pode ser usado para simplificar.

Neste passo, o processo de instalação usará o disco virtual criado antes no VirtualBox.

![Tela Principal Oracle VirtualBox](images/36-iniciando-o-particionador.png)
*(Imagem 36: Iniciando o particionador)*


O particionamento assistido facilita o processo em uma instalação rápida. Neste exemplo, escolhemos o particionamento assistido com uso do disco inteiro.

![Tela Principal Oracle VirtualBox](images/37-definindo-o-particionamento.png)
*(Imagem 37: Definindo o particionamento)*


### Finalizando o particionamento

O sistema apresenta uma visão geral das partições e pontos de montagem. Selecione a opção de finalizar o particionamento e escrever as mudanças no disco. Confirme as alterações e continue.

Em seguida, é necessário confirmar o processo. Observe que todos os dados do disco virtual serão apagados. Selecione o disco a ser particionado.

![Tela Principal Oracle VirtualBox](images/38-confirmando-o-disco-que-sera-usado.png)
*(Imagem 38: Confirmando o disco que será usado na instalação)*

---

### Configurando o usuário

Durante a instalação, será necessário definir informações do usuário do sistema.

O Ubuntu Server não cria usuário root com senha por padrão. Em vez disso, cria um usuário comum com privilégios de sudo.

Defina:

- **Nome do usuário**: o nome que será usado para login.
- **Nome do servidor**: o hostname da máquina.
- **Nome de usuário**: o login (por exemplo, `devops`).
- **Senha**: uma senha para esse usuário.

![Tela Principal Oracle VirtualBox](images/39-configurando-usuario-e-senha-vm.png)
*(Imagem 39: Configurando usuário e senha do sistema)*

---

### Exemplo da criação do usuário

A imagem abaixo é um exemplo de como devemos preencher os campos.

Após definir o nome de usuário e senha, clique em "Concluído".

![Tela Principal Oracle VirtualBox](images/40-exemplo-de-criacao-de-usuario.png)
*(Imagem 40: Exemplo de criação de usuário no processo de instalação)*

---

### Ubuntu Pro

Nesta etapa o instalador informa que é possível atualizar para o Ubuntu Pro.

O Ubuntu Pro é um serviço de assinatura de segurança e conformidade oferecido pela Canonical para estender o suporte ao sistema operacional.

Para este laboratório não é necessário selecionar essa opção.

Marque a opção "Skip for now" e clique em "Continue".

![Tela Principal Oracle VirtualBox](images/41-tela-ubuntu-pro.png)
*(Imagem 41: Etapa do processo de instalação / Opção Ubuntu Pro)*

---

### Configurando o OpenSSH

Agora o instalador do Ubuntu Server pergunta se você quer instalar o servidor OpenSSH.

Para este laboratório, marque a opção para instalar o OpenSSH. Isso permite acessar a máquina virtual via SSH depois.


![Tela Principal Oracle VirtualBox](images/42-configurando-o-ssh.png)
*(Imagem 42: Tela de configuração do OpenSSH)*

---

### Selecionando Snaps

O Ubuntu Server permite instalar alguns **Snaps** (pacotes de software isolados em containers, projetados para uma instalação simples e segura) pré-configurados durante a instalação.

Para este laboratório, nenhum Snap adicional é necessário. Pule essa etapa.

![Tela Principal Oracle VirtualBox](images/43-selecionando-snaps.png)
*(Imagem 43: Tela de seleção de Snaps)*

---

### Instalando o sistema

Depois que as configurações forem definidas, o instalador inicia a instalação dos arquivos do Ubuntu Server no disco virtual.

O tempo necessário depende principalmente do desempenho do computador físico e da configuração da máquina virtual.

![Tela Principal Oracle VirtualBox](images/44-instalando-o-sistema.png)
*(Imagem 44: Instalando o sistema Ubuntu Server)*

---

### Finalizando a instalação

Após a instalação dos pacotes, o instalador mostra uma tela de conclusão.

Escolha a opção de reiniciar o sistema. A máquina virtual irá reiniciar e o Ubuntu Server será carregado a partir do disco virtual.

![Tela Principal Oracle VirtualBox](images/45-finalizando-a-instalacao.png)
*(Imagem 45: Finalizando a instalação do Ubuntu Server)*

---

## Primeiro acesso ao Ubuntu Server

Após a reinicialização, será apresentada a tela de login em modo texto.

Utilize o usuário e a senha definidos durante a instalação.

![Tela Principal Oracle VirtualBox](images/46-tela-de-login-ubuntu-server.png)
*(Imagem 46: Tela de login do Ubuntu Server)*




Depois de digitar o seu usuário e senha e pressionar a tecla "<Enter>", o sistema estará pronto para ser utilizado como ambiente de laboratório.

![Tela Principal Oracle VirtualBox](images/47-apos-login.png)
*(Imagem 47: Representação do sistema operacional Ubuntu Server)*

---

## Verificando o sistema

Acesse o Ubuntu Server e faça algumas verificações básicas para confirmar que o sistema foi instalado corretamente.

Para ver as informações sobre o kernel e a arquitetura do sistema, utilize o comando:

```bash
uname -a
```

![Tela Principal Oracle VirtualBox](images/48-uname-a.png)
*(Imagem 48: Consultando informações do kernel no Ubuntu Server pelo terminal)*

Para ver informações da distribuição instalada:

```bash
cat /etc/os-release
```
![Tela Principal Oracle VirtualBox](images/49-cat-os-release.png)
*(Imagem 49: Consultando informações da distribuição Ubuntu pelo terminal)*

---

### Verificando a memória e os processadores

Para consultar a memória disponível:

```bash
free -h
```

![Tela Principal Oracle VirtualBox](images/50-free-h.png)
*(Imagem 50: Consultando a quantidade de memória disponível utilizando o terminal)*

Para verificar os processadores disponíveis:

```bash
nproc
```
![Tela Principal Oracle VirtualBox](images/51-nproc.png)
*(Imagem 51: Consultando os processadores através do terminal)*

---

### Verificando o armazenamento

O comando `df` permite consultar o espaço utilizado e disponível nos sistemas de arquivos:

```bash
df -h
```

![Tela Principal Oracle VirtualBox](images/52-df-h.png)
*(Imagem 52: Consultando o espaço utilizado e disponível no sistema via terminal)*

---

### Verificando a rede

Para ver as interfaces de rede e os endereços IP configurados:

```bash
ip addr
```

![Tela Principal Oracle VirtualBox](images/53-ip-addr.png)
*(Imagem 53: Verificando a rede do Ubuntu Server no terminal)*

Também podemos testar a comunicação com a internet usando o comando `ping`:

```bash
ping -c 4 ubuntu.com
```

Se houver resposta aos pacotes enviados, a máquina virtual tem conectividade com a internet.

![Tela Principal Oracle VirtualBox](images/54-teste-ping-0004.png)
*(Imagem 54: Teste de ping no terminal do Ubuntu Server)*

---

## Entendendo o ambiente criado

Depois de concluir todas as etapas, temos um computador físico executando Windows como sistema principal. Dentro do Windows está instalado o Oracle VirtualBox, responsável pela camada de virtualização. O VirtualBox disponibiliza recursos virtuais para a máquina, incluindo processador, memória, armazenamento e interface de rede. Dentro dessa máquina virtual está instalado o Ubuntu Server.

A estrutura final do projeto fica assim:

```
Computador físico
       |
       +-- Windows
              |
              +-- VirtualBox
                     |
                     +-- CPU virtual
                     +-- Memória virtual
                     +-- Disco virtual
                     +-- Interface de rede virtual
                     |
                     +-- Ubuntu Server
                            |
                            +-- Sistema operacional
                            +-- Usuário
                            +-- Rede
                            +-- Armazenamento
```

---

## Resultado

Ao final deste laboratório, temos uma máquina virtual com o sistema operacional Ubuntu Server funcionando dentro do Windows por meio do Oracle VirtualBox.

O ambiente criado pode ser usado como base para outros estudos relacionados à administração de sistemas, redes, servidores, containers e DevOps.

![Tela Principal Oracle VirtualBox](images/55-representacao-ubuntu-cli.png)
*(Imagem 55: Representação do sistema operacional Ubuntu Server)*

---

## Utilizando a máquina virtual como laboratório

Uma das principais vantagens desse ambiente é a possibilidade de usar a máquina virtual para fazer experimentos sem modificar diretamente o sistema operacional principal.

A partir do Ubuntu Server instalado, podemos criar diferentes cenários de estudo:

- Administração de sistemas Linux
- Configuração de usuários e permissões
- Gerenciamento de serviços
- Configuração de redes
- Instalação de servidores
- Docker e containers
- Nginx
- PHP
- MariaDB
- Redis
- OpenSearch
- Magento 2
- Automação e práticas de DevOps

Também é possível criar snapshots da máquina virtual antes de fazer alterações importantes. Assim, um estado anterior do laboratório pode ser recuperado caso alguma configuração apresente problemas.

![Tela Principal Oracle VirtualBox](images/56-painel-vb.png)
*(Imagem 56: Painel principal do Oracle VirtualBox para gerenciamento das máquinas virtuais)*

---

## Considerações

A criação de máquinas virtuais é uma das formas mais práticas de montar ambientes para estudos e testes usando um único computador físico.

Neste laboratório, instalamos o Oracle VirtualBox no Windows, criamos uma máquina virtual, definimos os recursos de hardware virtual, configuramos a rede e instalamos o Ubuntu Server.

O resultado é um ambiente Linux isolado que pode ser usado para desenvolver conhecimentos em infraestrutura e experimentar diferentes tecnologias.

Além de facilitar os estudos, a virtualização permite reproduzir ambientes, testar configurações e entender melhor a relação entre sistema operacional, hardware, rede e serviços.

---

## Referências

- [Oracle VirtualBox Downloads](https://www.virtualbox.org/wiki/Downloads)
- [Oracle VirtualBox Documentation](https://www.virtualbox.org/manual/)
- [Oracle VirtualBox Installation Guide](https://www.virtualbox.org/manual/ch01.html)
- [Ubuntu Server Downloads](https://ubuntu.com/download/server)
