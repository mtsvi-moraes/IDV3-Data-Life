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

<p>Over 1.8 billion people on Earth do not have access to adequate sanitation. Therefore, over 10 million people, with the majority being children, die every year due to the lack of safe drinking water. This is a major problem plaguing humanity, targeting the poorest populations, whose only source of drinking water are rivers that can become polluted unbeknownst to the people who rely on them.

Today, while scientific advancements are made daily, analyzing water quality is not a simple task. Researchers must travel to the region and collect individual samples. After which, the samples must then be  transported to a qualified laboratory where testing can be performed. Each of these crucial steps increase the time and monetary value spent on the expedition making it more difficult to receive funding and consequently alert the population.
Taking all of this into account, we developed SpecWater, a solution that aims to facilitate this process and improve access to safer water sources in all regions and in real time, for all humanity.

SpecWater uses Artificial Intelligence that analyzes the spectrum of light within a water sample collected by an IoT (a small equipment installed in rivers and lakes). After the analysis, results will be made available on an easily accessible website. Expanded functions such as the ability to trigger an alert via SMS, will also be available. When a water quality alert is sent, it will allow the population to be able to check the quality of the community source and view whether it has been contaminated, or if it’s safe to consume. Instructions regarding a separate source of drinking water will be provided if the community source tests confirm contamination thus, avoiding infant mortality, the human immunodeficiency virus, which is often found in contaminated water and several other serious health and nutrition problems. The responsible authorities will also be immediately alerted to take action and provide further assistance to the local population.</p>


### MATERIAIS E METODOS

According to a recent report made by the United Nations Children’s Emergency Fund (UNICEF) and the World Health Organization (WHO), one in three people worldwide does not have access to safe water. 
In many countries, taps, wells and pipes which are the only option for drinking water are contaminated unbeknownst by the population, putting the health of the ones who drink it at risk and making many sick.

### FONTES DE DADOS:

Every person needs a sustainable supply of clean water: for drinking, washing, cooking and cleaning. It is a basic human right and there are still millions of people who do not have clean water.

To date, governments, institutions and service providers around the world have not done enough to ensure that clean water reaches the poorest and most marginalized people.

Although COVID-19 highlights the importance of hand hygiene in preventing the spread of disease, billions of people around the world, including hundreds of millions of school-age children, do not have access to soapy washbasins. People living in rural areas, urban slums, disaster prone areas and low-income countries are the most vulnerable and the most affected. In addition, children who do not have clean water have not only their health affected, but also their nutrition, education and learning skills, impacting many aspects of their lives.

Given this, we have the sad realization that millions of people suffer annually, without water, sanitation and hygiene services.

### ESTATISTICA DISCRITIVA:

Once the Desk Research step is completed, we realize that the starting point is to create a solution that aims to facilitate the process of water analysis and make the quality in your region available to all humanity in real time, so that everyone can access the site whenever you want, alerts will also be issued when the water that supplies your region is contaminated, as well as instructions for another form of drinking water consumption, and allowing safe information to be shared.

In addition, the system will issue an alert for responsible authorities to take appropriate action.


## PREPARAÇÃO DOS DADOS

* Dos dados recebidos do Butantã, a partir de um arquivo csv com aproximadamente 1.3 milhões de dados descritivos e mais de 100 colunas, foram identificadas colunas potenciais, que incluíam sintomas e condições sociais relativas a pacientes com covid-19 com o objetivo de identificar potenciais casos da doença. 
* A partir de conversas com o cliente, o total de 100 colunas foram resumidas para um total de 51 colunas que mais representavam a doença, bem como representava as colunas que eram utilizadas, uma vez que outrora muitas colunas foram descartadas a longo do tempo, ou então não foram respondidas pelo paciente.

* SELEÇÃO DE VARIÁVEIS

  A base de dados utilizada neste estudo é categorizada como dados em painel com periodicidade diária contemplando observações não-únicas, com disponibilização de cento e uma variáveis.
Dada a disponibilidade, um melhor controle e limpeza da base foi necessária para obter uma melhor escolha ótima do modelo utilizados, com a divisão em cinco categorias, sendo elas:

Identificação da observação: Sexo, localização e idade
Socioambiental: Trabalho, residência e contato
Condição de saúde: Doenças anteriores e estado de saúde
Sintomas: Sintomas apresentados na data de coleta do exame
Resultado: Resultado do teste de Covid-19.

Para a seleção preliminar de variáveis, fora decidido seis etapas para a determinação da exclusão ou não de uma variável, sendo os itens a seguir:

Entrevista preliminar com epidemiologistas
Informações faltantes
Variáveis com informações duplicadas ou já incluídas
Amplitude das informações
Fora do escopo do projeto ou não aplicável
Observações fora do estado de São Paulo

A entrevista ocorrida no dia 31/08/2021 com as epidemiologistas ligadas ao Instituto Butantan foi deveras esclarecedora acerca de diversas variáveis da base de dados disponibilizada, assim permitindo um melhor entendimento e a decisão de permanências de cinquenta variáveis, sendo estas escolhidas pelo baixo índice de informação faltante, a congregação de colunas com informações duplicadas e a alta relevância acerca do entendimento da doença através da entrevista realizada.
A decisão de não incluir observações que ocorreram fora do estado de São Paulo foi tomada por conta do alto número de informações faltantes de testes realizados fora do mesmo e também por se tratar de um estudo de caso epidemiológico, onde fatores regionais distintos podem ocasionar em uma falsa interpretação do modelo.

