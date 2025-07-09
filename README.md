# Previsão de Estoque Inteligente com AWS SageMaker Canvas
Este guia fornece um passo a passo prático para criar um modelo de Machine Learning (ML) de previsão de estoque utilizando o AWS SageMaker Canvas, uma ferramenta no-code para construção de modelos preditivos. A analogia aqui é como organizar um armário: você junta as roupas (dados), decide como dobrá-las (preparar os dados), e o SageMaker Canvas te ajuda a prever quais peças você precisará pegar com mais frequência (previsão de demanda).

## Objetivo

Criar um modelo de ML que preveja a demanda de estoque com base em dados históricos de vendas, minimizando excessos ou faltas, como um lojista sábio que sabe quanto de cada produto manter na prateleira.

## Pré-requisitos

Conta ativa na AWS com permissões para acessar o SageMaker Canvas.
Dados históricos de vendas em formato CSV (ex.: colunas como data, produto_id, quantidade_vendida, preço).
Familiaridade básica com a AWS Console.
Analogia: Antes de cozinhar, reúna os ingredientes (dados) e prepare a cozinha (AWS).

## Passo a Passo

1. Configurar o ambiente na AWS

Acesse a AWS Management Console e vá para o SageMaker.
No menu lateral, selecione SageMaker Canvas e clique em Open Canvas.
Faça login ou crie um perfil de usuário para o Canvas.
Analogia: É como abrir a porta do seu ateliê de costura antes de começar a trabalhar.

2. Importar os dados

No SageMaker Canvas, clique em Datasets > Import data.
Faça upload do arquivo CSV com os dados históricos de vendas.
Exemplo de estrutura de dados:data,produto_id,quantidade_vendida,preço
2024-01-01,001,50,10.99
2024-01-02,001,45,10.99


Verifique se os dados foram importados corretamente e renomeie colunas, se necessário.
Analogia: É como separar as roupas por tipo e cor antes de guardá-las no armário.

3. Criar um modelo

Vá para Models e clique em Create new model.
Dê um nome ao modelo, como PrevisaoEstoque.
Selecione o dataset importado no passo anterior.
Escolha o tipo de problema: Time series forecasting (previsão de séries temporais).
Defina a coluna alvo (quantidade_vendida) e a coluna de tempo (data).
Configure os preditores (ex.: produto_id, preço).

