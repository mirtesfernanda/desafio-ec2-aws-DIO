# Desafio: Arquitetura AWS - S3 / EC2 / Lambda / EBS

## Visão Geral
Este projeto implementa uma arquitetura em AWS utilizando serviços gerenciados como **API Gateway, AWS Lambda, Amazon S3, EC2 e EBS** para orquestrar o recebimento, processamento e confirmação de transações.

A solução foi projetada em três etapas principais:
1. **Autorização**
2. **Recebimento de Transação**
3. **Confirmação da Transação**

---

## Arquitetura:

### 1. Autorização
- **API Gateway**: responsável por autorizar o acesso.  
- **Lambda (AUC-TokenAuth)**: validação de token de autenticação.  

### 2. Recebe Transação
- **API Gateway (recebe)**: recebe a requisição da transação.  
- **Lambda (AUC-Cloud-Consumer)**: processa os dados recebidos.  
- **Amazon S3**: armazenamento dos dados da transação.  
- **Lambda (AVC-SyncS3)**: sincroniza dados para instância EC2.  
- **EC2 + EBS**: processamento e armazenamento adicional dos dados.  

### 3. Confirma Transação
- **Lambda (AtualizaTransacao)**: confirma e atualiza o status da transação no sistema.  

---

## Estrutura do Repositório
```bash
📦 desafio-arquitetura-aws
 ┣ README.md   # Documentação do projeto
 ┣ images      # Capturas de tela e diagramas
 ┗ docs        # Documentos de apoio (opcional)
