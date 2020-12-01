# data-mart-investimento-pre-vestibular-sc

O trabalho feito para a realização de um Data Mart que tem como o objetivo encontrar os melhores municípios ou regiões para o investimento e implantação de cursos pré-vestibulares no estado de Santa Catarina, com o objetivo de apoiar a tomada de decisão dos envolvidos no processo. Primeiramente foi modelado um esquema estrela que fosse possível conter as questões referentes a média de acertos, o percentual de inscritos, percentual dos que fizeram curso pré-vestibulares por localização. A realização do Data Mart foi possível através dos dados disponibilizados pela Coperve dos vestibulares da Universidade Federal de Santa Catarina entre anos 2008 a 2012, também foi utilizados referente à economia das regiões disponibilizados no IBGE no ano de 2014. A realização do back-end foi feita através do Kettle com o software Pentaho e o Power BI para o front-end.

## Organização

Esse repositório é dividido em três arquivos, sendo eles referentes ao [back-end](https://github.com/marinastavares/data-mart-investimento-pre-vestibular-sc/tree/main/back-end), [front-end](https://github.com/marinastavares/data-mart-investimento-pre-vestibular-sc/tree/main/front-end) e os [assets](https://github.com/marinastavares/data-mart-investimento-pre-vestibular-sc/tree/main/assets).

No arquivo de back-end se encontram os arquivos relacionados ao desenvolvimento do processo de ETL, contendo também arquivos json da base de dados multidimensional criada através deste processo no MySQL, a qual segue o esquema estrela proposto pelo grupo.

No arquivo front-end encontra-se as imagens geradas no Software Power PI.

E por fim, o assets encontram-se arquivos utilizados para a base de dados referentes as regiões brasileiras, como também o arquivo com o documento final do projeto.

## Rodando o projeto

### Execução do ETL

Para o processo de ETL, é necessário a instalação do software Pentaho Data Integration, sendo a versão 9.1 utilizada para a criação dos arquivos deste repositório. Além disso, para ser possível a conexão com o servidor MySQL é necessária a inclusão do driver para o MySQL na pasta lib do Pentaho, e o arquivo dump deve ser rodado para geração das tabelas no MySQL. Após o setup necessário do ambiente, os seguintes passos podem ser seguidos para a execução do processo de ETL:

1 - Criar uma conexão `transacional` conectando à base de dados `vestibular` que foi gerada através do arquivo dump no MySQL;

2 - Criar uma conexão com o MySQL nomeada `multidimensional`, para onde serão carregadas as tabelas do modelo dimensional;

3 - Conferir se as entradas dos arquivos `.ktr` estão conectados de forma correta à conexão `transacional`, com exceção da entrada de dados do Microsoft Excel na dimensão `cidade`, a qual deve estar conectada à [base de dados do IBGE](https://github.com/marinastavares/data-mart-investimento-pre-vestibular-sc/blob/main/assets/base_de_dados_2014.xls);

4 - Conferir se as saídas dos arquivos `.ktr` estão conectados de forma correta à conexão `multidimensional`;

5 - Rodar o job [JOB](https://github.com/marinastavares/data-mart-investimento-pre-vestibular-sc/blob/main/back-end/job.kjb) para executar as transformações e carregar os dados para o Data Mart.

