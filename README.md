<h1 align="center"> SQL_python_Covid19_analysis </h1>
 
 ## Descrição do projeto
  
  O objetivo do projeto consiste em fazer o download de um banco de dados disponibilizado no dropbox e efetuar algumas análises  após o tratamento desses dados. Para isso foi gerado um arquivo Jupyter para executar os processos necessários, desde o download do arquivo database, passando pela manipulação do banco de dados utilizando a biblioteca SQlite3 e, por fim, tratando os dados e gerando os resultados esperados.
  Buscou-se responder as seguintes questões:
  - Como foi a evolução diária dos casos?
  - Qual a influência da campanha de vacinação no número de mortes diárias?
  
 ## Descrição da solução
   Primeiramente foi feito o download do database e executada uma query utilizando a biblioteca Pandas para identificar o schema de cada tabela presente no banco de dados. O banco em questão consiste num conjunto de 83 tabelas com informações sobre a evolução da pandemia de Covid19 em diferentes distritos da Índia e, uma vez que a coleta desses dados ocorreu de forma descentralizada, cada distrito registrou um conjunto diferente de informações, o que gera uma barreira adicional no tratamento dos dados.
   
   Na sequência foi criada a função para gerar a conexão com o banco de dados e executar as queries necessárias em cada análise. Com isso, se deu inicio à resposta para a primeira questão. Foram extraídos os dados de novos casos diários em 4 diferentes distritos, utilizou-se de INNER JOIN para contornar as datas que estejam faltando em alguma das tabelas e  foram ordenados pela data.
   
  Como uma parte importante da análise, foi avaliada a questão dos dados NaN, os quais poderiam prejudicar o resultado. Primeiramente foi utilizada a função isnull() para verificar os dados inadequados, encontrando 26 incidências nos dados referentes ao distrito de Delhi. Como é um número pequeno comparado ao tamanho dos dados utilizados, optou-se por excluir os dados referente a essas datas da análise. Por fim, foram plotadas as curvas de casos diários para os 4 distritos analisados assim como para o somatório desses.
  
  Além disso, o processo foi repetido para responder a segunda questão, porém dessa vez explorando outros conjuntos de dados para entender como se da o resultado da vacinação no número diário de mortes nos distritos estudados. Para isso foram somados os dados de vacinação assim como os dados de mortes para que pudesse plotar num gráfico x-y, após o tratamento novamente dos dados NaN.
  
  
  
 ## Resultados 
  Os resultados obtidos foram plotados nos gráficos apresentados a seguir. Como a análise ocorreu com a finalidade de compor portfólio, foram selecionadas somente uma parte das regiões, assim como um número limitado de questões a serem respondidas. Logo é possível executar análises mais completas com os dados presentes no database em questão. 
  
  ### Casos diários
  A partir do gráfico apresentado podem ser observados alguns detalhes como os picos de contaminação que coincidem principalmente com o surgimento de novas variantes e alivio de medidas restritivas, assim como pode ser verificado que o distrito de Kerala foi o que mais enfrentou dificuldades para controle da contaminação dentre os distritos estudados, o que demandaria uma concentração dos esforços nessa região.
  <p align="center">
 <img src="/Images/DailyCases.png"  width="800" height="400"
 </p>
 
  ### Influência da campanha de vacinação
  
  Pode ser verificado que a quantidade de vacinas aplicadas na população exerce uma grande influência na redução do número diário de mortes, levando rapidamente a um número controlado apesar dos picos de contaminação encontrados no segundo trimestre de 2021. Pode ser destacado um rápido pico no número de mortes mesmo após a situação aparentemente controlada, o que se justifica pela nova variante que afetou o país nesse período, logo a vacina que estava sendo utilizada ainda não protegia de forma adequada contra essa variante.
  <p align="center">
 <img src="/Images/Vaccination.png"  width="800" height="400">
  </p>
 
