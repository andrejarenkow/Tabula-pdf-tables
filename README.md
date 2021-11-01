# Leitura das tabelas do arquivo

O notebook deste repositório é um exemplo de como é possível extrair as tabelas de um arquivo pdf, que muitas vezes pertence a algum laudo de análise, ou algum documento emitido por algum órgão governamental.

O arquivo de exemplo é uma [análise de água](http://www.viapol.com.br/media/468572/manta-asf%C3%A1ltica-2019-laudo-de-potabilidade.pdf) disponibilizado na internet.
A ideia é buscar as tabelas que são interessantes no arquivo, e juntá-las.

Analisando o arquivo pdf, as tabelas que nos interessam estão apenas nas páginas 1, 2, 3 e 4. Sendo assim, colocaremos este parâmetro na função *read_pdf*.

Também faremos uso do parâmetro *lattice*, que refere-se a buscar tabelas que tenham linhas separadoras.

Esta função devolverá uma lista de DataFrames (**dfs**), dentre os quais utilizaremos somente os dfs 3,5,6,8,9,10,12. 

Como queremos juntar todas tabelas em uma só, é fundamental que tenham as mesmas colunas, com os mesmos nomes, para que encaixemos uma abaixo da outra.

As os dfs 5, 6, 8 e 9 iguais, sendo assim alteramos apenas os nomes das colunas com um *loop* **FOR** e concatenamos um embaixo do outro.

Os dfs 3, 10 e 12 precisaram de alguns ajustes, pois não tinham as mesmas colunas, sendo necessário excluir ou incluir valores.

Por fim, deletou-se as linhas que possuíam algum *NaN*.

Assim, é possível exportar a tabela como arquivo *Excel* e analisá-la separadamente, ou criar um banco de dados.