Para a decisão de variável de controle, consideramos o teste igM (teste da Imunoglobulina M), pois ele representa uma infecção recente daqueles afetados da COVID-19, assim, dentro do escopo sugerido, é a variável que mais interessante se torna para a determinação se o indivíduo está ou não infectado, conforme Prazuck (2020), em testes rápidos pertencentes às empresas COVID-PRESTO® e COVID-DUO®  a presença do anticorpo igM é prevalecente até o décimo e quinto dia de infecção.

Variáveis escolhidas:

1. Identificação (5)
  - municipio
  - id_patient
  - sex
  - date_exam
  - age_category

2. Socioambiental (11)
  - department
  - test_worker
  - healthcare_professional
  - home_rooms
  - has_running_water
  - public_transport
  - has_traveled
  - presential_work
  - has_contact_hospital
  - has_contact_confirmed
  - has_contact_suspicious

3. Condição (18)
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

4. Sintomas (15)
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

Em uma exploração aos dados descartados com base nos parâmetros já esclarecidos anteriormente, apesar de terem sido descartados por não se adequarem ao modelo aqui proposto, podem apresentar uma alta relevância em estudos futuros a fundo.

Variáveis descartadas:

1. Condição (15)
  - Alto números de valores nulos
    - chest_tomography
    - pregnancy_trimester
    - x_ray_result
    - chronic_disease
    - had_dengue_confirmed
    - high_colesterol
  - Amplitude de informações
    - x_ray
    - had_baby
    - interned
    - previous_disease_assessment_symptomatic
    - had_dengue
  - Informações duplicadas ou já incluída
    - has_comobidity
    - comorbities_number
  - Fora do escopo da proposta
    - blood_type
2. Sintomas (4)
  - Alto números de valores nulos
    - weakness
    - fatigue
  - Fora do escopo da proposta
    - purple_marks
    - red_marks
3. Identificação (13)
  - Alto números de valores nulos
    - purpose_of_exam
    - latitude
    - longitude
  - Informações duplicadas ou já incluídas
    - pandemic_week_year
    - date_hour_exam
    - last_exam_by_document
    - insert_date
    - pandemic_week
    - year
  - Fora do escopo da proposta
    - city
    - last_exam_by_group
    - project
    - state
4. Resultado (6)
  - Alto números de valores nulos
    - previous_pcr_result
    - previous_quick_test_result
  - Amplitude
    - previous_covid_exam
  - Informações duplicadas ou já incluídas
    - soro_reagent_desc
    - soro_reagent
    - Fora do escopo do projeto
    - result_igg
    
5. Socioambiental (13)
  - Alto números de valores nulos
    - home_people
    - risk_occupation
    - work_people
    - butantan
    - family_income
    - formal_job
  - Amplitude
    - live_with_another_people
    - work_masks
    - work_windows
    - wear_mask
    - work_airy_environment
  - Fora do escopo da proposta
    - work_people_bin
    - work_city

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


## DESIGN DE TESTES

### Spectrophotometry research:
It is a method used to measure how much a chemical substance absorbs light by measuring the intensity of when a beam of light passes through a sample, making it possible to measure the quantity of a known chemical substance



### Arduino prototype:
We developed a spectrophotometry prototype in Arduino capable of analyzing water samples, which when in the future installed in rivers, streams, wells, springs and treatment plants will collect the water data and process them through cloud.



### Collection in the river:
The Tietê river, born in Salesópolis, in the Serra do Mar, crosses the state of São Paulo, bathing 62 municipalities. The river is at the top of the ranking of the most polluted rivers in Brazil, as it receives domestic and industrial sewage in the stretch of the capital where less than half of this sewage is treated. The analyzed sample was collected in the western region of the city, after the river had crossed the entire state capital on the border with the municipality of Osasco.



### Creation of an Arduino collector for spectrophotometry testing:
Taken from the point where the water runs calmly with a strong sewage odor using a plastic container and transferred to the test body applying the method of analysis according to the variation of the light beam through the substance without decanting of organic material.



### Data analysis
For this project, two samples were collected for analysis, one from safe water and the other from the most polluted river in Brazil, the Tietê river, located in the capital of São Paulo. Thus, we carried out a comparison between different samples and proved the efficiency of the chosen method, proving that the project is functionally applicable:



### Model algorithms, Auto AI 
We used a cognitive system applied in Watson Studio together with Watson ML to test different algorithms and compare the efficiency of the models, streamlining the analysis process between the collected samples, and in the future analyzing any changes or anomalies that will be immediately noticed in the rivers.:




### Web site 
The SpecWater website is available for desktops and mobile devices. It is possible to search the water quality by filtering the country or province where the user is located, as well as view the map where the IoT device was installed and the water sample was collected, and through a check mark, view the quality of the water and in the future receive instructions on how to treat it for consumption, until the responsible authorities take further actions.

You can check more details at: http://specwater.web.app




#### Consequently creating a complete monitoring system through which we can observe changes in the physical, chemical and biological characteristics of the observed water


## BIBLIOGRAFIA

- [IBM Cloud](https://www.ibm.com/cloud)
- [Watson Studio](https://www.ibm.com/cloud/watson-studio)
- [Watson Machine Learning](https://www.ibm.com/br-pt/cloud/machine-learning)
- [Watson IoT Cloud](https://www.ibm.com/cloud/internet-of-things)

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

