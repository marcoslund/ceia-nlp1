# Desafío 3

[![Abrir en Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/marcoslund/ceia-nlp1/blob/main/desafio_3/Desafio_3.ipynb)

[`Desafio_3.ipynb`](Desafio_3.ipynb)

Modelo de lenguaje con tokenización por caracteres sobre *A Game of Thrones*, el
primer libro de *A Song of Ice and Fire*. Se comparan arquitecturas basadas en
`SimpleRNN`, `LSTM` y `GRU`, y se generan secuencias con greedy search y beam
search determinista y estocástico.

El corpus es el mismo del desafío 2 ([`desafio_2/archive/`](../desafio_2/archive));
el notebook lo usa desde ahí si está disponible y, si no, lo descarga de este
repositorio. El entrenamiento requiere GPU: en Colab, **Entorno de ejecución →
Cambiar tipo de entorno → T4 GPU**.
