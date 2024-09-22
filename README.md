#### Introdução  
A previsão de insuficiência cardíaca é um processo que visa identificar indivíduos em risco de desenvolver essa condição, usando dados clínicos e técnicas de aprendizado de máquina. A insuficiência cardíaca ocorre quando o coração não consegue bombear sangue de maneira eficiente, muitas vezes devido a doenças cardiovasculares subjacentes.  

As doenças cardiovasculares são a principal causa de mortalidade no mundo, responsáveis por aproximadamente 17,9 milhões de óbitos anuais, o que representa 31% de todas as mortes globalmente. Quatro em cada cinco fatalidades por DCV são decorrentes de infartos e acidentes vasculares cerebrais, e um terço desses casos ocorre de forma prematura em pessoas com menos de 70 anos. A insuficiência cardíaca é um evento frequente associado a essas condições, e este conjunto de dados inclui 11 atributos que podem ser utilizados para prever a possibilidade de uma doença cardíaca.

Indivíduos com condições do sistema circulatório ou que apresentam alto risco cardiovascular (devido à presença de um ou mais fatores de risco, como hipertensão, diabetes, hiperlipidemia ou doenças já diagnosticadas) necessitam de detecção e manejo precoces, onde um modelo de aprendizado de máquina pode ser de grande auxílio.  

<br>

#### Objetivo  
* Identificar os parâmetros mais importantes no conjunto de dados para classificar com precisão os casos de insuficiência cardíaca.
* Treinar um algoritmo de aprendizado de máquina para reconhecer e classificar os casos de insuficiência cardíaca com precisão.  

<br>

#### Base de Dados - Atributos

* **Age**:&nbsp; Idade do paciente  *\[anos]*  
* **Sex**:&nbsp; Sexo do paciente *\[0: Feminino, 1: Masculino]*    
* **ChestPainType (cp)**:&nbsp; Tipo de dor no peito na chegada ao hospital*\[TA(0): Angina Típica,&nbsp; ATA(1): Angina Atípica,&nbsp; NAP(2): Dor Não Anginosa, &nbsp;ASY(3): Assintomático]*  
* **RestingBP (trtbps)**:&nbsp; Pressão arterial sistólica em repouso na chegada ao hospital*\[mm Hg]*    
* **Cholesterol (chol)**:&nbsp; Nível de colesterol na chegada ao hospital *\[mm/dl]*    
* **FastingBS (fbs)**:&nbsp; Glicemia de jejum *\[(0)Normal,&nbsp; Glicemia em jejum > 120 mg/dl]*    
* **RestingECG (restecg)**:&nbsp; Resultado do eletrocardiograma em repouso *\[Normal(0): normal,&nbsp; ST(1): anormalidade da onda ST-T (inversões da onda T e/ou elevação ou depressão do segmento ST > 0,05 mV),&nbsp; LVH(2): mostrando hipertrofia ventricular esquerda provável ou definitiva pelos critérios de Estes]*  
* **MaxHR (thalach)**:&nbsp; Frequência cardíaca máxima na chegada ao hospital *\[Valor numérico entre 60 e 202]*     
* **ExerciseAngina (exng)**:&nbsp; Angina induzida por exercício *\[0: Sim, 1: Não]*   
* **Oldpeak**:&nbsp; Depressão do segmento ST induzida por exercício em relação ao repouso *\[Valor numérico medido em depressão]*
* **ST_Slope (slp)**:&nbsp; Inclinação do segmento ST no pico do exercício *\[(0) ascendente,&nbsp; (1)plano,&nbsp; (2)descendente]*    
* **caa**:&nbsp; Número de vasos principais (0-3) evidenciados por fluoroscopia, refere-se ao número de artérias coronárias principais que apresentam obstruções significativas (estenoses) detectadas por um exame de imagem, geralmente uma angiografia coronariana realizada com auxílio de fluoroscopia.  
  * 0 &nbsp;: significa que nenhum dos vasos principais está obstruído.
  * 1 &nbsp;: indica que um vaso principal apresenta obstrução.
  * 2 &nbsp;: indica que dois vasos principais apresentam obstrução.
  * 3 &nbsp;: indica que três vasos principais apresentam obstruçâo.
  * 4 &nbsp;: indica que quatro vasos principais apresentam obstruçâo.
* **thall**:&nbsp; Resultado da cintilografia de perfusão miocárdica com tálio*\[(0)resultado indefinido,&nbsp; (1)lesão permanente,&nbsp; (2)lesão reversível, (3)perfusão normal,&nbsp;]*  
* **HeartDisease**:&nbsp; output class [1:Alto risco de falência cardíaca,&nbsp; 0:Normal]    
