# Desafio: Implementando a Primeira Stack com AWS CloudFormation

Este repositório documenta meu aprendizado e a implementação da minha primeira "Stack" (pilha) com AWS CloudFormation, como parte do bootcamp.

## 1. Objetivo

O objetivo deste desafio foi consolidar o entendimento sobre **Infraestrutura como Código (IaC)**. Em vez de criar recursos manualmente pelo console da AWS (o que é sujeito a erros e demorado), o CloudFormation permite definir, provisionar e gerenciar recursos da AWS de forma declarativa, usando um arquivo de template (YAML ou JSON).

## 2. O Conceito: O que é CloudFormation?

* **Template:** É o "mapa" ou "planta baixa" da sua infraestrutura, escrito em formato YAML ou JSON. É aqui que você *declara* o que quer construir (ex: "Eu quero 1 S3 Bucket").
* **Stack:** É o conjunto de recursos que o CloudFormation cria com base em um template. É a "construção" real. Se você deletar a Stack, todos os recursos criados por ela são deletados juntos.
* **IaC (Infrastructure as Code):** É a prática de gerenciar sua infraestrutura (servidores, bancos de dados, buckets) da mesma forma que você gerencia seu código: com versionamento (Git), revisões e automação.

## 3. Implementação: Minha Primeira Stack

Para este desafio, criei um template de CloudFormation para provisionar um recurso essencial para qualquer aplicação: um **Amazon S3 Bucket**.

No meu cenário de **Sistema de Hotelaria**, este bucket (`Hotelaria-Image`) seria usado para armazenar e servir as fotos dos quartos, faturas em PDF ou outros arquivos estáticos.

## 4. Passos da Implementação (Meus Insights)
Durante o laboratório, estes foram os passos e aprendizados:

Escrever o Template: O primeiro passo foi escrever o arquivo .yaml.

Upload no Console: Fui ao console do CloudFormation e cliquei em "Create stack" > "With new resources".

Especificar Template: Fiz o upload do meu arquivo s3-bucket-template.yaml.

Parâmetros da Stack: Dei um nome para a minha Stack (no meu caso, Hotelaria-Image).

Revisão (Events): Este foi o insight mais importante! A aba "Events" mostra em tempo real o que o CloudFormation está fazendo (CREATE_IN_PROGRESS, CREATE_COMPLETE). Se algo der errado, é aqui que a mensagem de erro aparece.

Verificar Recursos: Após a conclusão, a aba "Resources" mostrou meu HotelImagesBucket criado.

Verificar Saídas (Outputs): A aba "Outputs" mostrou o nome físico exato do meu bucket.

Limpeza (Delete Stack): O passo final foi selecionar a Stack Hotelaria-Image e clicar em "Delete". O CloudFormation foi e destruiu o S3 Bucket que ele criou, limpando tudo automaticamente.

## 5. Conclusão
Este desafio mudou minha perspectiva sobre a criação de recursos na nuvem.

Com o CloudFormation, eu ganho:

* **Repetibilidade**: Posso criar 10 ambientes de hotelaria idênticos com um clique.

* **Consistência**: Garanto que o ambiente de teste é exatamente igual ao de produção.

* **Versionamento**: Posso salvar meu template no GitHub e ter um histórico de todas as mudanças feitas na minha infraestrutura.
