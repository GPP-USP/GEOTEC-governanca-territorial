# Aula 10 - Script Unificado de Importação

## Arquivo

| Arquivo | Descrição |
|---------|-----------|
| `01_importar_dados.ipynb` | Script unificado para importar todos os dados das aulas 07, 08 e 09 no banco local (suporta GPKG e SHP) |

## Dados importados

| Aula | Base | Tabela no banco |
|------|------|-----------------|
| **07** | CAR MT | `car.es_mt_car_20260406` |
| **07** | SIGEF | `incra.pa_br_sigef_privado_20260107` |
| **08** | CAR PI | `car.es_pi_car_20260406` |
| **09** | CAR MT (2025-07-02) | `car.es_mt_car_20250702` |
| **09** | CAR MT (2025-12-02) | `car.es_mt_car_20251202` |
| **09** | CAR MT (2026-04-06) | `car.es_mt_car_20260406` |
| **09** | Módulo Fiscal | `incra.pa_br_modulosfiscais_incra` |

## Pré-requisitos

- PostgreSQL com PostGIS
- Banco de dados `geotec`

## Como usar

1. **Configure a pasta dos dados**:
   - Edite a variável `PASTA_DADOS` no script de importação
   - Coloque os arquivos na pasta configurada

2. **Execute o script de importação**:
   - O script aceita arquivos nos formatos `.gpkg` ou `.shp`
   - Primeiro tenta carregar `.gpkg`; se não existir, tenta `.shp`

3. **Após a importação**, execute os notebooks das aulas 07, 08 e 09

## Controle de importação

O script permite desativar a importação de bases específicas:

| Variável | Descrição |
|----------|-----------|
| `IMPORTAR_CAR_MT` | Importa CAR do Mato Grosso (Aula 07) |
| `IMPORTAR_CAR_PI` | Importa CAR do Piauí (Aula 08) |
| `IMPORTAR_CAR_MT_VERSOES` | Importa versões do CAR MT (Aula 09) |
| `IMPORTAR_SIGEF` | Importa SIGEF (Aulas 07 e 08) |
| `IMPORTAR_MODULO_FISCAL` | Importa módulo fiscal (Aulas 08 e 09) |