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
Inicialmente, a máquina virtual estava configurada com a opção NAT nas configurações de rede do VirtualBox.

<p align="center"> <img src="images/16-redirecionamento-portas-01.png" alt="Tela de configuração da rede no VirtualBox"> </p>
<p align="right"><i>(Imagem: Tela de configuração da rede no VirtualBox)</i>

<br></br>

O NAT permite que a máquina virtual acesse a internet utilizando a conexão de rede do computador físico. Nesse modo, a máquina virtual (VM) fica atrás de uma camada de tradução de endereços de rede, e as conexões iniciadas de fora para dentro não são encaminhadas automaticamente.

Durante a configuração do laboratório, o Ubuntu Server conseguia acessar a internet, mas não conseguia estabelecer uma conexão via SSH diretamente do Windows para a máquina virtual utilizando o seu endereço IP.

---

### Solução 1: Utilizando o Modo NAT com Redirecionamento de Portas
No modo NAT padrão, o VirtualBox esconde a máquina virtual (VM) atrás de uma sub-rede isolada. Para iniciar uma conexão SSH do Windows para a máquina virtual sem alterar o tipo de placa, é obrigatório configurar uma regra de **Redirecionamento de Portas (Port Forwarding)**.

Essa regra instrui o VirtualBox a escutar uma porta específica na máquina física (Host) e repassar todo o tráfego para a porta do SSH (`22`) dentro da máquina virtual.

Por exemplo, encaminhando a porta `2222` do Windows para a porta `22` do Ubuntu Server:

```text
Windows
   |
   | SSH para localhost:2222
   v
VirtualBox (Mapeamento de Porta)
   |
   | Redirecionamento de tráfego
   v
Ubuntu Server
   |
   | Porta 22
   v
Servidor SSH
```

<br></br>

### Passo a Passo da Configuração do NAT
1. Com a VM desligada, abra as **Configurações** dela no VirtualBox.

<p align="center"> <img src="images/17-redirecionamento-portas-02.png" alt="Tela de configuração da rede no VirtualBox"> </p>
<p align="right"><i>(Imagem: Tela de configuração da rede no VirtualBox)</i>

<br></br>

2. Após clicar em configurações o VirtualBox exibe uma nova janela com as opções da máquina virtual do lado esquerdo da tela...

<p align="center"> <img src="images/18-redirecionamento-portas-03.png" alt="Tela de configuração da rede no VirtualBox"> </p>
<p align="right"><i>(Imagem: Tela de configuração da rede no VirtualBox)</i>

<br></br>

3. Clique na aba **Rede** > **Adaptador 1** (Garantir que a opção "Ligado a: NAT" está selecionada).

<p align="center"> <img src="images/18-redirecionamento-portas-04.png" alt="Tela de configuração da rede no VirtualBox"> </p>
<p align="right"><i>(Imagem: Tela de configuração da rede no VirtualBox)</i>

<br></br>

4. Clique no botão **Redirecionamento de Portas**.

<p align="center"> <img src="images/18-redirecionamento-portas-05.png" alt="Tela de configuração da rede no VirtualBox"> </p>
<p align="right"><i>(Imagem: Tela de configuração da rede no VirtualBox)</i>

<br></br>

5. Adicione uma nova regra com os seguintes parâmetros:

<p align="center"> <img src="images/18-redirecionamento-portas-06.png" alt="Tela de configuração da rede no VirtualBox"> </p>
<p align="right"><i>(Imagem: Tela de configuração da rede no VirtualBox)</i>

<br></br>

**Regras de Redirecionamento de Portas**
   * **IP do Hospedeiro:** `127.0.0.1`
   * **Porta do Hospedeiro:** `2222`
   * **IP do Convidado:** (Pode deixar em branco ou preencher com o IP interno da VM, ex: `10.0.2.15`)
   * **Porta do Convidado:** `22`

A imagem abaixo é um exemplo de como preencher os campos da Regra de Redirecionamento.   

