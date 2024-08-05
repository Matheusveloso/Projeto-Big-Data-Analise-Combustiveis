# Projeto-Big-Data-Analise-Combustiveis
Analise de preços dos combustíveis no Brasil de 2004 a 2022: Utilizando PySpark. Projeto desenvolvido na disciplina de Gerência de Grande Volumes de Dados, no mestrado em ciência da computação pela Universidade Federal Fluminense - UFF.

Projeto Desenvolvido pelos alunos:
- Matheus Veloso (mthsveloso@hotmail.com; matheusveloso@id.uff.br)
- Alexandre Gantos (alexandre gantos@id.uff.br)
- Lucas Dirk (lucasdirk@id.uff.br)
- Gustavo Silva (gsrocha@id.uff.br)

https://drive.google.com/file/d/1VzDusmb9LnGLVcGL_UXr6GnJ_pWop7QR/view?usp=sharing

## Introdução

A variação dos preços dos combustíveis impacta de forma direta ou indiretamente a vida de grande parte da população, seja associado ao próprio transporte ou mesmo ao custo agregado aos demais bens de consumo. Nos últimos anos, tem sido observado mudanças significativas nos preços dos combustíveis. Essa variação ̃é resultado de diversos fatores, como oferta e demanda, políticas governamentais, eventos geopolíticos, entre outros motivos. Neste relatório, será analisada a variação de preços dos combustíveis em diferentes postos do Brasil, no período de 2004 a 2022.

## Objetivo
Como objetivo primário desse estudo, analisar os dados de venda de combustíveis entre os anos de 2004 a 2022, utilizando a base de dados disponibilizada pela Agência Nacional de Petróleo, Gás Natural e Biocombustíveis (ANP). Os objetivos secundários deste estudo são:

1) Analisar a evolução dos preços de combustíveis ao longo do tempo
2) Analisar as vendas de combustíveis por região
3) Analisar a variabilidade dos preços de combustíveis entre as regiões.
4) Compreender o impacto das políticas públicas nos preços de combustíveis

## Metodologia

### Coleta de Dados e Montagem da Base
- Importação da base de dados dos anos de 2004 a 2022, gerados e fornecidos pela Agência Nacional de Petróleo

### Processamento de Dados
- Realização dos tratamentos de dados através da plataforma do google colab,  e utilizando PySpark
- Transformação dos dados para o formato Parquet
- Seleção dos melhores atributos para análise

### Análise de resultados
- Realização de agregações 
- Desenvolvimento de gráficos

## Base de Dados

Para realizar as análises, foram considerados os dados disponíveis em [gov.br/anp 2023],no qual foram gerados e fornecidos pela Agência Nacional de Petróleo, Gás Natural e Biocombustíveis (ANP). 

Esses dados abrangem informações sobre os preços praticados pelos postos de gasolina em relação aos derivados de petróleo, gás natural veicular e biocombustíveis e são utilizados tanto como referência de mercado quanto para nortear políticas públicas.

Base disponível no site: 
https://www.gov.br/anp/pt-br/centrais-de-conteudo/dados-abertos/serie-historica-de-precos-de-combustiveis

A Base Possui um total de 20.873.955 de registros e 16 atributos, sendo eles: 
- Região - Sigla
- Estado - Sigla
- Município
- CNPJ da Revenda
- Número Rua
- Bairro
- Produto
- Valor de Venda
- Unidade de Medida
- Revenda
- Nome da Rua
- Complemento
- Cep
- Data da Coleta
- Valor de Compra
- Bandeira

## Processamento de dados
Inicialmente, criou-se um dataframe Spark a partir de 36 arquivos CSV separados, cada um contendo informações correspondentes a um determinado ano e semestre, de 2004 a 2022.

Esses arquivos foram combinados resultando em 2.3 GB, 16 colunas e 22.214.364 linhas.

As colunas que foram mantidas relacionadas a Data. Região(UF e município), Bandeira, CNPJ,  Produto,  a coluna referentes às vendas e Unidade de Medida.

Por fim, a transformação do data frame em formato Parquet demonstrou ser altamente benéfica, uma vez que o tempo de processamento para abrir o arquivo foi reduzido significativamente para apenas 0.30 segundos.

## Análise dos Dados

Nessa etapa foi realizado processos de agregações dos dados e desenvolvimento gráficos para visualização dos dados, no qual foram desenvolvido as seguintes analises:
1) Realizou-se o cálculo da média dos preços, dos combustíveis no período de 2004 a 2022
![image](https://github.com/user-attachments/assets/dd42ab6a-5220-4975-8f6d-5784c669bed5)

2) Já no gráfico 2, conseguimos ver a variação da média do valor dos produtos ao longo dos anos de 2004 a 2022.
![image](https://github.com/user-attachments/assets/b73c8284-e307-4cd8-a3a1-22f78b9f353b)

3) Já no gráfico 3, onde conseguimos observar os 5 postos de gasolina com maior média de preço no ano de 2022.
![image](https://github.com/user-attachments/assets/0eafee85-7888-4b82-a03a-e0988f37ff1e)

4) A tabela 4 apresenta informações sobre as cinco cidades que apresentaram maior desvio padrão no valor de venda dos combustíveis no ano de 2022
![image](https://github.com/user-attachments/assets/5f497ae1-e0ab-475f-b631-b7e35a36e65c)

5) Municípios com maior valor de venda de combustíveis entre os anos de 2004 e 2022.
![image](https://github.com/user-attachments/assets/75eee359-cb59-47d2-83da-a206f120595d)

6) Municípios com maior desvio padrão no preço de venda dos combustíveis entre os anos de 2004 e 2022
![image](https://github.com/user-attachments/assets/5694231e-4957-476f-8e0e-af4990c086fe)

7) Série temporal do preço da gasolina, em real, dólar e brent.
![image](https://github.com/user-attachments/assets/8c94c7f4-9ad2-457e-8253-9315189e3d90)

8) Mapeamento dos preços médios da gasolina por UF.
![image](https://github.com/user-attachments/assets/98d7e898-413e-4ab6-b28c-36dea9c0efb4)

9) Mapeamento dos preços médios da gasolina por Município.
![image](https://github.com/user-attachments/assets/95e8d0f4-74b2-4918-9a34-59a156aac7bc)

## Conclusão

Utilizando a poderosa combinação de Python e Apache Spark os dados obtidos foram otimizados para melhor processamento e consequente facilidade na pesquisa exploratória.

Ao longo deste estudo foi possível analisar por diversas frentes os dados disponíveis quanto á precificação dos combustíveis na Brasil.

Foi verificada a evolução dos preços ao longo do período disponível na base de dados,  além de identificadas as cidades mais caras e de maior variação de preço.

## Trabalhos Futuros

O primeiro ponto para trabalhos futuros seria a indicação á própria ANP de regiões onde seria importante aumentar o investimento da pesquisa. Já que as metas de crescimento da amostragem não são tão específicas.

O segundo ponto seria a busca por possíveis fraudes nos postos já presentes na pesquisa.

O terceiro ponto seria utilizar métodos de aprendizado de máquina para treinamento de classificador na identificação de anomalias ou de possíveis fraudes de postos.


