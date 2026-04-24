# Feature Engineering com Python

## Sobre o Projeto
Este projeto demonstra técnicas de **criação de novas variáveis** a partir de dados existentes, um passo essencial para melhorar análises e preparar dados para machine learning.

## O que é Feature Engineering?
É o processo de transformar dados brutos em **features (variáveis)** que facilitam a análise e melhoram a performance de modelos preditivos.

## Técnicas Demonstradas

### 1. Criando variável condicional com informações existentes
python
def preencher_nivel(gestor, nivel):
    if gestor == 1:
        return "Pessoa Gestora"
    return nivel

dados['NOVO_NIVEL'] = dados.apply(
    lambda x: preencher_nivel(x['GESTOR?'], x['NIVEL']), axis=1
)