<p align="center"> <img src="images/18-redirecionamento-portas-07.png" alt="Tela de configuração da rede no VirtualBox"> </p>
<p align="right"><i>(Imagem: Tela de configuração da rede no VirtualBox)</i>

<br></br>
   
6. Clique em **OK** e inicie a máquina virtual.

<p align="center"> <img src="images/18-redirecionamento-portas-08.png" alt="Tela de configuração da rede no VirtualBox"> </p>
<p align="right"><i>(Imagem: Tela de configuração da rede no VirtualBox)</i>

<br></br>

7. **PuTTY:** Abra o PuTTY e digite no campo *Host Name (or IP address)* o endereço `127.0.0.1`, e no campo *Port*, altere para `2222`. Mantenha a opção padrão no Tipo de Conexão (Connection Type): SSH
Clique em ´Open´ para conectar a máquina virtual.

<p align="center"> <img src="images/18-redirecionamento-portas-09.png" alt="Tela de configuração da rede no VirtualBox"> </p>
<p align="right"><i>(Imagem: Tela de configuração da rede no VirtualBox)</i>

<br></br>

8. **Primeiro Acesso ao PuTTY e Alerta de Segurança (PuTTY Security Alert)**

Na primeira conexão ao servidor, o PuTTY exibirá um aviso de segurança chamado **PuTTY Security Alert**. 

Isso acontece porque o PuTTY ainda não conhece a chave de identificação criptográfica (*host key*) da máquina virtual (VM). Esse comportamento é padrão e serve para garantir que a conexão está correta ao servidor.

<p align="center"> <img src="images/primeiro-acesso-putty-red-portas.png" alt="Tela de configuração da rede no VirtualBox"> </p>
<p align="right"><i>(Imagem: Tela de configuração da rede no VirtualBox)</i>

<br></br>

#### Como proceder:
**Verifique as informações:** O alerta exibirá o algoritmo (ex: `ssh-ed25519` ou `rsa`) e a impressão digital da chave (**SHA256**).
**Escolha a opção ideal:**
   * **Accept (Aceitar):** Salva a chave no registro do seu computador. O PuTTY confiará nesta VM e o alerta **não aparecerá nos próximos acessos**. (Recomendado para este tutorial).
   * **Connect Once (Conectar uma vez):** Permite o acesso apenas para a sessão atual, perguntando novamente no próximo login.
   * **Cancel (Cancelar):** Aborta a conexão se você desconfiar da origem do servidor.

<p>Para este laboratório foi escolhida a opção Accept (Aceitar).</p>

<br></br>

Ao conectar no Ubuntu Server, digite o nome de usuário.

<p align="center"> <img src="images/primeiro-acesso-putty-red-portas-02.png" alt="Tela de configuração da rede no VirtualBox"> </p>
<p align="right"><i>(Imagem: Tela de configuração da rede no VirtualBox)</i>

<br></br>

Digite a senha do usuário. OBS: O campo da senha não exibe caracteres. Após digitar a senha pressione <kbd>ENTER</kbd>

<p align="center"> <img src="images/primeiro-acesso-putty-red-portas-03.png" alt="Tela de configuração da rede no VirtualBox"> </p>
<p align="right"><i>(Imagem: Tela de configuração da rede no VirtualBox)</i>

<br></br>

Pronto! A conexão SSH foi estabelecida no Ubuntu Server.

<p align="center"> <img src="images/primeiro-acesso-putty-red-portas-04.png" alt="Tela de configuração da rede no VirtualBox"> </p>
<p align="right"><i>(Imagem: Tela de configuração da rede no VirtualBox)</i>

<br></br>

---

<br></br>

### Solução 2: Utilizando a Placa em Modo Bridge
Como alternativa para simplificar o acesso e não depender de mapeamento de portas individuais para cada novo serviço, a interface de rede da máquina virtual pode ser alterada de NAT para **Bridge** (Placa em modo Bridge).

<p align="center"> <img src="images/modo-bridge-01.png" alt="Tela de configuração da rede no VirtualBox"> </p>
<p align="right"><i>(Imagem: Tela de configuração da rede no VirtualBox)</i>

