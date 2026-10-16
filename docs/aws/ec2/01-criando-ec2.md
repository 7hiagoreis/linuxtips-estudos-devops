# Criando uma instância EC2 na AWS

O Amazon EC2 (Elastic Compute Cloud) é um serviço da AWS que fornece servidores virtuais em uma nuvem segura e redimensionável. No contexto de DevOps, essa definição ganha um peso prático, deixando de ser apenas uma máquina virtual comum e passando a funcionar como parte de uma infraestrutura que pode ser automatizada e recriada conforme a necessidade.

## Pré-requisitos

- Possuir uma conta ativa na [Amazon Web Services (AWS)](https://aws.amazon.com/pt/).
- Consultar as instruções de [criação de uma conta na AWS](https://github.com/7hiagoreis/linuxtips-estudos-devops/blob/main/docs/aws/01-criando-uma-conta-na-aws.md).

## Configuração da EC2

### Passo 1. Acessar o painel do EC2

1. Faça login no [AWS Management Console](https://console.aws.amazon.com/).
2. Na barra de pesquisa no topo da página, digite `EC2` e selecione o serviço correspondente.
3. No canto superior direito, verifique e selecione a região onde deseja hospedar o servidor, como Norte da Virgínia (`us-east-1`) ou São Paulo (`sa-east-1`).

### Passo 2. Iniciar a criação da instância

1. No painel do EC2, clique em **Executar instância** (*Launch instance*).

### Passo 3. Configurar os atributos principais

Preencha as seções do assistente de criação conforme as orientações abaixo.

| Seção | O que selecionar ou preencher | Observações |
|---|---|---|
| Nome e tags | Informe um nome para identificar a máquina, como `MeuServidor-DevOps`. | Ajuda na organização dos recursos. |
| Imagens de aplicativos e sistema operacional (AMI) | Selecione o sistema operacional desejado, como Ubuntu ou Amazon Linux. | Verifique as imagens disponíveis e as condições de elegibilidade para o plano da AWS. |
| Tipo de instância | Selecione `t2.micro`, conforme solicitado no exercício. | A disponibilidade e as condições de cobrança dependem da região e do plano da conta. |
| Par de chaves (login) | Clique em **Criar novo par de chaves**, informe um nome e selecione o tipo de chave e o formato do arquivo. | Use `.pem` para OpenSSH ou `.ppk` para PuTTY. Guarde a chave privada em local seguro, pois ela não poderá ser baixada novamente. |

### Passo 4. Configurar a rede e o grupo de segurança

Os grupos de segurança funcionam como um firewall virtual, controlando o tráfego de entrada e saída da instância.

| Configuração | Opção recomendada | Finalidade |
|---|---|---|
| Grupo de segurança | Crie um novo grupo ou selecione um existente. | Define as regras de acesso à instância. |
| Tráfego SSH (porta 22) | Selecione **Meu IP**. | Permite o acesso remoto ao terminal a partir do endereço IP autorizado. |
| Tráfego HTTP/HTTPS | Habilite as portas 80 e 443 somente se necessário. | Permite o acesso a serviços web. |

Evite liberar o SSH para qualquer endereço IP (`0.0.0.0/0`) sem necessidade, pois isso expõe a porta de acesso remoto à internet.

### Passo 5. Configurar o armazenamento (volumes EBS)

1. Defina o tamanho do disco virtual e o tipo de volume.
2. Confira as condições de armazenamento incluídas no plano da AWS antes de iniciar a instância.

Os limites e as condições de gratuidade podem variar conforme a data de criação da conta e o plano disponível. Verifique os valores atuais para evitar cobranças inesperadas.

### Passo 6. Revisar e executar a instância

1. No painel de resumo, confirme as configurações e selecione uma instância.
2. Clique em **Executar instância** (*Launch instance*).
3. Após a confirmação, clique em **Visualizar todas as instâncias** para acompanhar o estado da máquina.

## Como conectar a instância EC2

Quando a instância estiver no estado **Em execução**, siga as etapas abaixo para acessá-la por SSH.

1. Selecione a instância no console da AWS e clique em **Conectar**.
2. Abra a aba **Cliente SSH** e consulte o comando de exemplo fornecido pela AWS.
3. Abra o terminal do computador no diretório onde a chave privada `.pem` está salva.
4. No Linux ou macOS, ajuste as permissões da chave:

```bash
   chmod 400 sua-chave.pem
```

5. Execute o comando SSH, substituindo o nome do arquivo da chave e o endereço público pelos valores da sua instância:

```bash
   ssh -i "sua-chave.pem" ubuntu@ENDERECO_PUBLICO_DA_EC2
```

Nesse exemplo, `ubuntu` é o usuário padrão de muitas imagens oficiais do Ubuntu. Para outras imagens, o nome do usuário pode ser diferente.

Em ambientes com sistema operacional Windows, o comando SSH pode ser executado pelo PowerShell com o OpenSSH instalado ou pelo terminal do WSL, caso o ambiente Linux esteja configurado. O comando `chmod` é utilizado no Linux e no macOS para ajustar as permissões da chave privada.
