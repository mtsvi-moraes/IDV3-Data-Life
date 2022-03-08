# IDV3 - Grupo Data-Life


## CONTEÚDO

1. [INTRODUÇÃO](#INTRODUÇÃO)
2. [MATERIAIS E METODOS](#MATERIAIS-E-METODOS)
3. [FONTES DE DADOS](#FONTES-DE-DADOS)
5. [ESTATISTICA DISCRITIVA](#ESTATISTICA-DISCRITIVA)
6. [PREPARAÇÃO DOS DADOS](#PREPARAÇÃO-DOS-DADOS)
7. [TÉCNICAS DE MODELAGEM](TÉCNICAS-DE-MODELAGEM)
8. [DESIGN DE TESTES](#DESIGN-DE-TESTES)
9. [BIBLIOGRAFIA](#BIBLIOGRAFIA)
10. [SOBRE NÓS](SOBRE-NÓS)



## INTRODUÇÃO:

<p>A pandemia que teve início em 2019 (COVID-19) causada pelo novo coronavírus SARS-CoV-2 trouxe a realidade do preparo de diversos setores na prevenção contra esse tipo de evento e continua sendo um desafio para os sistemas de saúde. O diagnóstico imediato e efetivo da doença é um fator chave para as decisões clínicas e para compreensão do processo de infecção, fornecendo embasamento para decisões quanto a políticas públicas, por exemplo.
O teste mais utilizado para o COVID-19 utiliza transcrição reversa seguida de reação em cadeia da polimerase em tempo real (RT-PCR). No entanto, estes testes costumam ser mais caros e demorados. Além disso, a falta de disponibilidade no início da pandemia e atraso nos resultados resultou na opção por testes mais rápidos. Testes sorológicos, por sua vez, são baseados na comprovação da presença de anticorpos no sangue, e, apesar de apresentarem uma menor sensibilidade são de baixo custo, mais acessíveis e rápidos. Todas as metodologias apresentam características diferentes e geralmente o diagnóstico depende não somente do exame, mas do histórico clínico e probabilidade de risco. A falta de diagnóstico correto pode acarretar um tratamento médico equivocado e uma fragmentação da informação sobre o avanço da pandemia.
O Instituto Butantan, uma instituição renomada em pesquisa e principal produtor de imunobiológicos do Brasil, em parceria com o governo do estado de São Paulo realizou diversas ações de testagem populacional para detecção do COVID-19, principalmente em populações em casos de vulnerabilidade utilizando testes sorológicos. Mediante as testagens foi realizado um inquérito epidemiológico para coletar informações sintomáticas, sociais, econômicas e condições de saúde dos indivíduos. Além do monitoramento da doença, o objetivo foi compreender o processo de infecção e fatores importantes de diagnóstico. 
Apesar de diversos estudos, ainda é desconhecido fatores chaves da infecção e indicadores, mesmo quando tratamos sobre sintomas e a interação entre estes.  Os sintomas mais citados na literatura como indicadores de infecção por COVID-19 foram dor de cabeça, febre, tosse, diarreia, hiposmia e anosmia. O uso de modelos de previsão pode ser uma estratégia chave especialmente em um contexto de recursos limitados que se utiliza da combinação de fatores para estimar a probabilidade de um indivíduo estar infectado e vai ao encontro da demanda social para entendimento de doenças e riscos de propagação e evolução de possíveis futuros eventos. </p>


### MATERIAIS E METODOS

Os recursos necessários para o desenvolvimento do projeto foi uma equipe totalmente dedicada ao projeto composta pelo product owner, scrum master e três desenvolvedores. Uma equipe parcialmente dedicada ao projeto composta por consultor funcional e um consultor técnico. Foram necessários equipamentos como notebooks, ambientes de desenvolvimento e repositórios.

### FONTES DE DADOS:

A base de dados utilizada neste estudo é categorizada como dados em painel com periodicidade diária contemplando observações não-únicas, com disponibilização de cento e uma variáveis. Ela foi disponibilizada através do Instituto Butantan, e se provém dos inquéritos epidemiológicos coletados em todo o Brasil, mas com maior ênfase no estado de São Paulo.

## PREPARAÇÃO DOS DADOS

  Dos dados recebidos do Butantã, a partir de um arquivo csv com aproximadamente 1.3 milhões de dados descritivos e mais de 100 colunas, foram identificadas colunas potenciais, que incluíam sintomas e condições sociais relativas a pacientes com covid-19 com o objetivo de identificar potenciais casos da doença. 
A partir de conversas com o cliente, o total de 100 colunas foram resumidas para um total de 35 colunas que mais representavam a doença, bem como representava as colunas que eram utilizadas, uma vez que outrora muitas colunas foram descartadas a longo do tempo, ou então não foram respondidas pelo paciente.

* SELEÇÃO DE VARIÁVEIS

  A base de dados utilizada neste estudo é categorizada como dados em painel com periodicidade diária contemplando observações não-únicas, com disponibilização de cento e uma variáveis.
Dada a disponibilidade, um melhor controle e limpeza da base foi necessária para obter uma melhor escolha ótima do modelo utilizados, com a divisão em cinco categorias, sendo elas:

Identificação da observação: Sexo, localização e idade
Socioambiental: Trabalho, residência e contato
Condição de saúde: Doenças anteriores e estado de saúde
Sintomas: Sintomas apresentados na data de coleta do exame
Resultado: Resultado do teste de Covid-19.

Para a seleção preliminar de variáveis, fora decidido seis etapas para a determinação da exclusão ou não de uma variável, sendo os itens a seguir:

- Entrevista preliminar com epidemiologistas
- Informações faltantes
- Variáveis com informações duplicadas ou já incluídas
- Amplitude das informações
- Fora do escopo do projeto ou não aplicável
- Observações fora do estado de São Paulo

  A entrevista ocorrida no dia 31/08/2021 com as epidemiologistas Elaine Cristina Marqueze e Claudia Renata dos Santos Barros ligadas ao Instituto Butantan foi deveras esclarecedora acerca de diversas variáveis da base de dados disponibilizada, assim permitindo um melhor entendimento e a decisão de permanências de cinquenta variáveis, sendo estas escolhidas pelo baixo índice de informação faltante, a congregação de colunas com informações duplicadas e a alta relevância acerca do entendimento da doença através da entrevista realizada.
A decisão de não incluir observações que ocorreram fora do estado de São Paulo foi tomada por conta do alto número de informações faltantes de testes realizados fora do mesmo e também por se tratar de um estudo de caso epidemiológico, onde fatores regionais distintos podem ocasionar em uma falsa interpretação do modelo.
Para a decisão de variável de controle, consideramos o teste igM (teste da Imunoglobulina M), pois ele representa uma infecção recente daqueles afetados da COVID-19, assim, dentro do escopo sugerido, é a variável que mais interessante se torna para a determinação se o indivíduo está ou não infectado, conforme Prazuck (2020), em testes rápidos pertencentes às empresas COVID-PRESTO® e COVID-DUO®  a presença do anticorpo igM é prevalecente até o décimo e quinto dia de infecção.

Variáveis escolhidas:

1. Identificação (2)
  - age_category
  - sex

2. Condição (18)
  - puerperal
  - hematological_disease
  - neurologicas_disease
  - tumor
  - autoimmune_diseases
  - other_comorbidity
  - pregnancy
  - disability
  - obesity
  - has_vaccine_flu
  - kidneys_disease
  - liver_disease
  - asthma
  - smoker
  - diabetes
  - lung_disease
  - heart_disease
  - high_pressure

3. Sintomas (15)
  - conjunctivitis
  - asymptomatic
  - abdomen_pain
  - chills
  - diarrhea
  - missing_smell
  - missing_tasy
  - nausea
  - body_pain
  - cough
  - fever
  - hard_breathe
  - head_pain
  - running_nose
  - throat_pain
   
5. Resultado (1)
  - result_igm

Em relação aos dados descartados com base nos parâmetros já esclarecidos anteriormente, apesar de terem sido descartados por não se adequarem ao modelo aqui proposto, podem apresentar uma alta relevância em estudos futuros a fundo.

Com o alto número de valores faltantes entre todos os cinco data sets, a solução para tornar esta base de dados aplicável para uma solução utilizando-se ferramentas de machine learning foi a imputação múltipla através da linguagem R, segundo Nunes et al (2010) uma vantagem da imputação múltipla em relação à imputação única é o fato de a imputação múltipla levar em conta a variabilidade entre imputações e, no caso do método BLR, por ter o componente Bayesiano embutido no procedimento, restringir a subestimação da variabilidade amostral, já que a cada vez (e são m vezes) que é ajustada a regressão da IM, um valor diferente é gerado. Segundo F. E. Harrel Jr. (2001), quando há mais de 15% de dados faltantes, na maior parte dos modelos é indicada a imputação múltipla. Portanto, como neste trabalho havia uma média de 20% ~ 60% de dados faltantes para algumas categorias dos data sets, justifica-se a aplicação da imputação múltipla.

A categoria da base de treino do modelo ou amplamente chamado como features também é transformado utilizando-se uma técnica de StandardScaler, na pacote da linguagem do python fornecido pela biblioteca SKlearn, segundo a informação da biblioteca, é necessário o uso desta transformação pois a uniformização do data set é um requerimento comum para diversos modelos de machine learning, estes modelos podem performar de maneira esdrúxula se as features não parecerem nem mais nem menos de uma uniformização de distribuição normal.


## TÉCNICAS DE MODELAGEM

1. Fase inicial: A partir da biblioteca Pandas do Python, foram utilizados o método drop para remover todas as colunas que foram identificadas como não potenciais
2. Após a deleção de tais colunas, através do método isnull do pandas foram identificadas as colunas que não possuíam valores NaN (Valores nulos)
3. Após a identificação dos valores NaN, foram pensadas alternativas para o preenchimento desses valores. Em colunas que possuíam a grande maioria das linhas com valores NaN, elas foram removidas, uma vez que em tal condição, onde por exemplo, 99% dos valores são nulos, não é possível fazer uma estimação desses valores.
4. Após a identifcação de tais valores, em colunas onde era possível, através da biblioteca Scikit-learn, foi utilizado o método IterativeImputer para estimar valores nulos.
5. Concluindo esse ponto, foram dividos os treinos entre treino e teste e escolhido o modelo de predição, que incluem Random Forest, Logit e Softmax
6. Após isso, para melhorar o desempenho do nosso modelo, foi utilizado o modulo GridSearchCV da biblioteca Scikit-learn para otimização de hiperparametros do modelo de Machine Learning
7. Após a otimização dos hiperparâmetros, mais uma vez foi rodado o modelo com os melhores parametros e uma melhor otimização
8. Para concluir, foram mostrado métodos de avaliação de modelo como Matriz de confusão, curva ROC, e classification report
9. Para mais uma vez validar nossos estudos, foi utilizada a plataforma Watson da IBM com o AutoAI

![AutoAI](/gifs/autoai.gif)


## DESIGN DE TESTES E RESULTADOS

Para a definição de nossos parâmetros para uma melhor estimação, definimos que o melhor resultado gerado seria aqueles que levam em consideração o balanceamento dos dados, o peso deles e o threshold. Para a percepção de resultados, levamos em consideração os seguintes itens:

- Curva ROC
- Matriz de Confusão
- Sensibilidade
- Especificidade
- Acurácia

-![Resultados](/gifs/rf.png)

Na tabela acima vemos três critérios diferentes para a classificação de performance do modelo Santos et al (2019) define que a sensibilidade é a proporção de verdadeiros positivos (VP) entre todos os indivíduos cuja resposta de interesse foi observada, e a especificidade refere-se à proporção de verdadeiros negativos (VN) entre aqueles com resposta de interesse ausente, a acurácia indica uma performance geral do modelo.
Consideramos que modelo de classificação que mais se adequa aos nossos parâmetros de qualidade é a que utiliza o método de Regressão Logística, pois explorando os resultados de Sensibilidade, Especificação e Acurácia, a especificação e acurácia por possuírem valores muito próximos nos três modelos, a regressão logística se destacou no item de sensibilidade, isso quer dizer, que dentro do modelo, o número de acertos na previsão de pessoas que possuíam dentro do banco de dados o reagente positivo para igM foram de quarenta e quatro por cento, seguido posteriormente e com resultado bem próximo pelo modelo de Random Forest, com um resultado de quarenta e dois por cento, o modelo de Árvore de Decisão equiparados aos dois modelos citados anteriormente apresentou um pior resultado, de trinta e oito por cento.
Também no nosso critério de escolha, observamos os resultados obtidos através da geração da Curva ROC, que irá nos dizer um comparativo de sensibilidade do desempenho dos modelos que melhor performaram, obtendo o seguinte resultado.

-![ROC](/gifs/roc2.png)

Na imagem acima, com a observação apenas da curva, não é conclusivo afirmar qual a melhor performance obtida, porém, ao analisarmos a área que elas possuem, veremos que o resultado da regressão logística possui uma leve vantagem comparado aos demais modelos, cravando assim nosso critério de escolha.
Na tabela a seguir, observamos a influência das variáveis respostas no modelo LOGIT:

-![LOGIT](/gifs/filogit.png)

-![LOGIT](/gifs/fi2.png)

Apesar de uma pior performance pouco perceptiva no critério de sensibilidade, o modelo performado no método Random Forest também apresentou resultados satisfatórios na importância das variáveis no modelo, podemos observar na tabela e na imagem a seguir respectivamente:

-![LOGIT](/gifs/firf.png)

-![LOGIT](/gifs/fi1.png)

Com resultados divergentes entre algumas posições de importância de variável, podemos observar o destaque de uma em especial, a categoria de idade, esta variável nos mostra como a idade da população observada está sendo determinante para a predição dos diferentes métodos empregados, no modelo LOGIT apresentando uma resposta de 21,75 e no modelo de Random Forest com uma resposta de 44,06%. A variável sex também se mostrou relevante, com os dois modelos apresentando um viés de gênero. Com um comparativo entre os dois métodos empregados, apesar de serem bastantes heterogêneos e divergentes, abrem oportunidades para uma discussão mais profunda sobre o assunto.

## BIBLIOGRAFIA

- [IBM Cloud](https://www.ibm.com/cloud)
- [Watson Studio](https://www.ibm.com/cloud/watson-studio)
- [Watson Machine Learning](https://www.ibm.com/br-pt/cloud/machine-learning)
- [Watson IoT Cloud](https://www.ibm.com/cloud/internet-of-things)
- NUNES, N. L.; KLUCK. M. M.; FACHEL. G. J;  Comparação de métodos de imputação única e múltipla usando como exemplo um modelo de risco para mortalidade cirúrgica. In: Rev. bras. epidemiologia, 2010. Disponível em: < https://www.scielo.br/j/rbepid/a/ZRCFBZDGfKC3RqTkRpbXWsF/?lang=pt >
- F.E. HARREL JR. REGRESSION MODELING STRATEGIES In: BIOS 330. 2014. Disponível em < https://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.468.8845&rep=rep1&type=pdf >
https://scikit-learn.org/stable/modules/generated/sklearn.preprocessing.StandardScaler.html
- SANTOS, G. H; NASCIMENTO, F. C; IZBICKI, R; DUARTE, O. Y; FILHO, C. A. Machine learning para análises preditivas em saúde: exemplo de aplicação para predizer óbito em idosos de São Paulo, Brasil In Cad. Saúde Pública 35 (7)  2019. Disponível em < https://www.scielo.br/j/csp/a/jyhKL6G4dZhcbchMD6bcS8s/ >
- ESTEVES,  S.  R.;LORENA,  A.  C.;  NASCIMENTO, M.  Z.  Aplicação  de  técnicas  Aprendizado  de Máquina     na     Classificação     de     Imagens Mamográficas. In:  SIMPÓSIO  DE  INICIAÇÃO CIENTÍFICA  DA  UNIVERSIDADE  FEDERAL  DO ABC,2. 2009. Disponível em: <http://ic.ufabc.edu.br/II_SIC_UFABC/resumos/paper_5_150.pdf>
- DUBEY. R. ; ZHOU. J. ; WANG. Y. ; THOMPSON. M. P. ; YE. J. ANALYSIS OF SAMPLING TECHNIQUES FOR IMBALANCED DATA: AN N=648 ADNI STUDY. In: Neuroimage. 220–241 (2014). Disponível em <   .https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3946903/ >

## SOBRE NÓS
* [Erick Grabowski Crisóstomo](https://github.com/dudegrabow), Data Scientist
* [Juliana Machado](https://github.com/dementshuk), Product Owner
* [Gisela Petroni](https://github.com/G1s2l3), Data Scientist
* [Matheus Moraes](https://github.com/mtsvi-moraes), Data Scientist
* [Mauro Pereira](https://github.com/Karmelia69), Scrum Master

<p>
  <img src="https://contributors-img.web.app/image?repo=mtsvi-moraes/IDV3---Data-Life" />
</p>

## License

This project is licensed under the Apache 2 License - see the [LICENSE](LICENSE) file for details.

