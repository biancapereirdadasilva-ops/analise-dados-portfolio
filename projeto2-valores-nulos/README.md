
# Tratamento de Valores Nulos com Pandas

## Sobre o Projeto
Este projeto demonstra estratégias para identificar e tratar valores ausentes (NaN) em datasets utilizando a biblioteca Pandas.

## Conceitos Aplicados
- Identificação de nulos com `.isnull().sum()`
- Preenchimento com `.fillna()` e `.loc[]`
- Uso de mediana para dados com outliers
- Preenchimento baseado em coluna auxiliar

## Exemplo Prático

```python
# Verificando valores nulos
dados['SALARIO'].isnull().sum()  # 577 valores nulos

# Preenchendo com a mediana
mediana_salario = dados['SALARIO'].median()
dados.loc[dados['SALARIO'].isnull(), 'SALARIO'] = mediana_salario
