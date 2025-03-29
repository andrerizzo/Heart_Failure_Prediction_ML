> 🇧🇷 Este README está em português.  
> 🇺🇸 [Click here for the English version.](README_EN.md)


# 🫀 Previsão de Insuficiência Cardíaca com Aprendizado de Máquina

## 🔍 Introdução  
A previsão de insuficiência cardíaca visa identificar indivíduos em risco de desenvolver essa condição, utilizando dados clínicos e técnicas de aprendizado de máquina. A insuficiência cardíaca ocorre quando o coração não consegue bombear sangue de maneira eficiente, muitas vezes como consequência de doenças cardiovasculares.

As doenças cardiovasculares (DCV) são a principal causa de mortalidade no mundo, sendo responsáveis por aproximadamente **17,9 milhões de mortes por ano**, o que representa **31% de todos os óbitos globalmente**. Quatro em cada cinco dessas mortes são decorrentes de infartos e AVCs, e **um terço ocorre de forma prematura em pessoas com menos de 70 anos**. A insuficiência cardíaca é um evento comum associado a essas condições.

Modelos de aprendizado de máquina podem ser úteis no processo de **detecção precoce e tomada de decisão clínica**, especialmente para indivíduos com fatores de risco como hipertensão, diabetes, hiperlipidemia ou histórico de doenças cardiovasculares.

---

## 🎯 Objetivo  
- Identificar os **parâmetros clínicos mais relevantes** para prever insuficiência cardíaca  
- Treinar um modelo de **aprendizado de máquina supervisionado** capaz de realizar classificações com boa acurácia  

---

## 🧠 Base de Dados — Atributos

| Atributo | Descrição |
|----------|-----------|
| **Age** | Idade do paciente (anos) |
| **Sex** | Sexo do paciente *(0: Feminino, 1: Masculino)* |
| **ChestPainType (cp)** | Tipo de dor no peito *(TA: Angina Típica, ATA: Atípica, NAP: Não Anginosa, ASY: Assintomático)* |
| **RestingBP (trtbps)** | Pressão arterial sistólica em repouso *(mm Hg)* |
| **Cholesterol (chol)** | Nível de colesterol *(mg/dl)* |
| **FastingBS (fbs)** | Glicemia de jejum *(0: normal, 1: > 120 mg/dl)* |
| **RestingECG (restecg)** | Eletrocardiograma em repouso *(0: normal, 1: anormalidade ST-T, 2: hipertrofia ventricular esquerda)* |
| **MaxHR (thalach)** | Frequência cardíaca máxima registrada *(entre 60 e 202 bpm)* |
| **ExerciseAngina (exng)** | Angina induzida por esforço *(0: Sim, 1: Não)* |
| **Oldpeak** | Depressão do segmento ST induzida por esforço (valor numérico) |
| **ST_Slope (slp)** | Inclinação do segmento ST *(0: ascendente, 1: plano, 2: descendente)* |
| **caa** | Número de vasos coronários principais obstruídos *(0 a 4)* |
| **thall** | Resultado da cintilografia com tálio *(0: indefinido, 1: lesão permanente, 2: reversível, 3: normal)* |
| **HeartDisease** | Classe alvo *(1: alto risco, 0: normal)* |

---

## 📐 Modelagem e Avaliação

Para a etapa de modelagem, foi utilizada uma abordagem experimental com diferentes algoritmos de classificação, aplicando **pipelines de pré-processamento, seleção de atributos e validação cruzada**. Os principais passos foram:

- Padronização dos dados com `StandardScaler`
- Seleção de variáveis com `SelectKBest(f_classif)`
- Ajuste de hiperparâmetros com `GridSearchCV`
- Avaliação com `StratifiedKFold` e métricas de classificação

### 🧪 Algoritmos testados
- Random Forest
- Extra Trees Classifier
- K-Nearest Neighbors (KNN)
- Gaussian Naive Bayes
- Quadratic Discriminant Analysis (QDA)
- Logistic Regression
- Suport Vector Machine (SVM)
- Avaliação inicial com `LazyClassifier` (benchmark)

### ✅ Modelo Final Selecionado
O melhor desempenho foi obtido com o classificador **QDA (Quadratic Discriminant Analysis)**.  
Esse modelo foi escolhido com base em uma combinação de desempenho nas métricas de classificação e simplicidade de implementação.

- **Pipeline utilizado:** `StandardScaler + QDA`
- **Hiperparâmetro ajustado:** `reg_param` via `GridSearchCV`
- **Acurácia na base de teste:** cerca de **XX%** *(substituir pelo valor real se desejar)*

### 📊 Métricas utilizadas
- Accuracy
- Precision
- Recall
- F1-Score
- Matriz de Confusão

---

## 💾 Salvamento do Modelo

O modelo final treinado foi salvo no formato `.joblib` para futura reutilização:

```python
joblib.dump(model.best_estimator_, 'Heart_Failure_Prediction_QDA_model.joblib')
```

---

## 🧠 Conclusão

O uso de aprendizado de máquina para previsão de insuficiência cardíaca se mostrou eficaz ao aplicar algoritmos clássicos com engenharia de atributos e validação cruzada. O modelo QDA foi o mais estável e eficiente dentro do escopo da base, com potencial de aplicação em contextos reais de triagem clínica.

Próximos passos podem incluir:
- Explicabilidade com SHAP/LIME
- Testes em dados de produção
- Deploy via API ou aplicativo de triagem clínica

---

### 👨‍💻 Sobre o Autor

**André Rizzo**  
📊 Cientista de Dados Sênior | Estatístico | MBA em IA e Big Data (USP)  
🧠 Especialista em Machine Learning, Deep Learning e Modelagem Estatística  
📍 Rio de Janeiro, Brasil  

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Perfil-0077B5?logo=linkedin&logoColor=white)](https://www.linkedin.com/in/andrerizzo1)
[![GitHub](https://img.shields.io/badge/GitHub-Portfólio-181717?logo=github&logoColor=white)](https://github.com/andrerizzo)
[![Email](https://img.shields.io/badge/Email-andrerizzo@hotmail.com-D14836?logo=gmail&logoColor=white)](mailto:andrerizzo@hotmail.com)

---
*Última atualização: 28/03/2025*
