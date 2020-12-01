# data-mart-investimento-pre-vestibular-sc

O trabalho feito para a realização de um Data Mart que tem como o objetivo encontrar os melhores municípios ou regiões para o investimento e implantação de cursos pré-vestibulares no estado de Santa Catarina, com o objetivo de apoiar a tomada de decisão dos envolvidos no processo. Primeiramente foi modelado um esquema estrela que fosse possível conter as questões referentes a média de acertos, o percentual de inscritos, percentual dos que fizeram curso pré-vestibulares por localização. A realização do Data Mart foi possível através dos dados disponibilizados pela Coperve dos vestibulares da Universidade Federal de Santa Catarina entre anos 2008 a 2012, também foi utilizados referente à economia das regiões disponibilizados no IBGE no ano de 2014. A realização do back-end foi feita através do Kettle com o software Pentaho e o Power BI para o front-end.

## Organização

Esse repositório é dividido em três arquivos, sendo eles referentes ao [back-end](https://github.com/marinastavares/data-mart-investimento-pre-vestibular-sc/tree/main/back-end), [front-end](https://github.com/marinastavares/data-mart-investimento-pre-vestibular-sc/tree/main/front-end) e os [assets](https://github.com/marinastavares/data-mart-investimento-pre-vestibular-sc/tree/main/assets).

No arquivo de back-end se encontram os arquivos relacioando ao desenvolvimento ETL do processo, contendo também um json com todos os dados que seguem o esquema estrela proposto pelo grupo.

No arquivo front-end encontra-se as imagens geradas no Software Power PI.

E por fim, o assets encontram-se arquivos utilizados para a base de dados referentes as regiões brasileiras, como também o arquivo com o documento final do projeto.

## Rodando o projeto
