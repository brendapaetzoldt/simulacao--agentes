# Simulação de evacuação em enchente  
> Desenvolvido para a disciplina 85EAG - Engenharia de Software Orientada a Agentes do curso Engenharia de Software da Udesc - Ceavi.

Simulação multiagente na evacuação durante uma enchente no bairro Canta Galo na cidade de Rio do Sul - SC



## Table of Contents
* [Resumo](#resumo)
* [Introdução](#Introdução)
* [Trabalhos Relacionados](#Trabalhos-Relacionados)
* [Especificação e Implementação da Simulação](#Especificação-e-Implementação-da-Simulação)
* [Resultados e Discussão](#Resultados-e-Discussão)



## Resumo
Desastres como enchentes e alagamentos ocorrem com muita
frequência em todo o mundo, e suas consequenciais podem levar a grandes 
perdas. Esse tipo de desastre tambem pode afetar muita a parte economica de 
uma sociedade. O presente trabalho tem como objetivo simular esse tipo de
desastre na cidade de Rio do Sul, bairro do Canta Galo. A simulac¸ao acontece 
com agentes situados em pontos aleatorios do mapa, esse mapa é representado 
por um bairro. A metodologia de desenvolvimento aplicada nesse trabalho foi
a utilização da ferramenta de desenvolvimento NetLogo para simulação de ambientes e do software de georreferenciamento Qgis, para a criação do mapa do 
bairro.

<!-- You don't have to answer all the questions - just the ones relevant to your project. -->


## Introdução

O aumento da frequencia de enchentes, sejam elas de grande porte ou apenas alagamentos pontuais,
 causam grandes problemas na vida dos moradores que em alguns casos
precisam fazer outra rota para chegar ao seu trabalho, fica ilhado ou ate mesmo precisa abandonar 
sua casa e ir ate um abrigo disponibilizado pela prefeitura para poder-se manter 
em segurança com seus familiares ate que a situação normalize.  


Ciente das ocorrencias mais frequentes a cada ano no município, a Defesa Civil do
estado de Santa Catarina disponibiliza em seu site diversas informações uteis: como cotas
do rio por rua, rotas para a locomoçao pelas trans enchentes, metragem do rio em tempo
real, pontos de maior risco de acidentes geologicos e localização de abrigos. 


O Bairro Cantagalo e localizado na região norte da cidade, fazendo a ligação entre os
demais bairros da área urbana e a rodovia BR470 que leva a saída da cidade. Neste
bairro esta localizada a rua Prefeito Wenceslau Borini que possuí a sua cota de inundação
mínima 3,01 metros, sendo esta a menor cota registrada no município. O bairro conta com
um abrigo chamado: ”Abrigo Obra Kolping” na Rua Adolfo Kolping que e para onde os 
moradores das areas mais baixas do bairro se abrigam quando necessário. 


Foi desenvolvida uma simulaçao multiagente de evacuacção onde os agentes são
carros que, ao iniciar, sao colocados em diferentes pontos do mapa e precisam chegar até
o abrigo ou conseguir sair do bairro por alguma saída que nao esteja coberta d’agua. Na 
configuraçao do setup pode se optar pelas diferentes cotas de alagamento que impedem o
transito pelas ruas cobertas pela água. 


Apos execuções nos diferentes estados de alagamento das ruas do bairro foi 
possível compreender em como uma evacuaçao de veículos ocorre e quantos conseguem
sair do bairro em uma situaçao de enchente. Em cenários com níveis mais altos de
inundaçao, ou seja, em níveis mais altos, menos carros foram evacuados com sucesso
do que em comparaçao com os dados do cenário de cotas mais baixas. 




## Trabalhos Relacionados

Os trabalhos relacionados a seguir foram buscados atraves do Google Schoolar, após
identificar pontos e palavras-chave com relações no assunto proposto, como, por exemplo,
as palavras: simulação multiagente, NetLogo, simulação enchente e simulação evacuação. Assim foi possível identificar pontos que diferenciam este estudo dos demais e pontos que
serviram como referencia para o desenvolvimento. 

- A Simulação Baseada em Agentes na Logística Humanitária: Aplicações do Netlogo.

> DE SOUZA, I. C. A Simulação Baseada em Agentes na Logística Humanitária: Aplicações do Netlogo. 189f. Dissertação 
(Mestrado Profissional em Gestão e Desenvolvimento da Educação Profissional). Centro Estadual de Educação Tecnológica Paula Souza, 
São Paulo, 2019. [_here_](http://www.pos.cps.sp.gov.br/dissertacao/a-simulacao-baseada-em-agentes-na-logistica-humanitaria-aplicacoes-do-netlogo). 


- Consequências econômicas das inundações e vulnerabilidade: desenvolvimento de metodologia para avaliação do impacto nos domicílios e na cidade.
>Cançado, V. L. CONSEQÜÊNCIAS ECONÔMICAS DAS INUNDAÇÕES E VULNERABILIDADE: Desenvolvimento de metodologia para avaliação do impacto nos domicílios e na cidade.
[_here_](https://www.smarh.eng.ufmg.br/defesas/245D.PDF). 




## Especificação e Implementação da Simulação

Desenvolvida no ambiente da plataforma NetLogo, a simulação baseada em agentes é
composta por tres tipos diferentes de agentes: Observer (observador), turtles (agentes
que se movem) e patches (agentes estaticos). Este ambiente ou mundo em que habitam os 
agentes moveis (turtles) e formado por uma malha ou grade de patches que podem possuir
características distintas. E possível modelar e criar infinitas possibilidades de simulações 
com agentes de características e variaveis ilimitadas. Após criada a simulação, é possível
controla-la por botões, caixas de texto e sliders e acompanhar sua execução e resultados
em gráficos e monitores de informações configuráveis.


Para ser possível criar uma simulação com uma malha viária do bairro Canta Galo 
extremamente parecida com a realidade, foi utilizado um arquivo shapefile de georeferenciamento criado pelo IBGE - Instituto Brasileiro de Geografia e Estatística no software
QGis 3.28. Neste arquivo estao contidas as informações referêntes aos nomes de logradouros, bairros e geocódigos de todo o município, mas como o objetivo deste trabalho
e simular apenas o bairro citado acima, foi feito um recorte em suas divisas e todas as
informações dos demais bairros. 


A defesa civil de Rio do Sul disponibiliza em seu site as camadas em arquivos
shapefile referentes as cotas de inundação dos principais níveis monitorados de acordo
com estudos e observac¸oes realizados pela entidade. As camadas foram adicionadas sobrepondo as linhas de logradouro adicionadas anteriormente, assim foi possível visualizar
todo o bairro e alternar entre as cotas para visualizar como cada local e afetado pelas inundações. A figura 1 mostra uma visão geral de todas as ruas do bairro com todas as
suas camadas de inundação ativas no QGIS.

![Figura 1](https://user-images.githubusercontent.com/18469694/209573798-0b4c4f8a-3b26-41b1-abb7-7f5beab29d49.png)

Apos a exportação dos mapas, foi realizado o desenho para a Simulação no NetLogo. O metodo import-pcolors le um arquivo de imagem, dimensiona-o para as mesmas 
dimensoes da grade, mantendo a proporção original da imagem e transfere as cores de
pixel resultantes para os patches e e centralizada na grade de patches.
As cores de patch resultantes ficam um pouco distorcidas, pois o espaço de cores
NetLogo nao inclui todas as cores possíveis e tambem não trabalha bem com a mudança
entre cores e tons. Na imagem 2 e possível observar os mapas exportados e importados
pelo metodo import-pcolors.

![Figura 2](https://user-images.githubusercontent.com/18469694/209573790-b9e6db1a-1437-43f4-b15b-50c3ba566059.png)


Cada Patch possui uma cor e de acordo com ela sua natureza e definida. Caso a
cor do Patch seja preta, naquele momento aquela coordenada e um asfalto, se for branca
e um quarteirão e por fim, azul que é considerada uma área alagada. Os agentes carros só
podem transitar por Patchs de cor preta, já que esses representem estradas. Quando um 
dos agentes se deparar com um Patch azul ou branco, ele e impedido de seguir em frente.

Ao se deparar com uma cor diferente da preta ele da uma volta de 365° e então anda para 
frente novamente. Um agente tem sucesso quando consegue alcanc¸ar o ponto em que esta localizado
o abrigo ou quando ele consegue sair do bairro por alguma rua que nao esteja alagada e
fac¸a ligac¸ao com o fim do mapa. Enquanto isso não ocorre, ele anda sempre em frente 
evitando ruas alagadas e quarteiroes.




## Resultados e Discussão
Foram realizadas trinta execuções em cada cenário de alagamento da simulação, sendo 
dez com apenas vinte e cinco agentes carros no mapa, dez execuções com cinquenta 
agentes e por fim, o restante com cem carros. Em cada uma das execuções os agentes 
iniciavam em uma localização totalmente aleatória, por este motivo foi necessário repetir o experimento para evitar possíveis vieses nos resultados. A figura 3 aprenta a média dos resultados obtidos em todas as execuções. 


Percebe-se que na execução dos cenários com apenas vinte e cinco carros os resultados obtidos nas cotar de 9,5 metros e 10,5 metros nao houveram nenhuma diferença
na quantidade de carros que permaneceram na simulação após a execução de 200 ticks.
Os demais resultados nao variaram significativamente e permaneceram próximos uns dos outros.


Já no experimento realizado com cinquenta carros, os maiores resultados de 
agentes que nao conseguiram evacuar da simulação no período estipulado sao no cenário 
de cota de 7,5 metros e 13,5 metros, respectivamente a cota mais baixa e a mais alta
da simulação. O mesmo acontece quando foram colocados cem agentes na simulação, 
mas neste caso a maior quantidade acaba sendo no cenario de maior valor da cota de 
inundação. 


Um fator observaveldurante a simulação e ao analisar a imagem 2 e que quanto
mais alta e a cota de inundação mais saidas do mapa são bloqueadas pela agua. Com
menos rotas para sair do bairro em momentos de cheia, os carros acabam se afunilando e
tendo difuculdade para evacuar.


A figura 4 apresenta o desvio padrao ocorrido das execuções realizadas. Não
foram identificados grandes valores de desvio padrao na média das simulações realizadas, isso significa que dentre os resultados obtidos em todas as execuções, a quantidade de agentes que nao conseguiram evacuar da simulação foi bastante homogêneo.


![Figuras 3 e 4](https://user-images.githubusercontent.com/18469694/209573796-044df116-90df-4743-a199-4ba082c269d1.png)
