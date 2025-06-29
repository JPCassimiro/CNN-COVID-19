- [CNN para classificaçao de imagens médicas de diagnosticos de Covid-19](#cnn-para-classificaçao-de-imagens-médicas-de-diagnosticos-de-covid-19)
- [Autor](#autor)
- [Descritor](#descritor)
- [Repositório](#repositório)
- [Classificador e acurácia](#classificador-e-acurácia)


# CNN para classificaçao de imagens médicas de diagnosticos de Covid-19

Este trabalho feito para a matéria de processamento de imagens da UTPFR-CP no primero semestre de 2025 no curso de engenharia de computação.

# Autor

João Pedro Silva Cassimiro
2142600
[https://github.com/JPCassimiro][https://github.com/JPCassimiro]

# Descritor

Métodologia: Transfer-learning
Modelo base: Xception
Camadas adicionadas de descrição: BatchNormalization, GlobalAveragePooling2D

Dataset: COVID-19 & Normal Posteroanterior(PA) X-rays
Classes: 2
Total de imagens: 280
Sobre: raio-x com duas categorias diferentes, covid ou normal
link: [https://www.kaggle.com/datasets/tarandeep97/covid19-normal-posteroanteriorpa-xrays][https://www.kaggle.com/datasets/tarandeep97/covid19-normal-posteroanteriorpa-xrays]

# Repositório


# Classificador e acurácia

Estrutura de camadas de classificação:

    x = tf.keras.layers.Dropout(0.5)(x)
    x = tf.keras.layers.Dense(64,kernel_regularizer=tf.keras.regularizers.L2(0.01), activation='relu')(x)
    x = tf.keras.layers.Dropout(0.5)(x)
    output_layer = tf.keras.layers.Dense(1, activation='sigmoid')(x)

Otimizador: Adam (0.0001)
Função de perda: Binary Crossentropy
Métrica: Accuracy