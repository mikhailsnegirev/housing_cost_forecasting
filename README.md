# Прогнозирование стоимости жилья в жилом массиве 
## Описание проекта и цель  <br>
Сервис по продаже квартир закала разработку модели по прогнозированию стоимости квартиры. Необходимо определить медианную стоимость квартиры.



## Инструменты
`предобработка данных`
`Python`
`Pandas`
`Matplotlib`
`numpy`
`исследовательский анализ данных`
`визуализация данных`
`Регрессия`
`Big-Data`
`Spark`


## Вывод
**В ходе выполнения проекта:**

- Инициализировали локальную Spark-сессию.
	
- Прочитали содержимое файла housing.csv.
		
- Вывели типы данных колонок датасета, используя методы pySpark и выяснили что: 
    - В наборе данных представлены исключительно числовые переменные, исключение составила одна категориальная переменная - ocean_proximity.
		
- Выполнили предобработку данных:
  - Исследовали данные на наличие пропусков и выяснили что: 
	- Пропуски обнаружены только в столбце total_bedrooms — общее количество спален в домах жилого массива, пропущенные значения составляют около 1% от общего числа строк, и их удаление не повредило нашему исследованию.
  - Преобразовали колонку с категориальными значениями техникой One hot encoding.
  - Также пришли к выводу, что для числовых признаков тоже нужна трансформация — шкалирование значений — чтобы сильные выбросы не смещали предсказания модели.
		
- Построили две модели линейной регрессии на разных наборах данных:
	- используя все данные из файла;
	- используя только числовые переменные, исключив категориальные;
    - для построения модели использовали оценщик LinearRegression из библиотеки MLlib.
		
- Сравнили результаты работы линейной регрессии на двух наборах данных по метрикам RMSE, MAE и R2. И пришли к выводу, что на всех трех метриках первая модель (с использованием всех данных) показывает более лучшие значения. 
