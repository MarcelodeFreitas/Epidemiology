# Exercício Introdutótio 3

[Enunciado Exercicio 3](https://github.com/jgrocha/covid-pt/blob/master/Jupyter/Ponto%20da%20Situa%C3%A7%C3%A3o%20em%20Percentagem.ipynb)
Considere o "Ponto da Situação", como apresentado pela DGS. Na imagem, o ponto da situação refere-se a 14 de maio de 2020. Estes dados aparecem agregados pelas regiões do Continente, designadas NUTS II, segundo a Nomenclatura das Unidades Territoriais para Fins Estatísticos (NUTS), estabelecida para a União Europeia.

![DGS Casos Covid-19](https://github.com/jgrocha/covid-pt/blob/master/Jupyter/imagens/situa%C3%A7%C3%A3o%20em%2020200514.png)

O Norte aparece com muitos mais casos do que as outras regiões. Será que assim é?

## Resolução

Dados:
- dados de covid do dia 19-05-2020 retirados do site da [DGS](https://covid19.min-saude.pt/)

![DGS Casos Covid-19 19-05-2020](https://github.com/MarcelodeFreitas/Epidemiology/blob/master/Exercises/images/dgs_19-05-2020.PNG)


- [dados geográficos do INE]https://inspire.ine.pt/SU/atom/gml/SU_StatisticalUnits_NUTSII2013_PTCont_EPSG3763.zip)
- [dados estatísticos do INE](https://github.com/jgrocha/covid-pt/blob/master/Jupyter/dados/BGRI11_PT.csv.zip)

Para a resolução deste exercício foi necessário a construção de um ficheiro .csv com a informação do número de casos em relação à quantidade de população relativa às regiões: Norte, Centro (PT), área metropolitana de Lisboa, Alentejo e Algarve.

De forma a calcular os casos por milhão de pessoas que está no ficheiro .csv acima mencionado pegaram-se nos casos confirmados e dividiu-se pelo número de residentes, multiplicando o resultado por 10^6.

1. Carregmento dos [dados geográficos do INE](https://inspire.ine.pt/SU/atom/gml/SU_StatisticalUnits_NUTSII2013_PTCont_EPSG3763.zip)

2. Carregamento dos [dados estatísticos do INE](https://github.com/jgrocha/covid-pt/blob/master/Jupyter/dados/BGRI11_PT.csv.zip)

3. Filtro dos dados estatísticos por NIVEL = 3 e criação de uma nova tabela apenas com estes valores.

4. Utilização da ferramenta de processamento "redefinir campos" para redefinir os nomes dos fields pois não foram diretamente detetados na operação anterior.

5. Atualização de "GEO_COD_DSG2 para corresponder ao field "name" da layer de dados geográficos, esta operação vai possibilitar a sua união.

4. Introdução manual do número de casos de covid-19 por região na nova tabela.

5. Construção de uma nova coluna com os casos por milhão de pessoas, para tal para tal dividiu-se o número de casos confirmados pelo número de residentes e multiplicou-se o resultado por 10^6.

6. União da tabela com os dados geográficos através do nome das regiões.

![Casos confirmados por milhão de pessoas](https://github.com/MarcelodeFreitas/Epidemiology/blob/master/Exercises/images/ex_3.PNG)


Verifica-se que no mapa criado apesar deste representar o número de casos por milhão as relações entre regiões permanecem inalteradas. 