<br></br>

Nesse modo, o VirtualBox faz com que a máquina virtual participe diretamente da rede local física, comportando-se como se fosse outro computador real conectado ao roteador, recebendo um endereço IP próprio na mesma faixa do computador hospedeiro.

#### Passo a Passo da Configuração do Bridge:
1. Nas configurações de **Rede** da VM, mude o campo "Conectado a:" de NAT para **Placa em modo Bridge**.

<p align="center"> <img src="images/modo-bridge-02.png" alt="Tela de configuração da rede no VirtualBox"> </p>
<p align="right"><i>(Imagem: Tela de configuração da rede no VirtualBox)</i>

<br></br>

2. No campo **Nome**, selecione a placa de rede ativa do seu computador físico (ex: sua placa de rede (Ethernet) conectada por cabo).

<p align="center"> <img src="images/modo-bridge-03.png" alt="Tela de configuração da rede no VirtualBox"> </p>
<p align="right"><i>(Imagem: Tela de configuração da rede no VirtualBox)</i>

<br></br>

3. Inicie a máquina virtual.

<p align="center"> <img src="images/modo-bridge-04.png" alt="Tela de configuração da rede no VirtualBox"> </p>
<p align="right"><i>(Imagem: Tela de configuração da rede no VirtualBox)</i>

<br></br>

4. No terminal do Ubuntu Server, execute o comando `ip addr` ou `ip a` para identificar o endereço IP recebido via DHCP (ex: `192.168.15.4`).

<p align="center"> <img src="images/modo-bridge-05.png" alt="Tela de configuração da rede no VirtualBox"> </p>
<p align="right"><i>(Imagem: Tela de configuração da rede no VirtualBox)</i>

<br></br>

5. **No PuTTY:** Digite o IP da máquina virtual (VM), obtido com o comando `ip addr` e mantenha a porta padrão `22`. Clique em "Open" para conectar a máquina virtual.

<p align="center"> <img src="images/modo-bridge-06.png" alt="Tela de configuração da rede no VirtualBox"> </p>
<p align="right"><i>(Imagem: Tela de configuração da rede no VirtualBox)</i>

<br></br>

6. **Primeiro Acesso ao PuTTY e Alerta de Segurança (PuTTY Security Alert)**

Na primeira conexão ao servidor, o PuTTY exibirá um aviso de segurança chamado **PuTTY Security Alert**. 

Isso acontece porque o PuTTY ainda não conhece a chave de identificação criptográfica (*host key*) da máquina virtual (VM). Esse comportamento é padrão e serve para garantir que a conexão está correta ao servidor.

<p align="center"> <img src="images/modo-bridge-07.png" alt="Tela de configuração da rede no VirtualBox"> </p>
<p align="right"><i>(Imagem: Tela de configuração da rede no VirtualBox)</i>

<br></br>

#### Como proceder:
**Verifique as informações:** O alerta exibirá o algoritmo (ex: `ssh-ed25519` ou `rsa`) e a impressão digital da chave (**SHA256**).
**Escolha a opção ideal:**
   * **Accept (Aceitar):** Salva a chave no registro do seu computador. O PuTTY confiará nesta VM e o alerta **não aparecerá nos próximos acessos**. (Recomendado para este tutorial).
   * **Connect Once (Conectar uma vez):** Permite o acesso apenas para a sessão atual, perguntando novamente no próximo login.
   * **Cancel (Cancelar):** Aborta a conexão se você desconfiar da origem do servidor.

<br></br>

7. **Digite o nome de usuário e senha**

Sempre que conectar ao PuTTY neste método, ele vai solicitar o nome de usuario e senha cadastrados no Ubuntu Server.

<p align="center"> <img src="images/modo-bridge-08.png" alt="Tela de configuração da rede no VirtualBox"> </p>
<p align="right"><i>(Imagem: Tela de configuração da rede no VirtualBox)</i>

<br></br>

