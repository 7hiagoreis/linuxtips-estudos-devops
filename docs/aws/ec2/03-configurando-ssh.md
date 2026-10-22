# Configurando o acesso SSH à EC2 a partir de uma VM Ubuntu Server

Procedimentos para configurar o acesso SSH a uma instância Amazon EC2 a partir de uma máquina virtual Ubuntu Server executada no VirtualBox.

O processo utiliza o comando `ssh-copy-id` para instalar uma chave pública SSH na instância remota, permitindo autenticar conexões futuras utilizando uma chave pessoal.

---

## 1. Pré-requisitos

Antes de iniciar, é necessário ter:

- Uma VM Ubuntu Server instalada e funcionando no VirtualBox.
- Uma instância Amazon EC2 criada e acessível.
- O primeiro acesso a EC2 validado pelo PuTTY.
- O endereço IPv4 público da instância EC2.
- A chave privada `.pem` utilizada na criação da instância.
- Acesso a internet a partir da VM Ubuntu Server.

---

## 2. Verificar o cliente SSH

Na VM Ubuntu Server, execute:

```bash
ssh -V
```

O comando exibe a versão do cliente SSH instalado.

Verifique se o comando `ssh-copy-id` está disponível:

```bash
which ssh-copy-id
```

Caso não esteja instalado, execute:

```bash
sudo apt update
sudo apt install openssh-client
```

---

## 3. Verificar as chaves SSH da VM

Liste os arquivos existentes no diretório SSH do usuário:

```bash
ls -la ~/.ssh/
```

Uma chave pessoal ed25519 utiliza normalmente dois arquivos:

- `id_ed25519`: chave privada.
- `id_ed25519.pub`: chave pública.

Caso ainda não exista uma chave pessoal, gere uma:

```bash
ssh-keygen -t ed25519
```

Aceite o caminho padrão para utilizar `~/.ssh/id_ed25519`, caso seja adequado ao ambiente.

A chave privada deve permanecer protegida. Somente a chave pública, identificada pela extensão `.pub`, será instalada na EC2.

---

## 4. Transferir a chave privada da AWS para a VM

A chave `.pem` selecionada durante a criação da EC2 será utilizada para autenticar o primeiro acesso a partir da VM.

Transfira o arquivo da chave privada do Windows para a VM por um método seguro. Evite armazená-la em diretórios públicos ou em repositórios Git.

Considere que o arquivo foi transferido para `~/chaves/chave-aws.pem`. Ajuste o caminho e o nome conforme o local utilizado:

```bash
mkdir -p ~/.ssh
cp ~/chaves/chave-aws.pem ~/.ssh/
chmod 400 ~/.ssh/chave-aws.pem
```

O comando `chmod 400` restringe a leitura do arquivo ao proprietário.

**Importante:** Nunca publique ou compartilhe a chave privada `.pem`.

---

## 5. Acesso inicial à EC2

Para uma instância Ubuntu Server, execute na VM:

```bash
ssh -i ~/.ssh/chave-aws.pem ubuntu@IP_PUBLICO_DA_EC2
```

Substitua `IP_PUBLICO_DA_EC2` pelo endereço IPv4 público da instância.

Na primeira conexão, confira a identidade do servidor antes de aceitar a sua chave de identificação.

Após confirmar que o acesso funciona, encerre a sessão:

```bash
exit
```

---

## 6. Instalar a chave pública da VM na EC2

Com o acesso inicial validado, execute na VM Ubuntu Server:

```bash
ssh-copy-id \
  -i ~/.ssh/id_ed25519.pub \
  -o "IdentityFile=$HOME/.ssh/chave-aws.pem" \
  -o "IdentitiesOnly=yes" \
  ubuntu@IP_PUBLICO_DA_EC2
```

Substitua `IP_PUBLICO_DA_EC2` pelo endereço IPv4 público da instância.

O comando utiliza a chave privada da AWS para autenticar a conexão inicial e instala a chave pública pessoal da VM no arquivo `~/.ssh/authorized_keys` do usuário remoto.

Caso seja solicitada uma confirmação da identidade do servidor, confira a chave apresentada antes de aceitar.

---

## 7. Testar o acesso com a chave pessoal

Após instalar a chave pública, teste uma nova conexão utilizando a chave privada pessoal da VM:

```bash
ssh -i ~/.ssh/id_ed25519 ubuntu@IP_PUBLICO_DA_EC2
```

Caso a conexão seja estabelecida, a chave pessoal está funcionando para autenticação na EC2.

Para verificar o usuário conectado, execute:

```bash
whoami
```

Para encerrar a sessão:

```bash
exit
```

---

## 8. Configurar um alias SSH

Após validar o acesso por chave pessoal, é possível criar um alias para simplificar as próximas conexões.

Abra o arquivo de configuração SSH:

```bash
vim ~/.ssh/config
```

Adicione a configuração abaixo:

```sshconfig
Host ec2-lab
    HostName IP_PUBLICO_DA_EC2
    User ubuntu
    IdentityFile ~/.ssh/id_ed25519
    IdentitiesOnly yes
```

Substitua `IP_PUBLICO_DA_EC2` pelo endereço IPv4 público da instância.

Salve o arquivo e ajuste suas permissões:

```bash
chmod 600 ~/.ssh/config
```

Para conectar utilizando o alias, execute:

```bash
ssh ec2-lab
```

O alias permite utilizar um nome curto para a conexão, sem precisar informar o endereço IP e o caminho da chave em cada comando.

---

## 9. Observações de segurança

- Nunca compartilhe ou publique chaves privadas `.pem` ou `id_ed25519`.
- Somente a chave pública `.pub` deve ser instalada no servidor.
- Restrinja as regras de entrada SSH no Security Group aos endereços IP confiáveis.
- A VM precisa ter conectividade de rede com a EC2 pela porta TCP 22.
- O endereço IPv4 público pode mudar após a instância ser parada e iniciada novamente, dependendo da configuração utilizada.
- Para instâncias Amazon Linux, o usuário padrão geralmente é `ec2-user`, em vez de `ubuntu`.

---

## Referências

- [OpenSSH](https://www.openssh.com/)
- [Manual do ssh-copy-id](https://manpages.ubuntu.com/manpages/noble/en/man1/ssh-copy-id.1.html)
- [Documentação da AWS: conexão SSH com instâncias Linux](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/connect-linux-inst-ssh.html)

