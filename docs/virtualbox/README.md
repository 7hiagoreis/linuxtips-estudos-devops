# VirtualBox

Documentação do laboratório de virtualização com Oracle VirtualBox e Ubuntu Server.

Aqui ficam os guias que explicam como montar, configurar e usar uma máquina virtual para estudos de Linux, redes, Docker, DevOps e áreas relacionadas.

---

## Por que o VirtualBox

O VirtualBox permite rodar um sistema operacional completo dentro do computador físico, de forma isolada, sem precisar formatar a máquina ou alterar o sistema principal.

Isso cria um ambiente seguro para testes. Se algo quebrar, basta recriar a máquina virtual do zero.

É útil principalmente para:

- Estudar Linux sem sair do Windows
- Praticar comandos e configurações do servidor virtualizado
- Testar serviços, redes e containers com liberdade
- Simular ambientes parecidos com os de produção
- Destruir e recriar o ambiente com agilidade, quando necessário

---

## Estrutura dos Documentos

```
docs/virtualbox/
└── windows/
    ├── 01-introducao.md
    └── 02-instalando-virtualbox-e-ubuntu.md
```

Cada arquivo cobre uma etapa do laboratório. O número no começo do nome indica a ordem de leitura.

---

## Documentos Disponíveis

### Windows (sistema hospedeiro)

| Documento | O que cobre |
|---|---|
| [01-introducao.md](windows/01-introducao.md) | Conceitos de virtualização, hypervisor, host, guest e visão geral do projeto |
| [02-instalando-virtualbox-e-ubuntu.md](windows/02-instalando-virtualbox-e-ubuntu.md) | Instalação do VirtualBox, criação da VM e instalação do Ubuntu Server |

---

## Documentos Planejados

Conforme o laboratório for evoluindo, novos documentos serão adicionados:

- Configuração de rede da VM
- Diretórios/Pastas compartilhadas entre host e guest
- Snapshot e restauração de estados
- Instalação do Guest Additions
- Comandos básicos de administração do sistema
- Acesso remoto via SSH
  
---

## Outros sistemas hospedeiros

No momento, o foco é o Windows como sistema principal. Tutoriais para Linux e macOS como host serão adicionados futuramente, mantendo o mesmo padrão de diretórios:

```
docs/virtualbox/
├── windows/
├── linux/
└── macos/
```

---

## Como ler

Sugestão de ordem para quem está começando:

1. Leia o `01-introducao.md` para entender os conceitos
2. Siga o `02-instalando-virtualbox-e-ubuntu.md` para montar o ambiente
3. Use o laboratório pronto para praticar os próximos tópicos do curso

Os documentos foram escritos para serem seguidos em sequência, mas também podem ser consultados separadamente conforme a necessidade.

---

## Referências

- [Oracle VirtualBox Downloads](https://www.virtualbox.org/wiki/Downloads)
- [Oracle VirtualBox Documentation](https://www.virtualbox.org/manual/)
- [Ubuntu Server Downloads](https://ubuntu.com/download/server)
