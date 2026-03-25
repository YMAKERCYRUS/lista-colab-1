# lista-colab-1
lista feita pelo colab

Análise Exploratória de Dados — Emendas Parlamentares
 
Análise exploratória (EDA) do dataset de emendas parlamentares do orçamento federal brasileiro, cobrindo o período de **2014 a 2016**. O objetivo é entender a estrutura dos dados, identificar inconsistências e extrair insights iniciais sobre a distribuição e execução orçamentária das emendas.
 
---
 
## Sobre o Dataset
 
| Propriedade | Valor |
|---|---|
| Fonte | Portal da Transparência / Dados Abertos |
| Período | 2014 – 2016 |
| Linhas | 20.632 |
| Colunas | 28 |
| Formato | CSV |
 
###  Dicionário de Variáveis
 
| Coluna | Descrição |
|---|---|
| `Código da Emenda` | Identificador único da emenda parlamentar |
| `Ano da Emenda` | Ano em que a emenda foi registrada |
| `Tipo de Emenda` | Classificação da emenda (ex: individual, bancada) |
| `Código do Autor da Emenda` | Identificador do parlamentar autor da emenda |
| `Nome do Autor da Emenda` | Nome do parlamentar que propôs a emenda |
| `Número da Emenda` | Número sequencial da emenda |
| `Localidade de aplicação do recurso` | Local onde o recurso será aplicado |
| `Código Município IBGE` | Código oficial IBGE do município beneficiado |
| `Município` | Nome do município beneficiado |
| `Código UF IBGE` | Código numérico IBGE do estado |
| `UF` | Sigla do estado beneficiado |
| `Região` | Região do Brasil onde o recurso é aplicado |
| `Código Função` | Código da função orçamentária (ex: saúde, educação) |
| `Nome Função` | Nome da função orçamentária |
| `Código Subfunção` | Código da subfunção orçamentária |
| `Nome Subfunção` | Detalhamento da subfunção orçamentária |
| `Código Programa` | Código do programa governamental vinculado |
| `Nome Programa` | Nome do programa governamental vinculado |
| `Código Ação` | Código da ação orçamentária específica |
| `Nome Ação` | Descrição da ação orçamentária |
| `Código Plano Orçamentário` | Código do plano orçamentário |
| `Nome Plano Orçamentário` | Descrição do plano orçamentário |
| `Valor Empenhado` | Valor comprometido/reservado para a emenda |
| `Valor Liquidado` | Valor confirmado após prestação de contas |
| `Valor Pago` | Valor efetivamente pago ao beneficiário |
| `Valor Restos A Pagar Inscritos` | Valor inscrito em restos a pagar (não pago no ano) |
| `Valor Restos A Pagar Cancelados` | Valor de restos a pagar que foi cancelado |
| `Valor Restos A Pagar Pagos` | Valor de restos a pagar que foi efetivamente quitado |
 
---
 
##  Etapas da Análise (Notebook)
 
O notebook `pandas_intro_ex1_respondida.ipynb` percorre as seguintes etapas:
 
1. **Carregamento dos dados** — leitura do CSV e visualização das primeiras linhas
2. **Dimensões do dataset** — verificação de linhas e colunas com `df.shape`
3. **Listagem das colunas** — identificação e descrição de cada variável
4. **Tipos de dados** — verificação com `df.dtypes`
5. **Valores nulos** — contagem de nulos por coluna com `df.isnull().sum()`
6. **Valores duplicados** — verificação com `df.duplicated().sum()`
7. **Estatísticas descritivas** — análise com `df.describe()`
8. **Atualização do dataset** — identificação do ano mais recente com ordenação descrescente
 
---
 
## Problemas de Qualidade Identificados
 
- **Colunas financeiras como `object`** — valores como `Valor Empenhado`, `Valor Liquidado` e `Valor Pago` estão como texto, provavelmente por formatação brasileira (`1.500,00`), impedindo análises numéricas diretas.
- **Campos com "Sem Informação"** — diversas colunas de identificação possuem esse valor como preenchimento padrão, indicando registros incompletos.
- **`Código UF IBGE` com valor negativo** — o valor mínimo `-14` é inválido, pois códigos IBGE são sempre positivos.
- **12 colunas com 1 valor nulo cada** — provavelmente pertencentes à mesma linha com problema de importação.
 
---
 
##  Tecnologias Utilizadas
 
- Python 3
- Pandas
- jupyter notbook
