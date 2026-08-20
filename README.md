# ceia-nlp1

Desafíos de Procesamiento de Lenguaje Natural I (CEIA - FIUBA).

## Autor

- Marcos Lund (a2408)

## Desafíos

| # | Notebook | Colab | Estado |
|---|----------|-------|--------|
| 1 | [`Desafio_1.ipynb`](desafio_1/Desafio_1.ipynb) | [![Abrir en Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/marcoslund/ceia-nlp1/blob/main/desafio_1/Desafio_1.ipynb) | Finalizado |
| 2 | [`Desafio_2.ipynb`](desafio_2/Desafio_2.ipynb) | [![Abrir en Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/marcoslund/ceia-nlp1/blob/main/desafio_2/Desafio_2.ipynb) | Finalizado |
| 3 | [`Desafio_3.ipynb`](desafio_3/Desafio_3.ipynb) | [![Abrir en Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/marcoslund/ceia-nlp1/blob/main/desafio_3/Desafio_3.ipynb) | Finalizado |
| 4 | [`Desafio_4.ipynb`](desafio_4/Desafio_4.ipynb) | [![Abrir en Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/marcoslund/ceia-nlp1/blob/main/desafio_4/Desafio_4.ipynb) | Finalizado |

## Setup local

Con [uv](https://docs.astral.sh/uv/getting-started/installation/#standalone-installer) instalado:

```bash
uv sync
```

Para abrir Jupyter Lab:

```bash
uv run jupyter lab
```

## Ejecución en Colab

Cada desafío tiene un badge que abre su notebook directamente en Colab. Los
notebooks incluyen una celda inicial de `%pip install` cuando necesitan
dependencias que Colab no trae (el desafío 4 usa solo paquetes preinstalados),
así que se ejecutan sin configuración previa.

El desafío 2 usa un corpus propio (`desafio_2/archive/`, los cinco libros de
*A Song of Ice and Fire*). El notebook usa los archivos locales si existen y,
si no, los descarga de este mismo repositorio, de modo que también corre en
Colab sin pasos adicionales. El desafío 3 reutiliza ese mismo corpus con el
mismo mecanismo.

El desafío 3 entrena redes recurrentes, así que necesita GPU: en Colab,
**Entorno de ejecución > Cambiar tipo de entorno > T4 GPU**. La corrida completa
lleva alrededor de una hora y media.

El desafío 4 también necesita GPU y su corrida completa entrena seis modelos
seq2seq, unas tres horas en una T4. Todos sus datos (el dataset spa-eng de
Tatoeba, los embeddings de GloVe y fastText) se descargan solos. El notebook
monta Google Drive —pide permiso al correrlo— y guarda un checkpoint por
modelo en `MyDrive/ceia-nlp1/desafio_4`: si la sesión se corta, al re-correr
solo se entrena lo que falta, y con todos los checkpoints presentes el
notebook entero se re-ejecuta en minutos.

## Dependencias

| Import | Paquete |
|--------|---------|
| `numpy` | `numpy` |
| `sklearn` | `scikit-learn` |
| `gensim` | `gensim` |
| `matplotlib` | `matplotlib` |
| `plotly` | `plotly` (necesita `nbformat` para renderizar en notebooks) |
| `tensorflow`, `keras` | `tensorflow` |
| `pandas` | `pandas` |
| `seaborn` | `seaborn` |
| `gradio` | `gradio` |

Las dependencias se agregan a medida que cada desafío las requiere.
