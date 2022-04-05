Тестовое задание для стажёра в команду Core ML

На датасете MovieLens 20M https://www.kaggle.com/datasets/grouplens/movielens-20m-dataset сравните два подхода к построению рекомендаций:

• коллаборативный: используйте только рейтинги. Например SVD-like алгоритмы, ALS, Implicit-ALS.

• коллаборативный + контентный: используйте рейтинги и всю дополнительную информацию о фильмах, имеющуюся в датасете. Например LightFM.

Для выполнения задания:

1    Выберите метрику и обоснуйте этот выбор.

**Для обучения я выбрал метрику precision@10. Precision@10 используется когда необходимо рекомендовать n лучших "вариантов". Ещё при анализе я использовал recall, miss_rate, ndcg, map, coverage**

2    Придумайте и обоснуйте способ разбиения данных на обучение и валидацию.

**Столбцы входной таблицы отсортированы по временной метке. В качестве тренировочного набора взяты старые записи, а для тестового новые. Это имитирует работу рекомендационной модели**

3    Обратите внимание на сходимость обучения и настройку важных гиперпараметров моделей.

**В качестве средства настройки гиперпараметров я использовал библиотеку [optuna](https://optuna.org/)**

4    Выберите лучшую модель (При необходимости, оцените статистическую значимость результатов).

**Для всех выбранных метрик LightFM показал лучшие результаты чем SVD.**

5    Выложите на GitHub воспроизводимый код и краткий текстовый отчёт с выводами (можно в формате Jupyter Notebook).

**https://github.com/LiceyMaxim/VK_CoreML/blob/main/solve.ipynb**

Если возникают проблемы с загрузкой данных (wget), то их можно скачать вручную
https://drive.google.com/file/d/1j4UDdE0qWxEOsHhMyBPi8hSCZSRyN9GA/view?usp=sharing
https://drive.google.com/file/d/1JQWMelZa3ybAkI_mQibInwnr7HFCnWgM/view?usp=sharing

В поиске информации я нашёл статью, она послужила основой для решения. Поэтому я решил использовать холодный старт)
https://www.eigentheories.com/blog/lightfm-vs-hybridsvd/