Digite o nome de usuário.

<p align="center"> <img src="images/modo-bridge-09.png" alt="Tela de configuração da rede no VirtualBox"> </p>
<p align="right"><i>(Imagem: Tela de configuração da rede no VirtualBox)</i>

<br></br>

Digite a senha do usuário. OBS: O campo da senha não exibe caracteres. Após digitar a senha pressione <kbd>ENTER</kbd>

<p align="center"> <img src="images/modo-bridge-10.png" alt="Tela de configuração da rede no VirtualBox"> </p>
<p align="right"><i>(Imagem: Tela de configuração da rede no VirtualBox)</i>

<br></br>

Pronto! A conexão SSH foi estabelecida no Ubuntu Server.

<p align="center"> <img src="images/modo-bridge-11.png" alt="Tela de configuração da rede no VirtualBox"> </p>
<p align="right"><i>(Imagem: Tela de configuração da rede no VirtualBox)</i>

<br></br>

Abaixo, a imagem é uma representação do terminal com o comando `ls -lha` para listar todo o conteúdo do diretório incluindo os arquivos ocultos.

<p align="center"> <img src="images/modo-bridge-12.png" alt="Tela de configuração da rede no VirtualBox"> </p>
<p align="right"><i>(Imagem: Representação do Terminal / Ubuntu Server)</i>

<br></br>

---

### Comparação entre NAT e Bridge

| Característica | NAT (Com Redirecionamento) | Bridge |
| :--- | :--- | :--- |
| **Acesso da VM à internet** | Sim | Sim, se a rede local permitir |
| **IP próprio na rede local** | Não, fica oculta atrás do VirtualBox | Sim, obtido via roteador (DHCP) |
| **Acesso via PuTTY** | Através de `127.0.0.1` na porta `2222` | Diretamente pelo IP da VM na porta `22` |
| **Acesso a novos serviços (ex: Web)** | Exige criar novas regras para cada porta | Livre, basta acessar o IP da VM |

---

<br></br>

## Problemas de Conectividade no Modo Bridge (Identificado e Resolvido)
Durante os testes em outro computador, um Dell XPS 8700, foram encontradas dificuldades para estabelecer a conexão com a máquina virtual utilizando o modo Bridge. O Ubuntu Server não recebia um endereço IP válido da rede local ou, mesmo recebendo, o Windows não conseguia pingar ou conectar via PuTTY.

* **Causa Raiz:** O computador físico estava conectado à rede exclusivamente via **Wi-Fi**. O padrão técnico de redes sem fio (IEEE 802.11) foi projetado para associar apenas **um endereço MAC por conexão**. Quando o VirtualBox tenta simular um segundo endereço MAC (da máquina virtual / VM) através da placa Wi-Fi do hospedeiro, a maioria dos roteadores residenciais e placas de rede rejeita essa requisição por segurança ou limitação de hardware, impedindo a comunicação direta em Modo Bridge.

<p align="center"> <img src="images/desativa-rede-wi-fi-001.png" alt="Tela de configuração da rede no VirtualBox"> </p>
<p align="right"><i>(Imagem: Representação do Terminal / Ubuntu Server)</i>

<br></br>

---

### Solução Adotada no Laboratório
Para contornar o problema de conectividade sem abrir mão da facilidade do acesso direto via IP (sem redirecionamento de portas), a solução adotada foi corrigir a seleção do adaptador de rede físico dentro do VirtualBox, garantindo que a ponte (Bridge) fosse feita exclusivamente através da conexão cabeada.

```
                  +---------------------------------------+

                  |           Máquina Virtual             |
                  |           (Ubuntu Server)             |
                  +-------------------+-------------------+
                                      |
                                      v
                        +---------------------------+

                        |   Placa em modo Bridge    |
                        +-------------+-------------+
                                      |
                                      v
                        +---------------------------+

                        | Adaptador Físico Realtek  |
                        |      (Cabo de Rede)       |
                        +-------------+-------------+
                                      |
                                      v
                            [ Roteador Local ]
                                      |
                     +----------------+----------------+

                     |                                 |
                     v                                 v
          [ Saída para Internet ]              [ Windows Host ]
         (Apt, Docker Pull etc.)         (PuTTY, Ansible, Jenkins)
```

