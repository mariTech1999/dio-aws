# RELATÓRIO DE IMPLEMENTAÇÃO DE SERVIÇOS AWS

Data: 24/12/2025
Empresa: Distribuidora Pharma
Responsável: Marina Keiko Yano

## Introdução
Este relatório apresenta o processo de implementação de ferramentas na empresa Distribuidora Pharma, realizado por Marina Keiko Yano. O objetivo do projeto foi elencar 3 serviços AWS, com a finalidade de realizar diminuição de custos imediatos e modernização da arquitetura para lidar com picos de demanda logística e retenção de dados regulatórios.

## Descrição do Projeto
O projeto de implementação de ferramentas foi dividido em 3 etapas, cada uma com seus objetivos específicos. A seguir, serão descritas as etapas do projeto:

### Etapa 1: Armazenamento Inteligente
- **Nome da ferramenta:** Amazon S3 Intelligent-Tiering
- **Foco da ferramenta:** Otimização automática de custos de armazenamento com base na frequência de acesso.
- **Descrição de caso de uso:** A empresa armazena grandes volumes de notas fiscais e laudos sanitários por 5 anos para conformidade (Anvisa). Implementamos o S3 Intelligent-Tiering para mover automaticamente objetos não acessados por 90 dias para a camada "Archive Instant Access", gerando uma economia estimada de 40% sem necessidade de scripts manuais de limpeza.

### Etapa 2: Processamento de Dados com Baixo Custo
- **Nome da ferramenta:** Amazon EC2 Spot Instances
- **Foco da ferramenta:** Redução de custos computacionais utilizando capacidade ociosa da AWS.
- **Descrição de caso de uso:** A rotina noturna de cálculo de rotas e previsão de estoque é um processo de "batch" (lote) tolerante a interrupções. Substituímos as instâncias On-Demand por Spot Instances para esses jobs, aproveitando descontos de até 90% no valor da hora computacional.

### Etapa 3: Arquitetura Event-Driven
- **Nome da ferramenta:** AWS Lambda
- **Foco da ferramenta:** Eliminação de custos de ociosidade (pay-per-use).
- **Descrição de caso de uso:** A API de recebimento de pedidos das farmácias tinha baixo tráfego durante a madrugada, mas mantinha servidores ligados 24/7. Migramos este microsserviço para AWS Lambda. Agora, o custo é zero quando não há requisições, e a cobrança é feita apenas pelos milissegundos de execução quando um pedido entra.

## Conclusão
A implementação de ferramentas na empresa Distribuidora Pharma tem como esperado uma **redução de OPEX (Custos Operacionais) da ordem de 35%**, além de aumentar a elasticidade da infraestrutura para suportar a volatilidade do mercado farmacêutico. Recomenda-se a continuidade da utilização das ferramentas implementadas e a ativação do **AWS Cost Explorer** para monitoramento granular das despesas futuras.

## Anexos

- [Documentação Oficial - S3 Intelligent-Tiering](https://aws.amazon.com/s3/cost-optimization/)
- [Calculadora de Economia AWS (Estimativa)](https://calculator.aws/)
- [Diagrama da Arquitetura Serverless (Conceitual)]

Assinatura do Responsável pelo Projeto:

Marina Keiko Yano
