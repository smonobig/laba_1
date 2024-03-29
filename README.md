# Исследование и разработка системы для автоматической идентификации предпочтений пользователей в электронной коммерции(Лабораторная№1).

## О проекте.
Этот проект направлен на анализ больших данных из каких-либо сетевых магазинов и т.п. заведений. Направлен на создание системы, способной автоматически выявлять и анализировать предпочтения пользователей при осуществлении покупок в онлайн-магазинах. В данном проекте использовались стандартные python-библиотеки такие как : numpy, pandas, matplotlib, catboost.

## Matplotlib
Matplotlib - это библиотека для создания статических, интерактивных и анимационных графиков в языке программирования Python. Эта библиотека предоставляет широкие возможности для визуализации данных и широко используется в области научных исследований, анализа данных, инженерии, машинного обучения и других областях.

Некоторые основные особенности Matplotlib:
* *Разнообразные типы графиков.* Matplotlib поддерживает создание различных видов графиков, таких как линейные графики, столбчатые диаграммы, точечные диаграммы, гистограммы, круговые диаграммы, трехмерные графики и многие другие.
* *Высокая гибкость настройки.* Библиотека предоставляет обширные возможности для настройки внешнего вида графиков, включая цвета, стили линий, маркеры, размеры шрифтов, подписи и легенды.
* *Интеграция с NumPy и pandas.* Matplotlib легко интегрируется с другими библиотеками Python, такими как NumPy для работы с массивами данных и pandas для анализа данных.
* *Поддержка различных форматов вывода.* Графики, созданные с использованием Matplotlib, могут быть сохранены в различных форматах, таких как PNG, JPEG, PDF и другие.
* *Интерактивные возможности.* Начиная с определенных версий, Matplotlib также поддерживает интерактивные графики с использованием бэкенда, такого как Qt или Tkinter.

## Catboost
CatBoost (Categorical Boosting) - это открытая библиотека машинного обучения, предназначенная для задач классификации, регрессии и ранжирования. Она была разработана компанией Yandex и предоставляет высокопроизводительные алгоритмы градиентного бустинга, специально оптимизированные для работы с категориальными признаками.

Основные характеристики :
* *Обработка категориальных признаков.* CatBoost автоматически обрабатывает категориальные признаки без необходимости предварительного кодирования. Это упрощает процесс подготовки данных и позволяет более эффективно использовать информацию из категориальных переменных.
* *Работа с пропущенными данными.* Алгоритм может обрабатывать пропущенные значения в данных без дополнительной предварительной обработки.
* *Эффективная обработка больших датасетов.* CatBoost оптимизирован для работы с большими объемами данных, что делает его подходящим для применения в широком диапазоне задач, включая те, где объем данных значителен.
* *Встроенная поддержка для ранжирования.* CatBoost предоставляет функциональность для решения задач ранжирования, что полезно, например, в поисковых движках или рекомендательных системах.
* *Высокая производительность.* Алгоритм реализован с использованием эффективных оптимизаций, что обеспечивает высокую производительность в сравнении с другими библиотеками градиентного бустинга.
  
CatBoost стал популярным инструментом в сообществе машинного обучения благодаря своей эффективности, удобству использования и встроенной поддержке категориальных признаков.

## Как работает программа.

1. **Установка необходимых библиотек и подключение csv-файла**
2. **Выполняется предобработка данных: обработка пропущенных значений, преобразование даты, удаление отмененных транзакций и другие операции.**
3. **Анализируется статистика данных, строятся графики и диаграммы для визуализации распределения различных параметров (например, кодов товаров, описаний, цен).**
4. **Создаются новые признаки на основе анализа даты (год, квартал, месяц, день недели и др.), а также проводится кластеризация товаров и добавление статистических характеристик.**
5. **Подготавливается и обучается модель машинного обучения (CatBoostRegressor) для прогнозирования количества продаж.**
6. **Проводится анализ результатов обучения, включая оценку важности признаков, визуализацию ошибок и др.**
7. **В коде также присутствует неиспользуемый блок, связанный с гиперпараметрическим поиском (Hypertuner), который можно использовать для оптимизации параметров модели.**
8. **Некоторые операции в коде, такие как boxcox-преобразования и работа с кластерами товаров, направлены на улучшение статистических характеристик данных.**

## Требования.
* Python 3
* Google Colab или Jupyter Notebook
* Стабильное подключение к интернету

## Зависимости.
* Catboost
* Matplotlib
* Seaborn
* Shap
* Numpy
* Pandas



## Результаты.

![бокскокс](https://github.com/smonobig/laba_1/assets/86806629/d37fd1cc-c617-4b48-89b8-7b84dd347b0b)

На данном скриншоте представлена Box-Cox преобразование с параметром медианы.  Box-Cox преобразование - это статистическая техника, используемая для стабилизации дисперсии и нормализации распределения.


![медиана](https://github.com/smonobig/laba_1/assets/86806629/fa341a92-803b-440d-9d5c-28376af701a5)

На данном скриншоте представленна одиночная абсолютная ошибка - метрика оценки точности модели, используемая для измерения расхождения между фактическими и предсказанными значениями для отдельных наблюдений. Она определяется как абсолютное значение разницы между фактическим и предсказанным значениями для одного конкретного элемента данных. Эта метрика позволяет оценить точность модели на уровне отдельных наблюдений. Одиночные абсолютные ошибки могут быть использованы для вычисления различных статистик оценки качества модели, таких как средняя абсолютная ошибка (MAE) или медианная абсолютная ошибка (MedAE). В общем случае, чем меньше значения одиночных абсолютных ошибок, тем лучше модель справляется с предсказанием фактических значений.


![шап](https://github.com/smonobig/laba_1/assets/86806629/7085a904-8730-4bc9-8645-846c928ac8cb)
SHAP (SHapley Additive exPlanations) - это метод интерпретации моделей машинного обучения, который позволяет объяснить предсказания модели, определяя влияние каждого признака на конкретное предсказание. SHAP values основаны на теории кооперативных игр и используют концепцию численных вкладов Шепли (Shapley values) для распределения важности между признаками.

SHAP Values предоставляют график вклада каждого признака в предсказание модели для конкретного наблюдения. Этот график называется "Summary Plot" или "SHAP Summary Plot". В этом графике каждая точка представляет отдельный набор данных (например, одно наблюдение) и отражает вклад каждого признака в конкретное предсказание.

Основные компоненты SHAP Summary Plot:

**Горизонтальная линия: Это "Base Value" - базовое значение, которое представляет средний прогноз модели на обучающем наборе данных.**

**Вертикальные полосы: Каждая вертикальная полоса представляет вклад каждого признака в предсказание для конкретного наблюдения. Цвет полосы указывает на значение признака: красный для высоких значений, синий для низких значений.**

**Горизонтальные отрезки (бары): Длина каждого бара представляет абсолютное значение вклада признака в предсказание. Бары расположены слева или справа от базовой линии в зависимости от того, увеличивают ли они или уменьшают предсказанное значение.**


SHAP Values позволяют понять, какие факторы (признаки) оказывают наибольшее влияние на предсказания модели для конкретного наблюдения, что делает их полезными для объяснения работы моделей машинного обучения.




## Colab

| Colab                                                                                                                                                                          | Info               |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------ |
|[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/smonobig/laba_1/blob/main/lab_1.ipynb) |lab1|


