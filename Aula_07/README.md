# Aula 07 - Indicador de Semelhança CAR × SIGEF

## Arquivos

| Arquivo | Descrição |
|---------|-----------|
| `01_importar_dados.ipynb` | Script para importar os dados do CAR e SIGEF no banco local |
| `02_car_semelhanca_sigef.ipynb` | Notebook principal com o cálculo do indicador |

## Pré-requisitos

- PostgreSQL com PostGIS
- Banco de dados `geotec`
- Dados do CAR (MT) e SIGEF carregados

## Como usar

1. Execute `01_importar_dados.ipynb` para carregar os dados
2. Execute `02_car_semelhanca_sigef.ipynb` para calcular o indicador