# desafio-aws-cloudformation
Este repositório contém a implementação e documentação do desafio de **Automação de Infraestrutura com AWS CloudFormation**, proposto pela **Digital Innovation One (DIO)**.   O objetivo é aplicar os conhecimentos aprendidos sobre infraestrutura como código (IaC) utilizando CloudFormation.



##  Objetivo do Desafio

Implementar uma infraestrutura automatizada na AWS usando CloudFormation e documentar o processo no GitHub.

Com este desafio, pude:
- Aplicar os conceitos de **IaC (Infrastructure as Code)**;
- Criar e gerenciar recursos na AWS de forma automatizada;
- Entender a estrutura de templates em **YAML**;
- Utilizar o **GitHub** para versionamento e documentação técnica.

---

##  O que é o AWS CloudFormation?

O **AWS CloudFormation** é um serviço que permite **criar, configurar e gerenciar recursos da AWS automaticamente** a partir de um arquivo de configuração (template) escrito em **YAML** ou **JSON**.

Com ele, você pode definir tudo — de buckets S3 até VPCs e EC2 — de forma declarativa, evitando configurações manuais no console.

---

##  Estrutura do Template

Para este desafio, foi criado um **template simples** que cria um bucket S3 automaticamente.

###  Arquivo: `template.yaml`

```yaml
AWSTemplateFormatVersion: '2010-09-09'
Description: Template simples para o desafio DIO - Criação de um Bucket S3

Resources:
  MeuBucketDIO:
    Type: AWS::S3::Bucket
    Properties:
      BucketName: !Sub "meu-bucket-dio-${AWS::AccountId}-${AWS::Region}"
      AccessControl: Private

Outputs:
  BucketName:
    Description: Nome do bucket criado
    Value: !Ref MeuBucketDIO




