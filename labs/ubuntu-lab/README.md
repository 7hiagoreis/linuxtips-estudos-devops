# ubuntu-lab

Máquina virtual Ubuntu Server 22.04 LTS provisionada com Vagrant e VirtualBox, usada como ambiente de laboratório para os estudos do curso de DevOps Professional da LinuxTips.

---

## Objetivo

Este lab existe para servir como servidor de prática local. A ideia é ter um ambiente Linux isolado, que pode ser destruído e recriado a qualquer momento sem afetar o sistema operacional do computador físico.

Tudo o que for feito dentro da VM pode ser refeito do zero com um comando.

---

## O que vem instalado

Depois do provisionamento, a VM já sobe com:

- Ubuntu Server 22.04 LTS (Jammy)
- Docker e Docker Compose (plugin v2)
- git, curl, vim, nano, htop, tree, jq, make, build-essential
- net-tools, dnsutils, iputils-ping, traceroute
- Usuário `devops` com sudo habilitado

---

## Pré-requisitos

No computador físico, é preciso ter:

- [VirtualBox](https://www.virtualbox.org/wiki/Downloads)
- [Vagrant](https://developer.hashicorp.com/vagrant/downloads)
- Cerca de 4 GB de RAM livre
- Cerca de 3 GB de espaço em disco
- Virtualização habilitada na BIOS (VT-x / AMD-V)

> **Atenção no Windows:** se o Hyper-V ou o WSL2 estiverem ativos, poderá haver conflito com o VirtualBox. Nesse caso, desabilite temporariamente esses recursos.

---

## Estrutura

```
ubuntu-lab/
├── README.md
├── Vagrantfile
└── provision/
    └── bootstrap.sh
```

- `Vagrantfile`: Define a VM (sistema, recursos, rede, provisionamento)
- `provision/bootstrap.sh`: Script que roda dentro da VM e instala tudo o que está no script...

---

## Como usar

Dentro do diretório `labs/ubuntu-lab`:

```bash
# Sobe a VM e roda o provisionamento
vagrant up
```

Na primeira vez, o Vagrant baixa a box do Ubuntu (cerca de 500 MB) e o provisionamento demora alguns minutos. Depois disso, as próximas execuções são mais rápidas.

---

### Acessando a VM

```bash
# Entra na VM via SSH pelo Vagrant
vagrant ssh
```

Ou, se preferir acessar direto pelo IP:

```bash
ssh devops@192.168.56.13
```

Senha do usuário `devops`: `devops`.

---

### Comandos do dia a dia

```bash
vagrant up        # sobe a VM
vagrant halt      # desliga a VM, mantendo o disco
vagrant destroy   # apaga a VM completamente
vagrant reload    # reinicia aplicando mudanças do Vagrantfile
vagrant provision # roda o bootstrap novamente
vagrant status    # mostra o status da VM
```

---

## Configuração da VM

| Recurso | Valor |
|---|---|
| Sistema | Ubuntu Server 22.04 LTS (Jammy) |
| Box | `ubuntu/jammy64` |
| Hostname | `ubuntu-lab` |
| IP privado (host-only) | `192.168.56.13` |
| Memória RAM | 2048 MB |
| vCPUs | 2 |
| Diretório (Pasta) Compartilhado(a) | diretório do lab montado em `/vagrant` |
| Provider | VirtualBox |

A rede privada (host-only) permite acessar a VM apenas pelo computador físico. Nenhum outro dispositivo da rede local consegue acessar.

---

## Acesso SSH

O `bootstrap.sh` cria o usuário `devops` com:

- Shell: `/bin/bash`
- Grupos: `sudo`, `docker`
- Senha: `devops`
- Sudo sem senha (configurado em `/etc/sudoers.d/devops`)

Também copia a chave SSH do usuário `vagrant` para o usuário `devops`, permitindo o uso de `ssh-copy-id` logo depois.

---

### Alias no `~/.ssh/config`

Para acessar sem precisar digitar IP e usuário, adicione no arquivo `~/.ssh/config` (no Windows, fica em `C:\Users\<seu-usuario>\.ssh\config`):

```ssh
Host ubuntu-lab
    HostName 192.168.56.13
    User devops
    Port 22
```

Depois disso:

```bash
ssh ubuntu-lab
```

---

## Recriando o ambiente

Caso a VM quebre ou precise de um ambiente limpo:

```bash
vagrant destroy -f
vagrant up
```

Isso apaga a VM e sobe outra do zero. Útil para testes que podem quebrar o sistema operacional virtualizado.

---

## Observações

- Este lab é para estudos, formação DevOps Professional - LINUXtips. Algumas configurações (senha simples, sudo sem senha, `PasswordAuthentication yes` no SSH) **não devem ser usadas em produção**.
- O diretório `.vagrant/` é criada automaticamente e **não deve ser commitada**. Já está no `.gitignore`.
- Para mudar os recursos da VM, edite o `Vagrantfile` e rode `vagrant reload`.
