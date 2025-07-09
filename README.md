# Previsão de Estoque Inteligente com AWS SageMaker Canvas
Este guia fornece um passo a passo prático para criar um modelo de Machine Learning (ML) de previsão de estoque utilizando o AWS SageMaker Canvas, uma ferramenta no-code para construção de modelos preditivos. A analogia aqui é como organizar um armário: você junta as roupas (dados), decide como dobrá-las (preparar os dados), e o SageMaker Canvas te ajuda a prever quais peças você precisará pegar com mais frequência (previsão de demanda).

## Objetivo

Criar um modelo de ML que preveja a demanda de estoque com base em dados históricos de vendas, minimizando excessos ou faltas, como um lojista sábio que sabe quanto de cada produto manter na prateleira.

## Pré-requisitos

- Conta ativa na AWS com permissões para acessar o SageMaker Canvas.
- Dados históricos de vendas em formato CSV (ex.: colunas como data, produto_id, quantidade_vendida, preço).
- Familiaridade básica com a AWS Console.

## Passo a Passo

1. Configurar o ambiente na AWS

- Acesse a AWS Management Console e vá para o SageMaker.
- No menu lateral, selecione SageMaker Canvas e clique em Open Canvas.
- Faça login ou crie um perfil de usuário para o Canvas.

2. Importar os dados

- No SageMaker Canvas, clique em Datasets > Import data.
- Faça upload do arquivo CSV com os dados históricos de vendas.

- Exemplo de estrutura de dados:

data,produto_id,quantidade_vendida,preço
2024-01-01,001,50,10.99
2024-01-02,001,45,10.99

- Verifique se os dados foram importados corretamente e renomeie colunas, se necessário.

3. Criar um modelo

- Vá para Models e clique em Create new model.
- Dê um nome ao modelo, como PrevisaoEstoque.
- Selecione o dataset importado no passo anterior.
- Escolha o tipo de problema: Time series forecasting (previsão de séries temporais).
- Defina a coluna alvo (quantidade_vendida) e a coluna de tempo (data).
- Configure os preditores (ex.: produto_id, preço).

4. Treinar o modelo

- Clique em Build model para iniciar o treinamento.
- Escolha entre Quick build (rápido, menos preciso) ou Standard build (mais demorado, mais preciso).
- Aguarde o treinamento (pode levar de minutos a horas, dependendo do tamanho dos dados).

5. Avaliar o modelo

- Após o treinamento, analise as métricas fornecidas pelo SageMaker Canvas, como MAPE (Mean Absolute Percentage Error) ou RMSE (Root Mean Square Error).
- Verifique a importância das variáveis (ex.: o preço influencia mais que o produto_id?).

6. Gerar previsões

- Clique em Predict para gerar previsões.
- Escolha o período de previsão (ex.: próximos 30 dias).
- Exporte as previsões em CSV ou visualize os resultados no Canvas.

7. Integrar e automatizar (opcional)

- Exporte o modelo para o SageMaker Studio ou integre com pipelines da AWS (ex.: AWS Lambda, Glue).
- Configure atualizações automáticas com novos dados de vendas.

## Dicas para Sucesso

- Limpeza de dados: Remova valores ausentes ou outliers antes de importar o CSV.
- Granularidade: Use dados diários ou semanais para melhores resultados em séries temporais.
- Iteração: Teste diferentes combinações de preditores para melhorar a precisão.
- Monitoramento: Acompanhe as previsões e ajuste o modelo com novos dados regularmente.

## Exemplo de Saída

O modelo pode gerar algo como:

data,produto_id,quantidade_prevista
2025-01-01,001,48
2025-01-02,001,50

Conclusão

- Com o SageMaker Canvas, você cria um modelo de previsão de estoque sem escrever código, como um mestre organizador que mantém tudo no lugar. 
- Use este guia para otimizar seu estoque e prepare-se para concursos públicos com a mentalidade de resolver problemas complexos de forma prática!
