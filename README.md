# Classificação de Pixels em Imagens de Satélite

Este notebook Jupyter demonstra um processo de classificação de pixels em imagens de satélite usando técnicas de aprendizado de máquina. O objetivo principal é categorizar diferentes tipos de cobertura do solo (por exemplo, água, vegetação, áreas urbanas) com base nos valores espectrais dos pixels.

## Conteúdo do Notebook

O notebook `Pixel_Classification_of_satellite_images.ipynb` abrange as seguintes etapas:

1.  **Instalação e Importação de Bibliotecas**: Configuração do ambiente com as bibliotecas necessárias para manipulação de dados geoespaciais e aprendizado de máquina (ex: `rasterio`, `numpy`, `sklearn`).
2.  **Carregamento e Pré-processamento de Dados**: Leitura de imagens de satélite (geralmente em formato GeoTIFF) e preparação dos dados para classificação. Isso pode incluir a reorganização de bandas e a criação de um conjunto de dados adequado para o modelo.
3.  **Definição de Regiões de Interesse (ROIs)**: Identificação e extração de amostras de pixels que representam diferentes classes de cobertura do solo. Essas ROIs são usadas para treinar o modelo de classificação.
4.  **Treinamento do Modelo de Classificação**: Aplicação de algoritmos de aprendizado de máquina (como Random Forest ou Support Vector Machine) para treinar um classificador usando as amostras de ROIs.
5.  **Classificação da Imagem Completa**: Utilização do modelo treinado para classificar todos os pixels da imagem de satélite, gerando um mapa de cobertura do solo.
6.  **Visualização e Avaliação**: Apresentação dos resultados da classificação e, potencialmente, métricas de avaliação da acurácia do modelo.

## Bibliotecas Utilizadas

* `rasterio`: Para leitura e escrita de dados geoespaciais raster.
* `numpy`: Para operações numéricas e manipulação de arrays.
* `scikit-learn (sklearn)`: Para algoritmos de aprendizado de máquina (classificadores como `RandomForestClassifier` ou `SVC`).
* `matplotlib` e `seaborn`: Para visualização de dados.
* Outras bibliotecas auxiliares para manipulação de dados e operações específicas.

## Como o MLPClassifier Funciona
O MLPClassifier do scikit-learn é uma implementação de uma Rede Neural Perceptron Multicamadas (MLP), um modelo de aprendizado de máquina poderoso e versátil, inspirado no funcionamento do cérebro humano, que é usado para tarefas de classificação.

Em essência, um MLP é composto por camadas de "neurônios" (ou nós) interconectados, que processam as informações.

## Estrutura e Processamento de Dados:
- Camada de Entrada (Input Layer): Recebe os dados brutos. Cada neurônio de entrada corresponde a uma característica (feature) dos seus dados. Por exemplo, em classificação de pixels, cada neurônio pode representar um canal espectral (vermelho, verde, azul, infravermelho, etc.).
- Camadas Ocultas (Hidden Layers): São as camadas intermediárias onde a maior parte do processamento acontece. Os neurônios nessas camadas transformam as entradas de forma não-linear, permitindo que o modelo aprenda padrões complexos e extraia características mais abstratas. Um MLP pode ter uma ou múltiplas camadas ocultas.
- Camada de Saída (Output Layer): Produz a previsão final do modelo. Para problemas de classificação, o número de neurônios de saída geralmente corresponde ao número de classes que o modelo deve prever.


## O Funcionamento Interno (De maneira simplificada):
Soma Ponderada e Ativação: Cada neurônio recebe entradas dos neurônios da camada anterior, multiplica essas entradas por "pesos" (que representam a importância de cada conexão), soma-os e adiciona um "viés". O resultado é então passado por uma função de ativação (como ReLU, Sigmoid ou Tanh), que introduz a não-linearidade crucial para o aprendizado de padrões complexos.


![image](https://github.com/user-attachments/assets/ba9b3157-881e-455e-b8e8-eacbfe4e8bff)



Propagação (Forward Propagation): Quando os dados de entrada são fornecidos, eles "fluem" através da rede, da camada de entrada para as camadas ocultas e, finalmente, para a camada de saída, gerando uma previsão.

Aprendizado (Backpropagation): O processo de aprendizado ocorre durante o treinamento através de um algoritmo chamado retropropagação (backpropagation):

![image](https://github.com/user-attachments/assets/d45caa55-6aa6-4510-98ff-083cb86289b7)

O erro entre a previsão do modelo e o rótulo real é calculado.
Esse erro é então propagado para trás através da rede.
Com base nesse erro, os pesos e vieses de cada conexão e neurônio são ajustados iterativamente (usando um otimizador como Adam ou SGD) para minimizar o erro nas próximas previsões. Este processo é repetido por muitas "épocas" (passagens pelos dados de treinamento) até que o modelo aprenda a mapear as entradas para as classes de saída com alta acurácia.
Aplicação na Classificação de Pixels:
No contexto da classificação de pixels em imagens de satélite, o MLPClassifier é treinado para reconhecer padrões nos valores espectrais de cada pixel. Ao fornecer ao modelo pixels rotulados (por exemplo, "água", "vegetação", "urbano"), ele aprende a identificar essas categorias com base nas características espectrais. Uma vez treinado, o modelo pode classificar pixels desconhecidos em toda a imagem, gerando um mapa de cobertura do solo.
