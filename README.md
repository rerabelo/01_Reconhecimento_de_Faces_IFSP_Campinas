# Reconhecimento de Faces - IFSP - Campinas
Renata Rabelo & Mariana Cabride

O código depositado nesse repositório realiza várias etapas relacionadas ao treinamento e teste de redes neurais para reconhecimento facial utilizando o dataset PubFig83 disponibilizado no desafio do Kaggle elaborado para a disciplina de Aplicações em Ciência de Dados (D3APL 2023) do curso Especialização em Ciência de Dados do IFSP Campinas.


**Descrição das redes neurais adotadas:**
No código depositado são utilizadas duas arquiteturas de redes neurais: uma rede convolucional personalizada e a arquitetura VGG16 pré-treinada.
A primeira arquitetura foi construída utilizando a API Sequential do TensorFlow. Essa rede possui camadas convolucionais responsáveis por extrair características relevantes das imagens, seguidas por camadas de pooling para reduzir a dimensionalidade dos dados. Em seguida, as camadas são achatadas e conectadas a camadas totalmente conectadas, também conhecidas como MLP (Multilayer Perceptron), que são responsáveis por realizar a classificação das imagens em classes específicas. A função de ativação utilizada nas camadas convolucionais e nas camadas totalmente conectadas é a ReLU (Rectified Linear Unit).
A segunda arquitetura é a VGG16, uma arquitetura de rede neural convolucional pré-treinada que já obteve bons resultados em tarefas de classificação de imagens. Essa arquitetura é carregada a partir do TensorFlow utilizando a classe VGG16 da biblioteca Keras. A VGG16 possui uma configuração específica de camadas convolucionais, seguida por camadas totalmente conectadas para a classificação. Nesse código, as camadas convolucionais da VGG16 são mantidas congeladas, ou seja, seus pesos não são atualizados durante o treinamento, enquanto novas camadas são adicionadas no topo da rede para adaptá-la à tarefa de reconhecimento facial.

**Pré-processamento:**
A etapa de pré-processamento envolve a leitura das imagens do conjunto de dados e a aplicação de transformações para deixá-las em um formato adequado para o treinamento da rede neural. Isso inclui redimensionar as imagens para as dimensões desejadas, converter a representação de cores de BGR para RGB e normalizar os valores dos pixels.

**Treinamento:**
A etapa de treinamento é realizada usando o conjunto de dados de treinamento pré-processado. A função fit() do modelo é utilizada para treinar a rede neural. São especificados o número de épocas, tamanho do lote, conjunto de dados de validação e outros parâmetros relevantes.

**Otimizadores adotados:**
No código fornecido, são utilizados dois otimizadores diferentes: o otimizador SGD (Stochastic Gradient Descent) e o otimizador Adam. Esses otimizadores são responsáveis por ajustar os pesos da rede neural durante o treinamento, visando minimizar a função de perda e melhorar o desempenho do modelo.

**Fine-tuning:**
No código, é realizado o fine-tuning da arquitetura VGG16 pré-treinada. As camadas convolucionais da VGG16 são congeladas para evitar que seus pesos sejam atualizados durante o treinamento. Em seguida, camadas adicionais de classificação são adicionadas no topo da rede e treinadas com os dados específicos do problema em questão.

**Validação e discussão dos resultados:**
O modelo treinado é avaliado utilizando o conjunto de dados de validação. A função evaluate() é utilizada para obter métricas de desempenho, como a acurácia. Além disso, é possível analisar as curvas de aprendizado para entender o desempenho do modelo ao longo do tempo. Também são gerados arquivos CSV contendo as predições para o conjunto de teste. Esse .csv foi submetido como resposta ao desafio do Kaggle e recebeu um score de 
0.34. De fato, o resultado não foi satisfatório, e indica que o modelo não está conseguindo classificar corretamente a maioria das imagens de teste disponibilizadas no desafio. Uma possível abordagem para aumentar a acurácia do modelo em questão seria realizar algumas modificações e experimentações, levando em consideração a exploração dos hiperparâmetros e de outras arquiteturas de redes neurais convolucionais.





