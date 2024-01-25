# Modelo preditivo com Azure ML <h1>

## Descrição de todo o processo, da configuração do Azure ML ao teste do modelo preditivo <h2>

### Objetivo: <h3>
Neste exercício, o recurso de machine learning automatizado no Azure Machine Learning foi utilizado para treinar e avaliar um modelo de machine learning, incluindo todos os passos de configuração, deploy e teste do modelo treinado.

O aprendizado de máquina automatizado permite a experimentação de vários algoritmos e parâmetros para treinar distintos e inúmeros modelos e identificar qual o melhor para os dados e retorno desejado. Neste exercício, foi usado um conjunto de dados de detalhes históricos de aluguel de bicicletas para treinar um modelo que prevê o número de aluguel de bicicletas esperado em um determinado dia, com base em características sazonais e meteorológicas.

#### Criando um espaço de trabalho do Azure Machine Learning <h3>

Para utilizar o Azure Machine Learning, é necessário provisionar um espaço de trabalho do Azure Machine Learning na sua subscrição do Azure. Depois, você poderá usar o estúdio Azure Machine Learning para trabalhar com os recursos do seu espaço de trabalho.

Para os detalhes de como executar as configurações acesse o link e siga as instruções: <https://microsoftlearning.github.io/mslearn-ai-fundamentals/Instructions/Labs/01-machine-learning.html>

Após realizar todas as configurações indicadas passamos a ter um modelo pronto para a realização dos testes.

Assim no "Pontos de Extremidades" foi possível a configuração do algoritmo para realizar o teste de predição.

### Algoritimo utilizado:  
Esse algoritmo está disponível no depositório.
 ~~~
{
 "Inputs": {
    "data": [
      {
        "day": 0,
        "mnth": 0,
        "year": 0,
        "season": 0,
        "holiday": 0,
        "weekday": 0,
        "workingday": 0,
        "weathersit": 0,
        "temp": 0.0,
        "atemp": 0.0,
        "hum": 0.0,
        "windspeed": 0.0
      }
    ]
  },
  "GlobalParameters": 0.0
} 


 ~~~
### Teste e resultado

Para o teste foram passados os seguintes parâmetros:

~~~
{
   "Inputs": { 
     "data": [
       {
         "day": 1,
         "mnth": 1,   
         "year": 2022,
         "season": 2,
         "holiday": 0,
         "weekday": 1,
         "workingday": 1,
         "weathersit": 2, 
         "temp": 0.3, 
         "atemp": 0.3,
         "hum": 0.3,
         "windspeed": 0.3 
       }
     ]    
   },   
   "GlobalParameters": 1.0
 }
~~~

### Resultado do teste
~~~~
{1 item
"Results":[1 item
0:float 338.3857007891711
]
}
~~~~
O painel de teste pegou os dados de entrada e usou o modelo treinado para retornar o número previsto de **338 aluguéis**.

### Vamos revisar o que foi feito:
* Utilizamos dados históricos de aluguel de bicicletas para treinar um modelo. Dados esses disponíveis no link: <https://aka.ms/bike-rentals>
* O modelo prevê o número de aluguéis de bicicletas esperados num determinado dia, com base em características sazonais e meteorológicas.
* O modelo trouxe a previsão de **338 aluguéis**

### Aplicabilidade <h3>

Existem infinitas formas de aplicar um modelo como esse, mas em um exemplo concreto, esse caso poderia ser aplicada à uma loja de aluguel de bicicletas, que através do modelo poderia gerenciar melhor seu estoque tendo a previsão, por exemplo, dos períodos que precisaria ter mais bicicletas disponíveis e de períodos onde poderia deixar menos bicicletas para aluguel e fazer rotatividade de manutenção.

### Conhecimentos adquiridos com o laboratório:

* Acesso e configuração do Azure Machine Learning
* Criação de modelos predicionais simples
* Fundamentos de aprendizado de máquina
* Treinamento e avaliação de modelos

 # in English <h1> :earth_americas:
# Predictive Model with Azure ML<h1>

## Description of the entire process, from configuring Azure ML to testing the predictive model <h2>

### Goal: <h3>

In this exercise, the automated machine learning feature in Azure Machine Learning was used to train and evaluate a machine learning model, including all configuration, deployment, and testing steps of the trained model.

Automated machine learning allows experimentation with various algorithms and parameters to train different and numerous models and identify which is best for the data and desired return. In this exercise, we used a dataset of historical bike rental details to train a model that predicts the number of bike rentals expected on a given day, based on seasonal and weather characteristics.

### Creating an Azure Machine Learning workspace <h3>

To use Azure Machine Learning, you need to provision an Azure Machine Learning workspace in your Azure subscription. Then, you can use the Azure Machine Learning studio to work with the resources in your workspace.

For details on how to perform the settings, access the link and follow the instructions: <https://microsoftlearning.github.io/mslearn-ai-fundamentals/Instructions/Labs/01-machine-learning.html>

### Algorithm used:
This algorithm is available in the depository.

 ~~~
{
 "Inputs": {
    "data": [
      {
        "day": 0,
        "mnth": 0,
        "year": 0,
        "season": 0,
        "holiday": 0,
        "weekday": 0,
        "workingday": 0,
        "weathersit": 0,
        "temp": 0.0,
        "atemp": 0.0,
        "hum": 0.0,
        "windspeed": 0.0
      }
    ]
  },
  "GlobalParameters": 0.0
} 


 ~~~
### Test and result

The following parameters were passed for the test:

~~~
{
   "Inputs": { 
     "data": [
       {
         "day": 1,
         "mnth": 1,   
         "year": 2022,
         "season": 2,
         "holiday": 0,
         "weekday": 1,
         "workingday": 1,
         "weathersit": 2, 
         "temp": 0.3, 
         "atemp": 0.3,
         "hum": 0.3,
         "windspeed": 0.3 
       }
     ]    
   },   
   "GlobalParameters": 1.0
 }
~~~

### 
Test result
~~~~
{1 item
"Results":[1 item
0:float 338.3857007891711
]
}
~~~~
The test panel took the input data and used the trained model to return the predicted number of **338 rentals**.

### Let's review what was done: <h3>
* We use historical bike rental data to train a model. Data available at the link: <https://aka.ms/bike-rentals>
* The model predicts the number of bike rentals expected on a given day, based on seasonal and weather characteristics.
* The model provided a forecast of **338 rentals**

### Applicability <h3>

There are infinite ways to apply a model like this, but in a concrete example, this case could be applied to a bicycle rental store, which through the model could better manage its stock by predicting, for example, the periods it would need to have more bicycles available and periods where fewer bicycles could be left for rent and maintenance rotation.

### Knowledge acquired from the laboratory: <h3>

* Access and configure Azure Machine Learning
* Creation of simple predictive models
* Machine Learning Fundamentals
* Model training and evaluation
