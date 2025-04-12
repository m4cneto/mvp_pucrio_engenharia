
# 📊 State of Data 2023 - Engenharia de Dados com Databricks

## 📌 DESCRIÇÃO

Este projeto aplica boas práticas de engenharia de dados para estruturar e analisar os dados da pesquisa **State of Data Brasil 2023**. Utiliza uma arquitetura em camadas (Bronze, Silver e Gold) no ambiente do Databricks, com transformações realizadas em PySpark e armazenadas em formato Delta.

---

## 📦 DADOS

- **Fonte**: [Kaggle - State of Data 2023](https://www.kaggle.com/datasets/databrazil/state-of-data-2023)
- **Formato original**: CSV
- **Volume**: ~7 mil registros
- **Tema**: Perfil de profissionais de dados no Brasil (idade, formação, salário, experiência, diversidade, etc.)

---

## ⚙️ Metodologia

1. **Bronze Layer**: Leitura do CSV original no DBFS.
2. **Silver Layer**: Padronização de nomes de colunas, tipagem e remoção de valores nulos.
3. **Gold Layer**: Criação de tabelas analíticas com agrupamentos e transformações específicas para insights.

---

## 📈 Resultados - Camada Gold

### 1. `gold.faixa_salarial_por_experiencia`
- **Analise**: Profissionais com maior tempo de experiência tendem a se concentrar em faixas salariais mais altas.

### 2. `gold.salario_genero_cor_raca`
- **Analise**: Pessoas negras e indígenas estão sub-representadas nas faixas salariais mais elevadas, especialmente entre mulheres.

### 3. `gold.nivel_ensino_senioridade`
- **Analise**: A maioria dos profissionais de nível sênior possui ao menos ensino superior completo. A senioridade se correlaciona positivamente com a escolaridade.

### 4. `gold.mudanca_estado_salario`
- **Analise**: Profissionais que mudaram de estado tendem a estar em faixas salariais mais altas, indicando possível mobilidade para melhores oportunidades.

### 5. `gold.discriminacao_carreira`
- **Analise**: Há relatos significativos de discriminação por cor/raça, gênero e deficiência, impactando oportunidades e salários, especialmente entre pessoas pretas, mulheres e PcDs.

### 6. `gold.media_salarial_senioridade_experiencia`
- **Analise**: A média salarial aumenta progressivamente com o tempo de experiência e senioridade. Profissionais sêniors com mais de 10 anos de experiência recebem as maiores médias salariais.


---

## 📌 OBSERVAÇÕES

- Algumas categorias foram padronizadas para facilitar a análise (e.g., faixas salariais e experiência).
- Remoção de registros com informações incompletas em colunas-chave.
- As análises consideram apenas registros válidos e consistentes.
- O projeto está pronto para ser utilizado como base para análises mais avançadas ou integração com ferramentas de BI.
- Algumas categorias foram padronizadas para facilitar a análise (e.g., faixas salariais e experiência).


---

## ▶️ COMO EXECUTAR

1. Carregar o dataset que encontra-se no repositorio dentro Databricks via (DBFS) ou pegar o arquivo raw no proprio git e fazer a ingestão via python.
2. Executar os notebooks em ordem: Bronze → Silver → Gold.
3. Consultar as tabelas da camada Gold via SQL ou exportar os resultados.

## 🛠️ TECNOLOGIAS

- Python 3 + PySpark
- Databricks + Delta Lake
- DBFS
- SQL + Spark SQL
