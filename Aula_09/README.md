# Aula 09 - Indicador de Dinâmica dos Cadastros

## Arquivos

| Arquivo | Descrição |
|---------|-----------|
| `01_importar_dados.ipynb` | Script para importar os dados do CAR e tabela com tamanho de Módulo Fiscal no banco local |
| `02_dinamica_car.ipynb` | Notebook principal com o cálculo do indicador |

## Pré-requisitos

- PostgreSQL com PostGIS
- Banco de dados `geotec`
- Dados do CAR (MT) 
- Table Módulos Fiscais (INCRA)

## Como usar

1. Execute `01_importar_dados.ipynb` para carregar os dados
2. Execute `02_dinamica_car.ipynb` para calcular o indicador