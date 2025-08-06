# Análise de Dados do Airbnb no Rio de Janeiro

> Este projeto tem como objetivo realizar a **limpeza, transformação e análise de dados** de anúncios do Airbnb no Rio de Janeiro. A ideia é aplicar técnicas de manipulação de dados para **entender melhor o mercado de hospedagem, identificar padrões e tendências** e preparar os dados para futuras análises ou modelagem preditiva.

---

## Contexto

Você foi contratado por uma consultoria especializada no mercado de aluguel por temporada para analisar dados de acomodações do **Airbnb no Rio de Janeiro**. Sua missão é transformar um conjunto de dados brutos em uma base **limpa, estruturada e pronta para análise**.

Será que o preço é o fator mais decisivo na escolha de uma acomodação? Ou a localização e as avaliações dos hóspedes têm mais peso? Para descobrir isso, é fundamental garantir que os dados estejam prontos para qualquer tipo de análise.

---

## Sobre os dados

O conjunto de dados contém informações detalhadas sobre as acomodações disponíveis no Airbnb no Rio de Janeiro, incluindo:

### Listings (Anúncios de Propriedades)

| Coluna                  | Descrição                                  |
|-------------------------|--------------------------------------------|
| `id`                    | Identificador único do imóvel               |
| `neighbourhood_cleansed`| Bairro onde o imóvel está localizado        |
| `room_type`             | Tipo de acomodação (ex: quarto privativo)  |
| `accommodates`          | Número máximo de pessoas                     |
| `bathrooms`             | Quantidade de banheiros                      |
| `bedrooms`              | Número de quartos                            |
| `beds`                  | Número total de camas                        |
| `price`                 | Preço da diária em moeda local               |

### Reviews (Avaliações de Hóspedes)

| Coluna               | Descrição                                        |
|----------------------|-------------------------------------------------|
| `id`                 | Identificador único do imóvel (correspondente)  |
| `number_of_reviews`   | Quantidade total de avaliações                   |
| `review_scores_rating`| Nota média dada pelos hóspedes                    |

---

## Como começar?

- Carregue os dados e explore as primeiras linhas para entender a estrutura.
- Realize a limpeza: trate valores ausentes, corrija tipos de dados e remova colunas irrelevantes.
- Identifique outliers e faça ajustes necessários para evitar distorções na análise.
- Transforme os dados para padronizar informações categóricas e normalizar variáveis numéricas.
- Realize análises exploratórias para descobrir padrões e insights úteis para os anfitriões.

---

# 🎯 Etapas de Desenvolvimento

## Etapa 01) Carregando os dados

- Importação dos arquivos `listings_cleaned.csv` e `reviews.csv` usando pandas.
- Inspeção inicial com `.head()` para garantir carregamento correto.
- União dos DataFrames com `pd.merge()` usando a chave correta (`id` com `listing_id`) e junção do tipo `inner` para evitar perda de dados.

---

## Etapa 02) Limpeza e Tratamento de Dados

- Identificação de valores ausentes com `df.isnull().sum()`.
- Tratamento dos nulos por preenchimento (média, moda) ou remoção (`dropna()`).
- Exclusão de colunas irrelevantes para análise.
  
---

## Etapa 03) Tratando e Visualizando Outliers

- Visualização dos outliers com gráficos do tipo `boxplot`.
- Aplicação do método IQR (Intervalo Interquartil) para definição de limites aceitáveis.
- Remoção de registros com valores fora do intervalo aceitável para colunas como `price`.

---

## Etapa 04) Transformando Dados Categóricos

- Conversão das colunas categóricas (ex: `room_type`, `neighbourhood_cleansed`) para códigos numéricos com `.astype('category').cat.codes`.
- Criação de tabelas auxiliares para bairros (`neighbourhood`) normalizados.
- Remoção de colunas originais após transformação para evitar redundância.

---

## Etapa 05) Conferindo Resultado Final

- Verificação final para garantir que não há outliers não tratados.
- Remoção de colunas redundantes e desnecessárias.
- Confirmação que dados categóricos e numéricos estão transformados e normalizados.
- Última inspeção com `df.head()`, `df.info()`, `df.describe()` e listagem de colunas com `df.columns`.

---

## Tecnologias utilizadas

- Python 3.x
- Pandas
- Matplotlib
- Scikit-learn (para normalização, opcional)

---

## Como rodar o projeto

1. Clone o repositório.
2. Coloque os arquivos `listings_cleaned.csv` e `reviews.csv` na pasta do projeto.
3. Execute o notebook ou script Python com as etapas de análise.
4. Confira o dataset final limpo e pronto para modelagem salvo como `dataset_modelagem_pronto.csv`.

---

## Considerações finais

Este projeto permitiu entender melhor os dados do Airbnb no Rio de Janeiro, garantindo uma base confiável e estruturada para análises e modelagem preditiva. A etapa de limpeza e preparação é fundamental para o sucesso de qualquer projeto de ciência de dados.

---
