# 🏨 Automação de Tarefas com AWS Lambda e S3 – Hotelaria

Este repositório foi criado como parte do desafio da DIO para consolidar conhecimentos em **tarefas automatizadas utilizando AWS Lambda e Amazon S3**.  
O cenário prático simula uma empresa de hotelaria que automatiza processos internos usando serviços serverless da AWS.

---

## 🎯 Objetivo do Desafio

- Aplicar Lambda Functions para processamento automático de arquivos enviados ao S3  
- Demonstrar automação de rotinas internas sem uso de servidores (serverless)  
- Documentar a arquitetura e os aprendizados no GitHub de forma profissional  

---

## 🏗️ Arquitetura da Solução

O fluxo automatizado funciona da seguinte forma:

1. O hóspede ou funcionário faz **upload de documentos** através do site do hotel  
2. O arquivo é enviado para um **bucket S3 (Uploads)**  
3. Um **Lambda Function é disparado automaticamente** quando o arquivo chega  
4. O Lambda processa os dados, valida, converte formato e grava em **DynamoDB / S3 Processado**  
5. A equipe é notificada via **SNS / SES (e-mail interno do hotel)**  
6. Uma **rotina agendada (CloudWatch/EventBridge)** executa outro Lambda diariamente  
7. Esse Lambda gera um **relatório consolidado** e envia para o portal de gestão via outro bucket S3  
8. Gestores recebem notificação com link do relatório

🖼️ **Diagrama do fluxo automatizado**  
*(imagem em `/images` ou abaixo se seu GitHub permitir visualizar)*

![Diagrama AWS Lambda + S3 – Hotel](./images/lambda_s3_hotel_automation.jpg)

---

## 🧩 Serviços AWS Utilizados

| Serviço | Função |
|---------|--------|
| Amazon S3 | Upload de documentos e armazenamento de relatórios |
| AWS Lambda | Processamento automático de dados sem servidor |
| DynamoDB / S3 Processado | Armazenamento estruturado dos dados de reservas |
| Amazon SNS/SES | Notificações internas (time do hotel) |
| CloudWatch / EventBridge | Agendamento de tarefas diárias |
| IAM Roles | Controle de permissões seguro |

---
![FridayThe13thJasonGIF](https://github.com/user-attachments/assets/171ba386-208e-48b2-a914-dcf6bf63a1fc)



## 📂 Estrutura do Repositório