<br></br>

### Configuração com o Adaptador Correto no VirtualBox:
1. **Modo de Conexão:** A máquina virtual foi configurada mantendo o anexo em **Placa em modo Bridge**, permitindo que ela opere como um dispositivo autônomo e visível na rede local física.

<p align="center"> <img src="images/seleciona-placa-de-rede-001.png" alt="Tela de configuração da rede no VirtualBox"> </p>
<p align="right"><i>(Imagem: Representação do Terminal / Ubuntu Server)</i>

<br></br>

2. **Seleção do Adaptador (Nome):** Foi selecionada manualmente a placa de rede física **Realtek (Ethernet)** que estava conectada via cabo. Essa alteração evitou as restrições e incompatibilidades de pacotes que ocorrem ao tentar forçar o Modo Bridge usando a interface Wi-Fi do computador.

<p align="center"> <img src="images/seleciona-placa-de-rede-002.png" alt="Tela de configuração da rede no VirtualBox"> </p>
<p align="right"><i>(Imagem: Representação do Terminal / Ubuntu Server)</i>

---

<br></br>
---
### NAT e Bridge no VirtualBox

Durante a configuração da máquina virtual, foram testados os modos de rede NAT e Bridge disponíveis no VirtualBox.

**NAT:** permite que a máquina virtual acesse redes externas utilizando a conexão do computador físico. Para iniciar uma conexão SSH do Windows diretamente para a máquina virtual (VM) nesse modo, é necessário configurar o redirecionamento de portas.

**Bridge (Placa em modo Bridge):** conecta a máquina virtual à rede física, permitindo que ela receba um endereço IP próprio da rede local, desde que a rede disponibilize essa configuração.

### Modo utilizado no laboratório

Para este laboratório, foi utilizado o modo Bridge, acesso o Ubuntu Server por SSH a partir do Windows, utilizando o endereço IP da máquina virtual.

O teste com NAT ajudou a entender a diferença entre os dois modos e os requisitos de conectividade para o acesso SSH.

---

<br></br>

## 3. Gerando a chave SSH

### OpenSSH no Windows

O Windows possui o cliente OpenSSH, que permite gerar chaves SSH pelo PowerShell. Para este laboratório, será utilizado o algoritmo Ed25519.

Para abrir o PowerShell, clique no menu iniciar no canto inferior esquerdo. 

<p align="center"> <img src="images/powershell-00.png" alt="Abrindo o PowerShell"> </p>
<p align="right"><i>(Imagem: Representação para abrir o PowerShell / Windows)</i>

<br></br>

Na lista de programas, vá até a letra "W" e clique em "Windows PowerShell".

<p align="center"> <img src="images/powershell-01.png" alt="Abrindo o PowerShell"> </p>
<p align="right"><i>(Imagem: Representação para abrir o PowerShell / Windows)</i>

<br></br>

Outra forma de abrir o PowerShell digitando diretamente na barra de Pesquisar do Windows, conforme imagem abaixo:

<p align="center"> <img src="images/powershell-02.png" alt="Abrindo o PowerShell"> </p>
<p align="right"><i>(Imagem: Representação para abrir o PowerShell / Windows)</i>

<br></br>

No PowerShell execute o comando:

    ssh-keygen -t ed25519


<p align="center"> <img src="images/powershell-03.png" alt="Executando comando no PowerShell"> </p>
<p align="right"><i>(Imagem: Executando comando no PowerShell / Windows)</i>

<br></br>

Quando for solicitado o caminho para salvar a chave, pressione `Enter` para aceitar o caminho padrão, dentro do perfil do usuário atual. Por exemplo:

    C:\Users\SEU_USUARIO/.ssh/id_ed25519

O nome `SEU_USUARIO` é apenas um exemplo. O Windows utilizará automaticamente o nome do usuário atual.

