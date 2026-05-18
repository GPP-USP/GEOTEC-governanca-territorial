# Aula 08 - Indicador de Sobreposição entre CARs

## Arquivos

| Arquivo | Descrição |
|---------|-----------|
| `01_importar_dados.ipynb` | Script para importar os dados do CAR no banco local (suporta GPKG e SHP) |
| `02_car_sobreposicao.ipynb` | Notebook principal com o cálculo do indicador |

## Pré-requisitos

- PostgreSQL com PostGIS
- Banco de dados `geotec`
- Dados do CAR (PI)

## Como usar

1. **Configure a pasta dos dados**:
   - Edite a variável `PASTA_DADOS` no script de importação
   - Coloque os arquivos na pasta configurada

2. **Execute o script de importação**:
   - O script aceita arquivos nos formatos `.gpkg` ou `.shp`
   - Primeiro tenta carregar `.gpkg`; se não existir, tenta `.shp`

3. **Execute o notebook principal** para calcular o indicador