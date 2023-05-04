# Terraform-AWS
O Terraform é uma ferramenta de infraestrutura como código que permite provisionar, gerenciar e atualizar recursos de infraestrutura em diversos provedores de nuvem, incluindo a AWS.
Ele nos ajuda a garantir a consistência e escalabilidade da nossa infraestrutura, além de simplificar o gerenciamento e controle de versão do código.

### Tópicos 

:small_blue_diamond: [Descrição do projeto](#descrição-do-projeto)

:small_blue_diamond: [Pré-requesitos-AWS](#Pré-requisitos-AWS)

:small_blue_diamond: [Pré-requesitos-Terraform](#Pré-requesitos-Terraform)

:small_blue_diamond: [Como rodar a aplicação](#como-rodar-a-aplicação)


## Descrição-do-projeto
<p align="justify">
Neste repositório, você poderá criar recursos AWS como, LAMBDA, SNS,S3 BUCKET, GLUE DATABASE e GLUE TABLE com algumas configurações de exemplo que poderão ser adaptadas para a sua necessidade em específico. 
</p>

## Pré-requisitos-AWS

1 - Criar uma conta na AWS, caso ainda não tenha uma.

2 - Fazer login no Console da AWS e criar um usuário IAM com permissões necessárias para criar e gerenciar recursos na AWS. É importante que o usuário tenha permissão para criar e gerenciar chaves de acesso.

3 - Criar uma chave de acesso (access key) para o usuário IAM criado no passo anterior. As chaves de acesso são compostas por uma Access Key ID e uma Secret Access Key.

4 - Instalar o AWS CLI (Command Line Interface) na máquina local da pessoa. A AWS CLI é uma interface de linha de comando que permite interagir com a AWS usando comandos no terminal.

5 - Configurar o AWS CLI com as credenciais da chave de acesso criada no passo 3. Para isso você tem 2 opções: 
   - Entrar na pasta .aws que aparece ao instalar o AWS CLI(no passo 4) e colocar suas credenciais aws. 
   - Instalar a extensão do vscode 'AWS CLI Configure' e colocar suas credenciais diretamente por ela.

## Pré-requesitos-Terraform

:warning: [Terraform](https://www.terraform.io/downloads.html)

## Como-rodar-a-aplicação

No terminal, clone o projeto: 

```
https://github.com/psrosso/Terraform-AWS.git
```

Entre na pasta do projeto:  

```
Terraform-AWS
```

Insira suas credênciais AWS: (passo 5 no [Pré-requesitos-AWS](#Pré-requisitos-AWS))


- Pela pasta: 
``.aws``

  OU
- Pela extensão:
``AWS CLI Configure do vscode.``

Execute no terminal: 

``
terraform init
``

``
terraform plan
``

``
terraform apply
``



