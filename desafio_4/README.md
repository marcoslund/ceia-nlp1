# Desafío 4

[![Abrir en Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/marcoslund/ceia-nlp1/blob/main/desafio_4/Desafio_4.ipynb)

[`Desafio_4.ipynb`](Desafio_4.ipynb)

Traductor seq2seq inglés-español con LSTM, replicando y extendiendo el notebook
de clase ([`Traductor.ipynb`](Traductor.ipynb)): se amplía el dataset de 10k a
40k oraciones de Tatoeba (sin truncar secuencias), se barre el número de
unidades LSTM (128/256/512) y se analizan las traducciones del mejor modelo.
Como actividades opcionales se prueban embeddings preentrenados en ambos
idiomas (GloVe y fastText, congelados y entrenables) y estrategias de
generación alternativas a greedy: muestreo con temperatura y beam search.

Todos los datos se descargan solos (el dataset spa-eng, el pickle de GloVe y
los vectores de fastText, estos últimos en forma parcial por streaming). El
entrenamiento requiere GPU — en Colab, **Entorno de ejecución → Cambiar tipo
de entorno → T4 GPU** — y la corrida completa (seis modelos) lleva alrededor
de tres horas. El notebook monta Google Drive y guarda un checkpoint por
modelo en `MyDrive/ceia-nlp1/desafio_4`, así que si la sesión se corta, al
re-correr solo se entrena lo que falta; con todos los checkpoints presentes,
el notebook entero se re-ejecuta en minutos.
