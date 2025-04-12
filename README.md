
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

## 🔍 METODOLOGIA

### 🟫 Camada Bronze
- Armazenamento do dado bruto após leitura do CSV.
- Normalização dos nomes de colunas para evitar erros de schema.
- Registro no catálogo `bronze.state_of_data_2023`.

### ◼️ Camada Silver
- Seleção e renomeação das colunas relevantes.
- Padronização dos tipos de dados.
- Remoção de registros nulos.
- Inclusão da coluna `dt_silver` (data de ingestão).
- Registro no catálogo `silver.state_of_data`.

### 🟨 Camada Gold
- Mapeamento da coluna `tempo_experiencia` para valores categóricos padronizados.
- Extração da faixa numérica da `faixa_salarial`.
- Filtragem dos registros válidos para análise.
- Registro no catálogo `gold.state_of_data`.

---

## 📈 RESULTADOS

- Dados prontos para análise com colunas limpas e significativas.
- Tabela Gold com tipagem correta e sem valores inconsistentes.
- Base preparada para geração de dashboards e análises estatísticas.

### Exemplos de insights gerados:
- Distribuição de gênero por faixa etária.
- Faixa salarial média por senioridade.
- Impactos da diversidade nas oportunidades profissionais.
- Análise regional dos profissionais de dados.

---

## 📌 OBSERVAÇÕES

- As transformações foram feitas com foco em escalabilidade, legibilidade e reprodutibilidade.
- Utiliza funções UDFs e expressões regulares para tratamento textual.
- O projeto está pronto para ser utilizado como base para análises mais avançadas ou integração com ferramentas de BI.

---

## 📁 ESTRUTURA DO PROJETO

```
.
├── notebooks/
│   └── mvp_puc_rio_engenharia_documentado.ipynb
├── data/
│   └── State_of_data_BR_2023.csv
├── README.md
└── requirements.txt
```

## ▶️ COMO EXECUTAR

1. Faça upload do notebook para seu workspace no Databricks.
2. Coloque o arquivo CSV em `dbfs:/FileStore/State_of_data_BR_2023.csv`.
3. Execute o notebook célula a célula.

## 🛠️ TECNOLOGIAS

- Python 3 + PySpark
- Databricks + Delta Lake
- DBFS
- SQL + Spark SQL

## 📄 LICENÇA

Distribuído sob a licença MIT. Veja `LICENSE` para mais detalhes.
