# GEOTEC Aula 17 - Indicadores Ambientais

Este repositório contém notebooks para importar bases do CAR e calcular indicadores ambientais

## Link Bucket para baixar os dados da aula 17

https://storage.googleapis.com/geotec-governanca-territorial/Aula17/aula17_dados.zip

## Arquivos principais

- `import_dados.ipynb` — Notebook unificado de importação de dados (suporta `.gpkg` e `.shp`).
- `indicadores_ambientais.ipynb` — Notebook com rotinas para calcular indicadores

## Dados importados (exemplos)

- SICAR: `es_pi_apps_sicar`
- Módulo Fiscal: `incra.pa_br_modulosfiscais_incra`

## Pré-requisitos

- PostgreSQL com extensão PostGIS instalada
- Banco de dados `geotec` (ou ajuste a conexão nos notebooks)
- Arquivos de entrada em formatos `.gpkg` ou `.shp`

## Uso

1. Configure a pasta de dados no notebook `import_dados.ipynb` ajustando a variável `PASTA_DADOS`.
2. (Opcional) Ative/desative importações específicas modificando as flags do notebook:
   - `IMPORTAR_MODULO_FISCAL` — Módulo Fiscal
3. Execute `import_dados.ipynb` para carregar as bases no banco PostGIS. O notebook tenta carregar primeiro arquivos `.gpkg`; se não encontrados, tenta `.shp`.
4. Após a importação, execute `indicadores_ambientais.ipynb` para gerar os indicadores desejados.

## Observações operacionais

- Verifique e ajuste a string de conexão ao banco dentro dos notebooks conforme seu ambiente (usuário, senha, host, porta, nome do BD).
- Recomenda-se usar ambientes virtuais Python e instalar pacotes necessários (pandas, geopandas, sqlalchemy, psycopg2-binary, etc.).


