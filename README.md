# *Populus* и лексика человеческих общностей в корпусе Аврелия Августина

Материалы к статье «*Populus* и лексика человеческих общностей в корпусе Аврелия Августина: дистрибутивно-семантический и сетевой анализ». [Выходные данные статьи и DOI будут добавлены после публикации.]

*Supplementary materials for a distributional-semantic and network analysis of* populus *and related terms for human communities in the works of Augustine of Hippo. The notebooks are in Russian.*

## Содержание

| Папка / файл | Что содержит |
| --- | --- |
| `notebooks/01_main_analysis.ipynb` | Основной анализ: фоновое распределение сходства, ближайшие соседи, выбор порога, основная сеть и её сообщества, локальные сети 6–4, тепловая карта, проверка чисел, приводимых в статье |
| `notebooks/02_robustness.ipynb` | Проверки устойчивости: N = 10 / 15 / 20, 50 запусков алгоритма Лейдена, порог 0,48, UMAP и HDBSCAN (одна проекция и 120 проекций) |
| `html/` | Те же ноутбуки со всеми результатами в формате HTML: открываются в любом браузере без Python |
| `figures/` | Рисунки, которые создают ноутбуки: рис. 1–4 и П1–П2 статьи, отдельные сообщества (`communities/`), локальные сети всех 18 целевых лемм (`local_networks/`), матрица сходства целевых лемм |
| `appendix/` | Приложение к статье (табл. П1, П2; рис. П1, П2) |
| `requirements.txt` | Версии библиотек, с которыми ноутбуки проверены |

Соответствие рисунков статье:

| Файл | В статье |
| --- | --- |
| `Fig1_main_network.png` | Рис. 1. Сеть дистрибутивного сходства |
| `Fig2_local_network_populus.png` | Рис. 2. Локальная сеть *populus* |
| `Fig3_local_network_plebs.png` | Рис. 3. Локальная сеть *plebs* |
| `Fig4_umap_leiden_hdbscan.png` | Рис. 4. Сообщества Лейдена и кластеры HDBSCAN |
| `FigA1_cosine_distribution.png` | Рис. П1. Распределение косинусного сходства |
| `FigA2_threshold_selection.png` | Рис. П2. Выбор порога |

## Как запустить

**В Google Colab.** Откройте ноутбук по ссылке и выполните все ячейки («Среда выполнения → Выполнить все»):

- [01_main_analysis.ipynb](https://colab.research.google.com/github/USER/REPO/blob/main/notebooks/01_main_analysis.ipynb)
- [02_robustness.ipynb](https://colab.research.google.com/github/USER/REPO/blob/main/notebooks/02_robustness.ipynb)

Если после установки библиотек Colab попросит перезапустить среду, перезапустите её и снова выполните все ячейки.

**Локально.**

```bash
pip install -r requirements.txt
jupyter notebook notebooks/
```

Основной ноутбук выполняется примерно за минуту, ноутбук проверок устойчивости — за несколько минут.

## Модель

Используется модель Word2Vec (CBOW, векторы размерности 50), обученная Э. Врангбек и коллегами на корпусе сочинений Августина Corpus Augustinianum Gissense и опубликованная в репозитории <https://github.com/eehvrangbaek/aug_will_love>. Модель **не входит** в этот репозиторий: ноутбуки загружают её из репозитория разработчиков и проверяют контрольную сумму, чтобы гарантировать использование той же версии.

```
SHA-256  a3a336148d8dbfa53778c3ea911aa285797b7e3902acba35edde98bedf6ea105  word2vec.model
```

При использовании модели ссылайтесь на работы её разработчиков:

- Vrangbæk E. E. H., Nielbo K. L. Love Between Desire and Will: An Investigation of Augustine's Concept of Love Assisted by Computational Methods // *Augustine and Ethics* / ed. S. Hannan, K. Paffenroth. Lanham: Lexington Books, 2023. P. 130–149.
- Vrangbæk E., Vrangbæk C. Modelling the Semantic Landscape of Angels in Augustine of Hippo // *Open Theology*. 2025. Vol. 11, no. 1. Art. 20250050.

## Воспроизводимость

Все случайные процедуры используют фиксированные начальные значения. Результаты основного анализа (порог, сеть, сообщества, соседи, локальные сети) полностью воспроизводимы. Результат UMAP зависит также от версии библиотек и платформы, поэтому число кластеров HDBSCAN на рис. 4 при повторном запуске может отличаться на несколько единиц; выводы статьи опираются на многократную проверку по 120 проекциям, которая от этого не зависит. Раскладка узлов на рисунках сетей зависит от версии `networkx`.

Об орфографии: в ноутбуках и на рисунках леммы приводятся в орфографии словаря модели (*ciuitas, uulgus*); в тексте статьи — в традиционной (*civitas, vulgus*).

## Как цитировать

[Библиографическое описание статьи и DOI архивной версии репозитория будут добавлены после публикации.]

## Лицензия

Код — MIT; рисунки и приложение — CC BY 4.0. [Уточнить перед публикацией.]
