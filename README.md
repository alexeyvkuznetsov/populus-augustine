# *Populus* и лексика человеческих общностей в корпусе Аврелия Августина

Материалы к статье «*Populus* и лексика человеческих общностей в корпусе Аврелия Августина: дистрибутивно-семантический и сетевой анализ». [Выходные данные статьи и DOI будут добавлены после публикации.]

*Supplementary materials for a distributional-semantic and network analysis of* populus *and related terms for human communities in the works of Augustine of Hippo. The notebooks are in Russian.*

## Содержание

| Папка / файл | Что содержит |
| --- | --- |
| `notebooks/01_main_analysis.ipynb` | Основной анализ: распределение косинусного сходства, ближайшие соседи, выбор порога, основная сеть и её сообщества, локальные сети, сходство целевых лемм, значения, приводимые в статье |
| `notebooks/02_robustness.ipynb` | Проверки устойчивости: N = 10 / 15 / 20, 50 запусков алгоритма Лейдена, порог 0,48, сопоставление с UMAP и HDBSCAN |
| `html/` | Те же ноутбуки со всеми результатами в формате HTML (открываются в браузере без Python) |
| `figures/` | Изображения, которые создают ноутбуки: основная сеть, распределение сходства, выбор порога, тепловая карта, UMAP/HDBSCAN, отдельные сообщества (`communities/`) и локальные сети всех 18 целевых лемм (`local_networks/`) |
| `appendix/` | Приложение к статье (PDF) |
| `requirements.txt` | Версии библиотек, с которыми ноутбуки проверены |

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

Основной ноутбук выполняется примерно за минуту, ноутбук проверок устойчивости – за несколько минут. Размеры шрифта подписей на рисунках задаются в ячейке параметров каждого ноутбука.

## Модель

Используется модель Word2Vec (CBOW, векторы размерности 50), обученная Э. Врангбек и коллегами на корпусе сочинений Августина Corpus Augustinianum Gissense и опубликованная в репозитории <https://github.com/eehvrangbaek/aug_will_love>. Модель **не входит** в этот репозиторий: ноутбуки загружают её из репозитория разработчиков и проверяют контрольную сумму.

```
SHA-256  a3a336148d8dbfa53778c3ea911aa285797b7e3902acba35edde98bedf6ea105  word2vec.model
```

При использовании модели ссылайтесь на работы её разработчиков:

- Vrangbæk E. E. H., Nielbo K. L. Love Between Desire and Will: An Investigation of Augustine's Concept of Love Assisted by Computational Methods // Augustine and Ethics / ed. S. Hannan, K. Paffenroth. Lanham: Lexington Books, 2023. P. 130–149.
- Vrangbæk E., Vrangbæk C. Modelling the Semantic Landscape of Angels in Augustine of Hippo // Open Theology. 2025. Vol. 11, no. 1. Art. 20250050.

## Воспроизводимость

Все случайные процедуры используют фиксированные начальные значения. Результаты основного анализа полностью воспроизводимы. Результат UMAP зависит также от версии библиотек и платформы, поэтому число кластеров HDBSCAN на отдельной проекции при повторном запуске может немного отличаться. Раскладка узлов на рисунках сетей зависит от версии `networkx`.

В ноутбуках и на рисунках леммы приводятся в орфографии словаря модели (*ciuitas, uulgus*), в тексте статьи – в традиционной (*civitas, vulgus*).

## Как цитировать

[Библиографическое описание статьи и DOI архивной версии репозитория будут добавлены после публикации.]


