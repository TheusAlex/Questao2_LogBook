#### PASSO A PASSO ####

1 - Importação de biblioteca: 'panda' (É uma biblioteca para manipulação de dados.
                              'data_table' (É uma extensão do Google Colab para deixar a exibição interativa de DataFrames.

2 - Configuração do data_table: habilita o formato interativo para exibir no ambiente Colab.

3 - Carregamento de dados do CSV para DataFrame: Onde faz a leitura do arquivo info_transportes.csv e é carregado no dataframe.

4 - Conversão das Colunas de data para o formato adequado: Fiz conversões da data_inicio e data_fim, conforme solicitado no desafio.

5 - Agrupamento e agregações dos dados: Foi feito uma condição/métrica de dados por data_inicio como contagem, soma e média.

6 - Exibição do dataframe resultante usando data_table: Que exibe o DataFrame de uma forma mais interativa usando Data Tabela e excluindo padrão.


Obs: Para executar este código, certifique se o arquivos CSV (info_transporte.csv) esta no caminha especificado, caso não for executar somente terá a leitura do código eu fiz a exportação do arquivo final, 
'info_corridas_do_dia.csv' no projeto para validação/correção. 
