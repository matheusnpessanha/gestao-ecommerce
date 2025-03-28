# Gestão de e-commerce
## Visão Geral
Este projeto tem como objetivo desenvolver um sistema para cadastro de clientes (PJ e PF), formas de pagamento e status de entrega com código de rastreamento.

## Modelagem do Banco de Dados
A modelagem do banco de dados segue um esquema que inclui as seguintes entidades:

### 1. Cliente
- id (PK)  
- nome (String)  
- email (String, único)  
- telefone (String)  
- tipo (Enum: PJ ou PF)  
- cpf (String, exclusivo para PF)  
- cnpj (String, exclusivo para PJ)  
- endereco (String)  

### 2. Pagamento
- id (PK)  
- cliente_id (FK -> Cliente)  
- tipo_pagamento (Enum: Cartão, Boleto, Pix)  
- dados_pagamento (JSON ou String, conforme necessidade)  

### 3. Entrega
- id (PK)  
- cliente_id (FK -> Cliente)  
- status (Enum: Pendente, Em Transporte, Entregue, Cancelado)  
- codigo_rastreamento (String, único)  
- data_prevista (DateTime)  
