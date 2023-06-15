# Terraform-AWS
O Terraform é uma ferramenta de infraestrutura como código que permite provisionar, gerenciar e atualizar recursos de infraestrutura em diversos provedores de nuvem, incluindo a AWS.
Ele nos ajuda a garantir a consistência e escalabilidade da nossa infraestrutura, além de simplificar o gerenciamento e controle de versão do código.

### Tópicos 

:small_blue_diamond: [Descrição do projeto](#descrição-do-projeto)

:small_blue_diamond: [Pré-requesitos AWS](#Pré-requisitos-AWS)

:small_blue_diamond: [Pré-requesitos Terraform](#Pré-requesitos-Terraform)

:small_blue_diamond: [Alterações que devem ser feitas no código](#Alterações-que-devem-ser-feitas-no-código)

:small_blue_diamond: [Como rodar a aplicação](#como-rodar-a-aplicação)


## Descrição-do-projeto
<p align="justify">
Neste repositório, você poderá criar recursos AWS como, LAMBDA, SNS,S3 BUCKET, GLUE DATABASE e GLUE TABLE com algumas configurações de exemplo que poderão ser adaptadas para a sua necessidade em específico. 
</p>

.
├── data
│   ├── processed            <-  Dados processados
│   └── raw                  <-  Dados originais e imutáveis
├── notebooks                <-  Jupyter notebooks. Padrão de nomenclatura é um número, as iniciais de quem criou,
│                                e uma descrição ex.: `1.0-jt-coleção-de-links.ipynb`.
├── README.md                <-  Arquivo README.md contendo as informações do projeto
├── requirements.txt         <-  Arquivo de instalação de bibliotecas Python necessárias pra reproduzir o ambiente de análises.
│                                gerado usando `pip freeze > requirements.txt`
├── setup.py                 <-  Definições do pacote `src` que torna ele instalável usando o `pip`
└── src                      <-  Módulo Python criado para este projeto
    ├── data                 <-  Código para gerar/coletar dados
    │   └── make_dataset.py
    └── __init__.py

## Pré-requisitos-AWS

1️⃣ - Criar uma conta na AWS, caso ainda não tenha uma.

2️⃣ - Fazer login no Console da AWS e criar um usuário IAM com permissões necessárias para criar e gerenciar recursos na AWS. É importante que o usuário tenha permissão para criar e gerenciar chaves de acesso.

3️⃣ - Criar uma chave de acesso (access key) para o usuário IAM criado no passo anterior. As chaves de acesso são compostas por uma Access Key ID e uma Secret Access Key.

4️⃣ - Instalar o AWS CLI (Command Line Interface) na máquina local da pessoa. A AWS CLI é uma interface de linha de comando que permite interagir com a AWS usando comandos no terminal.

5️⃣ - Configurar o AWS CLI com as credenciais da chave de acesso criada no passo 3. Para isso você tem 2 opções: 
   - Entrar na pasta .aws que aparece ao instalar o AWS CLI(no passo 4) e colocar suas credenciais aws. 
   - Instalar a extensão do vscode 'AWS CLI Configure' e colocar suas credenciais diretamente por ela.

## Pré-requesitos-Terraform

:warning: [Terraform](https://www.terraform.io/downloads.html)

## Alterações-que-devem-ser-feitas-no-código

➡️ Insira sua região AWS no lugar de "us-east-1", caso for outra. E certifique-se de mudar em todos os outros lugares também.
```Terraform
provider "aws" {
  region = "us-east-1"
}
```

➡️ Em todos os lugares que aparecer 000000000000 insira seu id count.
```Terraform
resource "aws_lambda_function" "lambda_teste" {
  function_name = "arn:aws:lambda:us-east-1:000000000000:function:lambda-teste"
  filename      = ""
  handler       = "src/lambda_handler"
  runtime       = var.type_python
  memory_size   = 2048
  timeout       = 300
```



## Como-rodar-a-aplicação

1️⃣ No terminal, clone o projeto: 

```
https://github.com/psrosso/Terraform-AWS.git
```

2️⃣ Entre na pasta do projeto:  

```
cd Terraform-AWS
```

3️⃣ Insira suas credênciais AWS: (passo 5 no [Pré-requesitos-AWS](#Pré-requisitos-AWS))


- Pela pasta: 
``.aws``

  OU
- Pela extensão:
``AWS CLI Configure do vscode.``

4️⃣ Faça as [Alterações que devem ser feitas no código](#Alterações-que-devem-ser-feitas-no-código)

5️⃣ Execute no terminal: 

``
terraform init
``

``
terraform plan
``

``
terraform apply
``

:trophy: Pronto, agora seus recursos AWS estão criados!! 

