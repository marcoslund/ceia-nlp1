# Repositorio público de Procesamiento de Lenguaje Natural I

Fecha: 2026-07-31

## Objetivo

Transformar el directorio de trabajo local (`notebooks/`, con un único
`Desafio_1.ipynb` resuelto y sin control de versiones) en un repositorio de
GitHub público donde se publiquen los 4 desafíos de la materia Procesamiento de
Lenguaje Natural I (CEIA - FIUBA).

El repositorio es un contenedor de notebooks de cursada. No es una librería ni
una aplicación: no tiene código importable, tests ni CI.

## Decisiones

| Decisión | Elección | Razón |
|----------|----------|-------|
| Organización | Una carpeta por desafío | Deja lugar para datasets, imágenes o modelos propios de cada desafío sin ensuciar la raíz. Mismo patrón que `ceia-vpc1-tps`. |
| Nombre del repo | `marcoslund/ceia-nlp1`, público | Continúa la convención de `ceia-vpc1-tps`. |
| Carpeta local | Renombrada a `ceia-nlp1/` | Que la ruta local coincida con el repo remoto. |
| Autoría | Individual (Marcos Lund, a2408) | Los desafíos de la materia son individuales. |
| Desafíos 2-4 | Carpeta + README con "Pendiente" | La estructura queda reservada sin afirmar temas que todavía no fueron asignados. |
| Entorno | uv local + badges de Colab | Los desafíos 3 y 4 suelen requerir GPU. Se soportan ambos caminos. |
| Salidas de notebooks | Se publican ejecutadas | Los resultados quedan visibles en GitHub sin ejecutar nada, para la corrección de la materia. |
| Dependencias | Incrementales | `numpy` y `scikit-learn` hoy; el resto se agrega cuando cada desafío lo requiera. Bajar TensorFlow hoy no aporta nada. |

## Estructura

```
ceia-nlp1/
├── README.md              Materia, autor, tabla de desafíos, setup, dependencias
├── pyproject.toml         name = "ceia-nlp1"
├── uv.lock
├── .python-version        3.12
├── .gitignore
├── docs/superpowers/specs/
│   └── 2026-07-31-repo-publico-nlp1-design.md
├── desafio_1/
│   ├── README.md          Badge de Colab + link al notebook
│   └── Desafio_1.ipynb
├── desafio_2/README.md    Pendiente
├── desafio_3/README.md    Pendiente
└── desafio_4/README.md    Pendiente
```

## Contenido de los README

Los README no duplican el contenido ni los resultados de los notebooks. La
consigna, los experimentos y las conclusiones viven dentro de cada notebook;
repetirlos afuera crearía dos versiones que se desincronizan.

- **Raíz**: nombre y descripción de la materia, autor, tabla de los 4 desafíos
  (número, notebook, badge de Colab, estado), instrucciones de setup local con
  uv, nota sobre la ejecución en Colab y tabla de dependencias.
- **Por desafío**: título, badge de Colab y link al notebook. Nada más.
- **Desafíos pendientes**: título y la palabra "Pendiente".

## Convenciones para los notebooks

- Se publican con sus salidas ejecutadas.
- Cada notebook conserva una celda inicial de `%pip install` con sus
  dependencias, comentada como necesaria en Colab e innecesaria en local. Es lo
  que permite abrirlos en Colab sin editarlos.
- El `kernelspec.display_name` es `Python 3`, no el nombre del entorno local.
- Las salidas no deben contener rutas absolutas de la máquina local.

## Publicación

1. `git init` y commit inicial sobre la rama `main`.
2. `gh repo create marcoslund/ceia-nlp1 --public --source=. --push`.

El push requiere confirmación explícita: a partir de ese momento el contenido
queda público e indexable.

## Fuera de alcance

- GitHub Actions, tests o linters: overhead sin retorno para un repositorio de
  notebooks de cursada.
- Un paquete `src/` con utilidades compartidas: no hay todavía código repetido
  entre desafíos que lo justifique.
- Resolver los desafíos 2, 3 y 4.
