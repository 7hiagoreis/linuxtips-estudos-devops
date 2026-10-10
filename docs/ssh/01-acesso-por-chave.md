# Acesso SSH por chave

<br></br>

## 1. Instalação do PuTTY

O PuTTY será utilizado como cliente SSH no Windows para acessar a máquina virtual rodando o Ubuntu Server.

### Site oficial

O download do PuTTY foi realizado através do site oficial do projeto ( https://putty.software )

![Site oficial PuTTY](images/01-site-oficial-putty.png)
<p align="right"><i>(Imagem 01: Site oficial PuTTY)</i></p>

<br></br>

### Download

Após clicar no link indicado no passo anterior, o site oficial do PuTTY redireciona para o link =
<p>( https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html )</p>

Este site é do servidor original hospedado pelo criador e principal desenvolvedor do software, Simon Tatham.


![Página de download do PuTTY](images/02-pagina-download-putty.png)
<p align="right"><i>(Imagem 02: Página oficial de download do PuTTY)</i>

<br></br>

Na página de download, o arquivo executável com a instalação padrão fica em Package Files, neste laboratório utilizaremos a versão 64-bit x86.

![Package Files](images/03-package-files.png)
<p align="right"><i>(Imagem 03: Package Files / PuTTY)</i>

<br></br>

#### Alternative Binary Files (Putty Portável)

Existe a versão "*portable*" (portável) do PuTTY, é possível fazer o download desta versão na seção Alternative Binary Files.

![Alternative Binary Files](images/04-alternative-binary-files.png)
<p align="right"><i>(Imagem 04: Alternative Binary Files / PuTTY)</i>

<br></br>

#### Local do executável PuTTY 

O Windows geralmente salva os arquivos baixados da internet na pasta "Downloads", acesse o local onde foi salvo o instalador do PuTTY e execute o programa para iniciar o processo de instalação.

![Acessando a pasta Downloads](images/05-acessando-putty-pasta-download.png)
<p align="right"><i>(Imagem 05: Local onde foi salvo o instalador do PuTTY)</i>

<br></br>

### Instalação

Ao executar o instalador do PuTTY, o Windows pode solicitar uma confirmação para continuar, confirme para prosseguir.

Inicialmente, o instalador exibe a tela de boas vindas. Clique em "*Next*" (Avançar) para começar este processo.

<p align="center"> <img src="images/06-tela-de-boas-vindas-putty.png" alt="Tela de Boas Vindas do PuTTY"> </p>
<p align="right"><i>(Imagem 06: Tela de boas vindas / Instalando o PuTTY)</i>

<br></br>

### Local de instalação

O próximo passo é definir o local de instalação do PuTTY, neste exemplo vamos instalar no diretório padrão ( C:\Program Files\PuTTY\ ), sem fazer nenhuma alteração.

Clique em "*Next*" (Avançar) para continuar.

<p align="center"> <img src="images/07-local-de-instalacao-putty.png" alt="Local de instalação do PuTTY"> </p>
<p align="right"><i>(Imagem 07: Local de instalação do PuTTY)</i>

<br></br>

### Product Features / Recursos do Produto

Agora o instalador do PuTTY vai apresentar a seção "*Product Features*" (Recursos do Produto), aqui podemos escolher quais componentes e ferramentas extras do PuTTY desejamos instalar ou ativar no computador.

<p align="center"> <img src="images/08-selecionando-features.png" alt="Recursos Extras / Instalação do PuTTY"> </p>
<p align="right"><i>(Imagem 08: Recursos Extras / Instalação do PuTTY)</i>

<br></br>

### Adicionando atalho na Área de Trabalho

Antes de avançarmos para a próxima etapa, vamos habilitar o recurso para adicionar um atalho do PuTTY a área de trabalho do Windows.

Clique na opção "*Add shortcut to PuTTY on the Desktop*" (Adicionar atalho para o PuTTY na área de trabalho), em seguida selecione a opção "*Will be installed on local hard drive*" (Será instalado no disco rígido local), conforme a imagem abaixo.

<p align="center"> <img src="images/09-definindo-feature-icones-area-de-trabalho.png" alt="Adicionando ícone do PuTTY na área de trabalho"> </p>
<p align="right"><i>(Imagem 09: Recursos Extras / Adicionando ícone do PuTTY na área de trabalho)</i>

<br></br>

Depois de selecionar o recurso para criar um ícone do PuTTY na área de trabalho, clique em "*Install*" (Instalar) para iniciar o processo.

<p align="center"> <img src="images/10-feature-icone-definida.png" alt="Ícone do PuTTY na área de trabalho"> </p>
<p align="right"><i>(Imagem 10: Recursos Extras / Ícone do PuTTY na área de trabalho)</i>

<br></br>

### Confirmação para iniciar

O Windows nesta etapa, após clicar para instalar o PuTTY, pode solicitar a confirmação para continuar. Caso a janela do Controle de Conta de Usuário (UAC) apareça, basta clicar em Sim para autorizar o instalador.

<br></br>

### Instalando...

Agora, aguarde enquanto o instalador copia os arquivos para o seu computador. Assim que a barra de progresso estiver cheia, a tela final será exibida automaticamente.

<p align="center"> <img src="images/11-instalando-putty-progresso.png" alt="Instalando o PuTTY"> </p>
<p align="right"><i>(Imagem 11: Instalando o PuTTY)</i>

<br></br>

### Instalação finalizada

Pronto! O PuTTY foi instalado com sucesso no seu computador. 

<p align="center"> <img src="images/12-instalacao-finalizada.png" alt="Instalação do PuTTY finalizada"> </p>
<p align="right"><i>(Imagem 12: Instalação do PuTTY finalizada)</i>

<br></br>

Caso você não queira ler as notas de lançamento do programa, desmarque a opção <kbd>View README file</kbd> e clique no botão <kbd>Finish</kbd> para fechar o instalador.

<p align="center"> <img src="images/13-desmarcando-o-readme.png" alt="Desmarcando o Readme do PuTTY"> </p>
<p align="right"><i>(Imagem 13: Desmarcando o Readme do PuTTY)</i>

<br></br>

### Primeira utilização do PuTTY

Para abrir o PuTTY clique no ícone que está em sua área de trabalho, ou digite PuTTY na barra de pesquisa do sistema operacional Windows.

<p align="center"> <img src="images/14-putty-na-area-de-trabalho.png" alt="Desmarcando o Readme do PuTTY"> </p>
<p align="right"><i>(Imagem 14: Representação do PuTTY na área de trabalho no Windows)</i>

<br></br>

### Tela principal do PuTTY

Abaixo imagem da tela principal do PuTTY.

<p align="center"> <img src="images/15-tela-principal-putty.png" alt="Tela principal do PuTTY"> </p>
<p align="right"><i>(Imagem 15: Tela principal do PuTTY)</i>

---

<br></br>

## 2. Primeiro acesso ao Ubuntu Server

### Configuração da Rede na Máquina Virtual

Inicialmente, a máquina virtual estava configurada com a opção NAT no VirtualBox.

O NAT permite que a máquina virtual acesse a internet utilizando a conexão de rede do computador físico. Nesse modo, a máquina virtual (VM) fica atrás de uma camada de tradução de endereços de rede, e as conexões iniciadas de fora para dentro não são encaminhadas automaticamente.

Durante a configuração do laboratório, o Ubuntu Server conseguia acessar a internet, mas não consegue estabelecer uma conexão via SSH diretamente do Windows para a máquina virtual utilizando o seu endereço IP.

#### NAT (Network Address Translation)

No modo NAT, o VirtualBox permite que a máquina virtual utilize a conexão de rede do computador físico para acessar outros dispositivos e serviços.

Porém, para iniciar uma conexão SSH do Windows para a máquina virtual (VM), é necessário configurar o redirecionamento de portas no VirtualBox.

Por exemplo, seria possível encaminhar a porta `2222` do computador físico para a porta `22` da máquina virtual:

```text
Windows
   |
   | SSH para localhost:2222
   v
VirtualBox
   |
   | Redirecionamento de porta
   v
Ubuntu Server
   |
   | Porta 22
   v
Servidor SSH
```

Nesse cenário, a conexão seria configurada no PuTTY utilizando `127.0.0.1` como endereço e `2222` como porta, desde que a regra de redirecionamento esteja configurada.

#### Bridge (Placa em modo Bridge)

Para este laboratório, foi alterada a interface de rede da máquina virtual de NAT para Bridge, também chamado de modo bridge ou placa em modo bridge no VirtualBox.

Nesse modo, a máquina virtual pode participar diretamente da rede local, como outro dispositivo na rede conectado, e com endereço IP próprio.

Isso permite que o Windows estabeleça uma conexão SSH diretamente com o endereço IP da máquina virtual, desde que a rede, o firewall e o servidor SSH permitam a conexão.

Após alteração, é possível estabelecer a conexão de acesso remoto via SSH no Ubuntu Server.

#### Comparação entre NAT e Bridge

| Característica | NAT | Bridge |
|---|---|---|
| Acesso da VM à internet | Sim | Sim, se a rede permitir |
| IP próprio na rede local | Normalmente não, fica atrás do NAT do VirtualBox | Sim, normalmente obtido por DHCP |
| SSH do Windows para a VM | Geralmente exige redirecionamento de portas | Pode usar diretamente o IP da VM |
| Configuração para este laboratório | Exige uma etapa adicional | Mais direta para acesso pela rede local |

O NAT também permite outras formas de acesso, dependendo da configuração. A principal diferença é que o redirecionamento de portas precisa ser configurado quando desejar receber conexões externas na VM.

Neste laboratório, o modo Bridge foi utilizado para simplificar o acesso SSH do Windows ao Ubuntu Server.

<br></br>

#### Problemas de conectividade no modo Bridge

Durante os testes em outro computador, um Dell XPS 8700, encontrei dificuldades para estabelecer a conexão com a máquina virtual utilizando o modo Bridge.

O computador possui interfaces de rede Ethernet e Wi-Fi. Uma das possibilidades que pretendo investigar é se a seleção do adaptador de rede no VirtualBox está relacionada ao problema.

Também tentei configurar um endereço IP manualmente, mas a conexão não funcionou como esperado.

A causa ainda não foi identificada. Pretendo realizar novos testes para verificar a configuração das interfaces de rede, a seleção do adaptador utilizado pelo VirtualBox e os parâmetros de rede da máquina virtual.

Após os testes, esta seção será atualizada com os resultados e a solução encontrada, caso seja possível identificar a causa.

<br></br>

### Descobrindo o IP com ip addr
### Configurando o PuTTY
### Primeiro login

---

## 3. Gerando a chave SSH
### PuTTYgen
### Chave pública
### Chave privada

---

## 4. Instalando a chave no Ubuntu
### ssh-copy-id
### authorized_keys

## 5. Testando o acesso por chave

## 6. Configurando o ~/.ssh/config

## 7. Resultado
