# Desafio de Projeto DIO: Transfer Learning com Cats vs. Dogs

## 📒 Descrição
Este projeto é a implementação do desafio "Entendendo o Mecanismo de Transfer Learning na Prática" da DIO. O objetivo foi aplicar a técnica de Transfer Learning para construir um classificador de imagens capaz de diferenciar gatos e cachorros.

## 🤖 Modelo Utilizado
Para este projeto, utilizei a arquitetura **MobileNetV2** pré-treinada no dataset ImageNet. As camadas convolucionais da rede foram congeladas, e apenas uma nova camada de classificação foi adicionada e treinada com o dataset "Cats vs. Dogs".

## ⚙️ Tecnologias Utilizadas
- **Linguagem:** Python
- **Framework de Deep Learning:** TensorFlow / Keras
- **Ambiente de Execução:** Google Colab
- **Bibliotecas Principais:** `tensorflow`, `os`

## 🚀 Processo
1.  **Preparação do Ambiente:** O Google Colab foi configurado para utilizar aceleração via GPU.
2.  **Carregamento dos Dados:** O dataset "Cats and Dogs" foi baixado e descompactado diretamente no ambiente.
3.  **Pré-processamento:** As imagens foram redimensionadas para `160x160` pixels e foi aplicado *Data Augmentation* no conjunto de treino para melhorar a generalização do modelo.
4.  **Construção do Modelo:**
    - A base `MobileNetV2` foi carregada sem suas camadas de topo (`include_top=False`).
    - Suas camadas foram congeladas (`base_model.trainable = False`).
    - Uma camada `GlobalAveragePooling2D` e uma camada `Dense` final com ativação `sigmoid` foram adicionadas.
5.  **Treinamento:** O modelo foi compilado com o otimizador Adam e a função de perda `binary_crossentropy`, e treinado por 10 épocas.

## 📊 Resultados
O modelo atingiu uma acurácia de validação de aproximadamente 91.08% após 10 épocas. Isso demonstra a eficácia do Transfer Learning, que permite alcançar ótimos resultados com um esforço computacional relativamente baixo.

## 🔗 Link para o Notebook
Você pode visualizar todo o código e a execução no notebook principal do projeto:
- [Desafio_TransferLearning_CatsVsDogs.ipynb](https://colab.research.google.com/drive/1pAmirzE45H0xN6W5kEJHlkP9Sp8bfFgA?usp=sharing)
