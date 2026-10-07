# SSH

Documentação dos estudos de SSH realizados durante o curso de DevOps da LINUXtips.

Aqui ficam os guias relacionados ao acesso remoto a servidores Linux, autenticação por chaves SSH, configuração do arquivo `~/.ssh/config` e outros recursos utilizados nos laboratórios.


---

## SSH

O SSH permite acessar e administrar um sistema Linux remotamente por meio de uma conexão segura.

Durante os estudos, ele será utilizado para acessar diferentes ambientes, como a máquina virtual Ubuntu Server executada localmente no VirtualBox e uma instância EC2 na AWS.

A ideia é utilizar o mesmo conhecimento de acesso remoto em ambientes diferentes, praticando conceitos que fazem parte da administração de servidores e ambientes DevOps.

---

## Ambientes utilizados

O laboratório utiliza inicialmente dois ambientes:

```text
Computador físico
       |
       v
    Windows
       |
       v
   VirtualBox
       |
       v
Ubuntu Server
       |
       |
       +---------------- SSH ----------------+
                                            |
                                            v
                                      AWS EC2
```

A VM local é utilizada como ambiente de estudos e testes.

A instância EC2 será utilizada como ambiente na nuvem para os exercícios do curso.

---

## Conteúdos

Os documentos desta seção serão organizados conforme os conceitos forem estudados.

| Documento | O que cobre |
|---|---|
| [01-acesso-por-chave.md](01-acesso-por-chave.md) | Configuração das chaves SSH, `ssh-copy-id`, acesso a VM Ubuntu Server e primeiros testes de autenticação |


---

## Chaves SSH

O acesso por chave utiliza um par formado por uma chave privada e uma chave pública.

A chave privada permanece no computador utilizado para realizar o acesso e não deve ser compartilhada.

A chave pública pode ser instalada no servidor para permitir a autenticação.

De forma simplificada:

```text
Computador
    |
    | chave pública
    v
Servidor Linux
    |
    v
~/.ssh/authorized_keys
```

Depois da configuração, o acesso pode ser realizado utilizando a chave SSH em vez de depender apenas de autenticação por senha.

---

## SSH no laboratório

No primeiro capítulo do curso, o SSH será utilizado para preparar um ambiente híbrido formado por uma VM local e uma instância EC2 na AWS.

Entre os objetivos estão:

- Acessar a VM Ubuntu por SSH
- Configurar autenticação por chave
- Utilizar `ssh-copy-id`
- Configurar aliases no `~/.ssh/config`
- Acessar a EC2 por SSH
- Utilizar o mesmo computador para administrar os dois ambientes
- Executar comandos remotamente nos servidores

A configuração será utilizada novamente em capítulos posteriores sempre que o curso exigir acesso remoto ou administração dos servidores.

---

## Estrutura dos documentos

```text
docs/ssh/
├── README.md
└── 01-acesso-por-chave.md
```

A numeração indica a ordem em que os assuntos foram documentados durante os estudos.

A estrutura poderá crescer conforme novos conceitos de SSH forem apresentados no curso.

---

## Referências

- [OpenSSH](https://www.openssh.com/)
- [OpenSSH Manual](https://man.openbsd.org/ssh)
