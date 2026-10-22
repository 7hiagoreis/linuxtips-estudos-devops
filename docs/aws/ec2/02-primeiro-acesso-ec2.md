# Primeiro acesso à instância EC2 pelo PuTTY

Este documento apresenta os procedimentos para realizar o primeiro acesso a uma instância Amazon EC2 utilizando o PuTTY no Windows, com autenticação por chave SSH.

## 1. Pré-requisitos

Antes de iniciar, é necessário ter:

- Uma instância EC2 criada e com o estado `Running`.
- O endereço IPv4 público da instância.
- A chave privada `.pem` selecionada durante a criação da instância.
- O PuTTY e o PuTTYgen instalados no Windows.
- Uma regra de entrada no Security Group permitindo SSH pela porta `22`, preferencialmente restrita ao IP público do computador utilizado para o acesso.

## 2. Consultar os dados da instância

Acesse o [console da AWS](https://console.aws.amazon.com/) e navegue até:

**EC2 → Instances → Selecione a instância**

Na tela de detalhes, localize as seguintes informações:

| Informação | Descrição |
|---|---|
| Instance ID | Identificador da instância EC2 |
| Instance state | Deve estar como `Running` |
| Public IPv4 address | Endereço público utilizado para a conexão |
| AMI | Imagem do sistema operacional instalado |
| Key pair name | Nome do par de chaves selecionado na criação |

O endereço IPv4 público será utilizado na configuração do PuTTY.

## 3. Converter a chave PEM para PPK

O PuTTY utiliza normalmente o formato `.ppk` para autenticação por chave privada. Caso a versão instalada não aceite diretamente o arquivo `.pem`, será necessário convertê-lo utilizando o PuTTYgen.

1. Abra o PuTTYgen.
2. Clique em **Load**.
3. Selecione o arquivo `.pem` baixado durante a criação da instância.
4. Caso necessário, altere o filtro de arquivos para exibir todos os tipos.
5. Após carregar a chave, clique em **Save private key**.
6. Salve o arquivo no formato `.ppk`.

Guarde a chave privada em um local seguro. Ela não deve ser compartilhada nem enviada para repositórios no GitHub.

## 4. Configurar o PuTTY

Abra o PuTTY e configure os parâmetros da conexão.

### 4.1. Informar o endereço da instância

Na categoria **Session**, preencha:

- **Host Name (or IP address):** usuário SSH seguido do endereço IPv4 público.
- **Port:** `22`.
- **Connection type:** `SSH`.

Para uma instância Ubuntu Server, o formato do endereço será:

`ubuntu@IP_PUBLICO_DA_EC2`

Substitua `IP_PUBLICO_DA_EC2` pelo endereço real da instância.



### 4.2. Selecionar a chave privada

No menu lateral, navegue até:

**Connection → SSH → Auth → Credentials**

No campo de arquivo da chave privada, selecione o arquivo `.ppk` gerado anteriormente.

Volte à categoria **Session** para iniciar a conexão.

## 5. Realizar o primeiro acesso

Clique em **Open** para abrir a sessão SSH.

Na primeira conexão, o PuTTY poderá exibir um aviso sobre a chave de identificação do servidor. Confira a impressão digital (*fingerprint*) por um meio confiável antes de aceitar. Essa chave identifica o servidor remoto e é diferente da chave privada utilizada para autenticação.

Após a conexão, o terminal solicitará a autenticação por chave. Com a configuração correta, o acesso será realizado sem a necessidade de informar uma senha de usuário.

## 6. Validar a conexão

Após entrar na instância, execute os comandos abaixo para verificar o ambiente.

### Identificar o usuário conectado

```bash
whoami
```

### Identificar o nome do servidor

```bash
hostname
```

### Atualizar a lista de pacotes

Em uma instância Ubuntu Server, execute:

```bash
sudo apt update
```

O comando atualiza os índices dos pacotes disponíveis nos repositórios configurados, sem realizar a atualização dos pacotes instalados.

## 7. Encerrar a sessão

Para finalizar a conexão SSH, execute:

```bash
exit
```

## 8. Observações de segurança

- Mantenha a chave privada `.pem` ou `.ppk` protegida.
- Nunca publique suas chaves privadas no GitHub.
- Permita conexões SSH somente a partir de endereços IP confiáveis sempre que possível.
- O acesso depende das regras de rede, do estado da instância e da configuração do sistema operacional.
- O endereço IPv4 público pode mudar após a interrupção e a inicialização da instância, dependendo da configuração utilizada.

## Referências

- [Amazon EC2](https://aws.amazon.com/ec2/)
- [Documentação do PuTTY](https://www.putty.org/)
- [Conectar-se à instância Linux usando SSH](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/connect-linux-inst-ssh.html)