<p align="center"> <img src="images/powershell-04.png" alt="Executando comando no PowerShell"> </p>
<p align="right"><i>(Imagem: Executando comando no PowerShell / Windows)</i>

<br></br>

Em seguida, será solicitada uma senha (*passphrase*) para proteger a chave privada. É possível definir uma senha ou pressionar `Enter` duas vezes para continuar sem ela. Neste laboratório não foi definida uma senha passphrase para a chave privada. Em ambientes de produção é recomendado definir uma senha passphrase.

<p align="center"> <img src="images/powershell-05.png" alt="Representação Passphrase no PowerShell"> </p>
<p align="right"><i>(Imagem: Representação Passphrase no PowerShell / Windows)</i>

<br></br>

### Chave pública

Após a geração, será criado o arquivo `id_ed25519.pub`, que contém a chave pública.

Essa chave poderá ser instalada nos servidores Ubuntu e AWS, permitindo a autenticação por chave SSH.

A chave pública pode ser compartilhada para configurar o acesso aos servidores.

<br></br>

### Chave privada

O arquivo `id_ed25519` contém a chave privada, utilizada pelo cliente SSH durante a autenticação.

Esse arquivo deve permanecer protegido no computador local e nunca deve ser compartilhado ou enviado ao GitHub.

<br></br>

### Conferindo os arquivos gerados

Para verificar se as chaves foram criadas, execute o comando no PowerShell:

    Get-ChildItem "$env:USERPROFILE\.ssh"

O diretório deverá conter os arquivos `id_ed25519` e `id_ed25519.pub`, além de quaisquer outros arquivos SSH que já existam.

---

<br></br>

## 4. Instalando a chave no Ubuntu

### ssh-copy-id

O comando `ssh-copy-id` permite copiar a chave pública para um servidor remoto, facilitando a configuração da autenticação por chave SSH.

O comando não está disponível nativamente no PowerShell deste ambiente. Será necessário utilizar um ambiente que tenha esse utilitário, como o Ubuntu, para realizar a instalação da chave pública.

### authorized_keys

No servidor Ubuntu, as chaves públicas autorizadas para login ficam normalmente no arquivo:

    ~/.ssh/authorized_keys

Esse arquivo permite que o servidor identifique quais chaves públicas podem autenticar conexões para o usuário correspondente.

---

<br></br>

## 5. Testando o acesso por chave

Após instalar a chave pública no Ubuntu, será realizado um novo acesso SSH para verificar se a autenticação por chave está funcionando.

O objetivo é confirmar que o acesso pode ser feito sem precisar informar a senha do usuário do Ubuntu a cada conexão. Se a chave privada estiver protegida por uma *passphrase*, ela ainda poderá ser solicitada.

---

<br></br>

## 6. Configurando o ~/.ssh/config

O arquivo `config`, localizado no diretório `.ssh` do usuário, permite definir configurações e aliases para conexões SSH.

No Windows, o caminho padrão é:

    C:\Users\SEU_USUARIO\.ssh\config

Exemplo de configuração para a máquina virtual Ubuntu:

    Host ubuntu-lab
        HostName 192.168.15.4
        User SEU_USUARIO
        IdentityFile ~/.ssh/id_ed25519

Substitua `192.168.15.4` pelo endereço IP real da máquina virtual e `SEU_USUARIO` pelo usuário existente no Ubuntu Server.

Com essa configuração, a conexão poderá ser iniciada utilizando o alias:

    ssh ubuntu-lab

O arquivo poderá receber também um alias para a instância EC2 após a sua criação e configuração.

---

<br></br>

## 7. Resultado

Ao concluir as etapas, o laboratório deverá ter:

- Uma chave SSH Ed25519 gerada no Windows.
- A chave pública instalada no Ubuntu Server.
- A autenticação por chave SSH testada.
- Um alias configurado no arquivo `~/.ssh/config`.
- O acesso à máquina virtual realizado utilizando o alias definido.

