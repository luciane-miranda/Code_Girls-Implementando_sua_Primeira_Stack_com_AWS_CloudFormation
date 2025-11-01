# Code_Girls-Implementando_sua_Primeira_Stack_com_AWS_CloudFormation
Desafio do Curso da DIO: Santander Code Girls - 2025, Módulo mplementando sua Primeira Stack com AWS CloudFormation

---

## Objetivo

- Aplicar os conceitos aprendidos em um ambiente prático; 
- Documentar processos técnicos de forma clara e estruturada;
- Utilizar o GitHub como ferramenta para compartilhamento de documentação técnica.
- Demonstrar o uso de infraestrutura como código (IaC) para provisionar recursos na nuvem AWS de forma controlada, reproduzível e documentada através de CloudFormation, abordando:
  - Criação de um modelo (template) CloudFormation em JSON ou YAML  
  - Definição de parâmetros, recursos e saídas (Outputs)  
  - Criação da pilha (stack) usando o console da AWS  
  - Verificação de status e monitoramento da pilha  
  - Limpeza dos recursos para evitar custos desnecessários  

---

## Principais Etapas Realizadas

### 1. Preparação do Template  
- Escolhi o formato YAML (ou JSON) para o template.  
- Definição da versão `AWSTemplateFormatVersion`, `Description`, `Parameters`, `Resources` e `Outputs`.  
- Incluí parâmetros para tipo de instância, AMI, VPC/sub-rede, ou outras variáveis conforme a necessidade.  
- Em `Resources`, declarei pelo menos um recurso AWS (por exemplo, uma instância EC2 ou um bucket S3).  
- Em `Outputs`, defini valor(s) que serão retornados ao final da criação da pilha, como URL pública ou ID do recurso.

### 2. Criação da Pilha no Console AWS  
- Acesse o console do AWS CloudFormation.  
- No menu, optei por “Criar pilha” (Create stack) com novos recursos.  
- Faça upload do arquivo de template ou forneça URL do S3.  
- Insira o nome da pilha (“MyFirstStack” ou equivalente).  
- Preencha os parâmetros (quando aplicável).  
- Revise, confirme que compreende que serão criados recursos com permissões IAM (se aplicável).  
- Clique em “Criar”.

### 3. Monitoramento da Criação da Pilha  
- Acompanhei a guia **Eventos** para ver o progresso da criação (`CREATE_IN_PROGRESS` → `CREATE_COMPLETE`).  
- Em caso de erro, verifiquei detalhes nas mensagens de evento para identificar qual recurso falhou ou qual propriedade está inválida.  
- Após conclusão com sucesso, verifiquei os recursos no console correspondente (por ex., console EC2, S3 ou outro) para confirmar que foram criados corretamente.

### 4. Verificação e Testes  
- Utilizei o Output da pilha para acessar o recurso (por ex., URL ou ID) e verifiquei que funcionava conforme esperado.  
- Avaliei se o template está configurado de forma idempotente (ou seja, se rodado novamente, deveria gerar resultados consistentes).  
- Fiz testes simples de modificação do template ou substituição de parâmetros para confirmar repetibilidade.

### 5. Limpeza dos Recursos  
- Para evitar custos, selecionei a pilha no console CloudFormation → **Excluir** (Delete stack).  
- Acompanhei o evento `DELETE_IN_PROGRESS` até remoção completa dos recursos.  
- Confirmei que os recursos associados foram liberados (por ex., instância EC2 terminada, S3 vazio ou removido).

---

## Estrutura do Repositório

