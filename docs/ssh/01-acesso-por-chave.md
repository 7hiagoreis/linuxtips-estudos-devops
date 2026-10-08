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

Existe a versão "portable" (portável) do PuTTY, é possível fazer o download desta versão na seção Alternative Binary Files.

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

Inicialmente, o instalador exibe a tela de boas vindas. Clique em "Next" para começar este processo.

<p align="center"> <img src="images/06-tela-de-boas-vindas-putty.png" alt="Tela de Boas Vindas do PuTTY"> </p>
<p align="right"><i>(Imagem 06: Tela de boas vindas / Instalando o PuTTY)</i>

<br></br>

### Local de instalação

O próximo passo é definir o local de instalação do PuTTY, neste exemplo vamos instalar no diretório padrão ( C:\Program Files\PuTTY\ ), sem fazer nenhuma alteração.

Clique em "Next" para continuar.

<p align="center"> <img src="images/07-local-de-instalacao-putty.png" alt="Local de instalação do PuTTY"> </p>
<p align="right"><i>(Imagem 07: Local de instalação do PuTTY)</i>

<br></br>

### Product Features / Recursos do Produto

Agora o instalador do PuTTY vai apresentar a seção "Product Features" (Recursos do Produto), aqui podemos escolher quais componentes e ferramentas extras do PuTTY desejamos instalar ou ativar no computador.

<p align="center"> <img src="images/08-selecionando-features.png" alt="Recursos Extras / Instalação do PuTTY"> </p>
<p align="right"><i>(Imagem 08: Recursos Extras / Instalação do PuTTY)</i>

  
---

<br></br>

## 2. Primeiro acesso ao Ubuntu Server
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
