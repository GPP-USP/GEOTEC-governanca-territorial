# Aula 09 - Indicador de Dinâmica dos Cadastros

## Arquivos

| Arquivo | Descrição |
|---------|-----------|
| `01_importar_dados.ipynb` | Script para importar os dados do CAR e tabela com tamanho de Módulo Fiscal no banco local (suporta GPKG e SHP) |
| `02_dinamica_car.ipynb` | Notebook principal com o cálculo do indicador |

## Pré-requisitos

- PostgreSQL com PostGIS
- Banco de dados `geotec`
- Dados do CAR (MT) - múltiplas versões
- Tabela Módulos Fiscais (INCRA)

## Como usar

1. **Configure a pasta dos dados**:
   - Edite a variável `PASTA_DADOS` no script de importação
   - Coloque os arquivos na pasta configurada

2. **Execute o script de importação**:
   - O script aceita arquivos nos formatos `.gpkg` ou `.shp`
   - Primeiro tenta carregar `.gpkg`; se não existir, tenta `.shp`
   - Detecta automaticamente arquivos com "car" e "modulosfiscais" no nome

3. **Execute o notebook principal** para calcular o indicador