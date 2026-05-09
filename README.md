# DataCNPJ

DataCNPJ is a multilingual dataset designed for evaluating Large Language Models (LLMs) on the tasks of Text-to-SQL and Schema-Linking using a realistic database scenario based on public Brazilian company registration data (CNPJ).

The dataset provides:
* Natural language questions in English and Portuguese
* Executable SQL queries for both database versions
* Explicit Schema-Linking annotations
* Complexity labels following the Spider taxonomy
* Compatibility with Test Suite Eval

## Dataset Overview

Each dataset instance contains:

| Attribute               | Description                                                           |
| ----------------------- | --------------------------------------------------------------------- |
| `question_id`           | Unique numeric identifier                                             |
| `question_EN`           | Natural language question in English                                  |
| `query_cnpjEN`          | SQL query for the English database                                    |
| `schema_linking_cnpjEN` | Schema-Linking JSON annotation for the English database               |
| `question_PT`           | Natural language question in Portuguese                               |
| `query_cnpjPT`          | SQL query for the Portuguese database                                 |
| `schema_linking_cnpjPT` | Schema-Linking JSON annotation for the Portuguese database            |
| `synthetic`             | Boolean flag indicating whether the query was synthetically generated |
| `hardness`              | Query complexity level (`easy`, `medium`, `hard`, `extra`)            |

The current version contains:

* 187 queries
* 65 manually created queries
* Queries distributed across multiple complexity levels
* Two equivalent SQLite databases:
    * Portuguese schema
    * English schema
Both databases contain:
* 14 tables
* 75 columns

## Database Construction

The databases were built using public CNPJ data provided by the Brazilian Federal Revenue Service:

CNPJ public dataset:
    https://dados.gov.br/dados/conjuntos-dados/cadastro-nacional-da-pessoa-juridica---cnpj

The extraction and transformation pipeline used to generate the SQLite databases is available at: https://github.com/ErickIssa/Receita_Federal_do_Brasil_-_Dados_Publicos_CNPJ


The SQLite database files (Portuguese and English versions) are available at: https://drive.google.com/drive/folders/1HxDEOL7NDAxr-HberiIzjYFZgVDNH1wM?usp=sharing

### Test Suite Eval

The dataset is compatible with the Test Suite Eval framework used in Text-to-SQL evaluation: https://github.com/taoyds/test-suite-sql-eval

The folder TestSuitEval/ contains the gold SQL files required for evaluation.