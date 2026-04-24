# Correlação de Variáveis Categóricas com Cramér's V

## Sobre o Projeto
Este projeto implementa o coeficiente de **Cramér's V** para medir a força da associação entre duas variáveis categóricas.

## Por que Cramér's V?
- Correlação de Pearson funciona apenas para **números**
- Para variáveis categóricas (como raça, gênero, nível de ensino), usamos **Cramér's V**
- O resultado varia de **0 a 1**:
  - 0 = nenhuma associação
  - 1 = associação perfeita

## Função Implementada

```python
def cramer_v(coluna1, coluna2):
    tabela_cruzada = pd.crosstab(coluna1, coluna2)
    chi2 = chi2_contingency(tabela_cruzada)[0]
    n = tabela_cruzada.sum().sum()
    min_dim = min(tabela_cruzada.shape) - 1
    return np.sqrt(chi2 / (n * min_dim))
