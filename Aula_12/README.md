# Aula 12+13 - Sobreposição Fundiária, Desmatamento e Amazônia Legal

## Arquivos

| Arquivo | Descrição |
|---------|-----------|
| `01_importar_dados.ipynb` | Script para importar os dados no banco local (suporta GPKG e SHP) |
| `02_indicadores_fundiarios.ipynb` | Notebook principal com os indicadores |

## Bases de Dados Importadas

| Base | Descrição | Schema | Tabela |
|------|-----------|--------|--------|
| CAR MT | Cadastro Ambiental Rural - Mato Grosso | `car` | `es_mt_car_20260406` |
| SIGEF | Sistema de Gestão Fundiária | `incra` | `pa_br_sigef_privado_incra_2026` |
| SNCI | Sistema Nacional de Cadastro de Imóveis | `incra` | `pa_br_snci_privado_incra_2026` |
| UC | Unidades de Conservação (MMA) | `mma` | `pa_br_ucs_mma_2026` |
| TI | Terras Indígenas (FUNAI) | `funai` | `pa_br_terrasindigenas_funai_2026` |
| TQ | Territórios Quilombolas (INCRA) | `incra` | `pa_br_territoriosquilombolas_incra_2026` |
| CNFP | Cadastro Nacional de Florestas Públicas (SFB) | `sfb` | `pa_br_cnfp_sfb_2024_retificado` |
| Assentamentos | Projetos de Assentamento (INCRA) | `incra` | `pa_br_assentamentos_incra_2026` |
| Malha Fundiária MT | Malha fundiária do Mato Grosso | `malha` | `pa_mt_malhafundiaria_2025_cdt` |
| Módulo Fiscal | Valores de referência por município (INCRA) | `incra` | `pa_br_modulosfiscais_incra` |
| Desmatamento MT | Desmatamento no Mato Grosso (INPE) | `inpe` | `pa_mt_desmatamento_inpe_20260304` |
| Amazônia Legal | Polígono da Amazônia Legal (IBGE) | `ibge` | `pa_br_amazonialegal_ibge_2022` |
| Faixa de Fronteira | Polígono da Faixa de Fronteira (IBGE) | `ibge` | `pa_br_faixafronteira_ibge_2024` |

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

3. **Execute o notebook principal** para calcular os indicadores

## Controle de importação

O script permite desativar a importação de bases específicas:

| Variável | Descrição | Padrão |
|----------|-----------|--------|
| `IMPORTAR_CAR_MT` | CAR do Mato Grosso | `True` |
| `IMPORTAR_UC` | Unidades de Conservação | `True` |
| `IMPORTAR_TI` | Terras Indígenas | `True` |
| `IMPORTAR_TQ` | Territórios Quilombolas | `True` |
| `IMPORTAR_CNFP` | Cadastro Nacional de Florestas Públicas | `True` |
| `IMPORTAR_ASSENTAMENTOS` | Projetos de Assentamento | `True` |
| `IMPORTAR_MALHA_MT` | Malha Fundiária do MT | `True` |
| `IMPORTAR_MODULOS_FISCAIS` | Tabela de Módulo Fiscal | `True` |
| `IMPORTAR_SIGEF` | Sistema de Gestão Fundiária | `True` |
| `IMPORTAR_SNCI` | Sistema Nacional de Cadastro de Imóveis | `True` |
| `IMPORTAR_DESMATAMENTO_MT` | Desmatamento no MT (INPE) | `True` |
| `IMPORTAR_AMAZONIA_LEGAL` | Polígono da Amazônia Legal | `True` |
| `IMPORTAR_FAIXA_FRONTEIRA` | Polígono da Faixa de Fronteira | `True` |

## Observações

- O script detecta automaticamente se o arquivo está em formato `.gpkg` ou `.shp`
- Para arquivos SHP, todos os arquivos complementares (.shx, .dbf, .prj, etc.) devem estar na mesma pasta
- O nome base do arquivo deve ser o mesmo (ex: `municipios.shp`, `municipios.shx`, etc.)