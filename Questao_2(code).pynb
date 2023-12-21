import pandas as pd
from google.colab import data_table
from vega_datasets import data

data_table.enable_dataframe_formatter()

# Carregar os dados do CSV para um DataFrame
df = pd.read_csv('data/csv/info_transportes.csv')

# Converter as colunas de data para o formato adequado
df['DATA_INICIO'] = pd.to_datetime(df['DATA_INICIO'], errors='coerce')
df['DATA_FIM'] = pd.to_datetime(df['DATA_FIM'], errors='coerce')

# Agrupar os dados pela data de início e formatar as colunas de distância
grouped_data = df.groupby(df['DATA_INICIO'].dt.date).agg(
    QT_CORR=('DATA_INICIO', 'count'),
    QT_CORR_NEG=('CATEGORIA', lambda x: sum(x == 'Negocio')),
    QT_CORR_PESS=('CATEGORIA', lambda x: sum(x == 'Pessoal')),
    VL_MAX_DIST=('DISTANCIA', lambda x: round(x.max(), 2)),
    VL_MIN_DIST=('DISTANCIA', lambda x: round(x.min(), 2)),
    VL_AVG_DIST=('DISTANCIA', lambda x: round(x.mean(), 2)),
    QT_CORR_REUNI=('PROPOSITO', lambda x: sum(x == 'Reuniao')),
    QT_CORR_NAO_REUNI=('PROPOSITO', lambda x: sum(pd.isna(x) or (not pd.isna(x) and not x.startswith('Reuniao')) for x in x))
).reset_index()

# Exibir o DataFrame resultante usando data_table
data_table.DataTable(grouped_data, include_index=False)
