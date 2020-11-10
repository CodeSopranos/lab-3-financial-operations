# lab-3-financial-operations

НИУ ВШЭ НН. Моделирование финансовых операций. 17ПМИ.
Домашнее задание 3. Неопределенность оптимального портфеля.
Оптимизация CVaR.

Целью работы является оценка неопределенности оптимального портфеля
для нормального многомерного распределения и двух способов вычисления
оптимального портфеля (оптимизация в модели Марковица и оптимизация
CVaR)

Подготовка модели.

Выберите на рынке 20 активов (N=20). По наблюдениям за 2018 год оцените
математические ожидания доходностей и матрицу ковариаций доходностей
(используйте выборочную матрицу ковариаций). Найденные вектор средних
и матрица ковариаций будут далее использованы в экспериментах как
«истинные» вектор E=(E 1 , E 2 , …, E N ) и матрица ковариаций (σ i,j ). Убедитесь,
что матрица ковариаций невырожденная (если она близка к вырожденной, то
измените состав активов).

1. Истинный оптимальный портфель в модели Марковица с заданным
отношением к риску.

Задана константа b. Решите задачу оптимизации
-E(x)+ b σ(x) -&gt; min, x 1 +x 2 +…+x N =1, x i ≥0
(т.е. найдите оптимальный портфель с отношением к риску, равным b).
Найдите и зафиксируйте веса портфеля и значение целевой функции.
Здесь E(x)= E 1 x 1 +E 2 x 2 +…+E N x N , σ 2 (x)=∑∑ σ i,j x i x j

2. Оценка неопределенности оптимального портфеля в модели
Марковица с заданным отношением к риску.

2.1 Задайте число наблюдений T=30. С помощью генератора многомерного
нормального распределения создайте выборку размера Т из нормального
распределения с вектором математических ожиданий E=(E 1 , E 2 , …, E N ) и
матрицей ковариаций (σ i,j ).

2.2. По построенной выборке сделайте оценку E est вектора математических
ожиданий и оценку (σ est i,j ) матрицы ковариаций.

2.3 Используя эти оценки решите задачу оптимизации
-E est (x)+ b σ est (x) -&gt; min, x 1 +x 2 +…+x N =1, x i ≥0
Здесь E est (x)= E est 1 x 1 + E est 2 x 2 +…+ E est N x N , [σ est (x)] 2 =∑∑ σ est i,j x i x j
(т.е. найдите выборочный оптимальный портфель с отношением к риску,
равным b). Найдите и зафиксируйте веса портфеля и значение целевой
функции.

2.4 Сравните два портфеля: истинный (п.1) и выборочный (п.2.3). Оцените
относительную ошибку в определении весов портфеля в норме Manhattan (L 1
норма Минковского). Сделайте выводы. Сделайте сравнение в системе
координат (σ, E).

2.5. Повторите эксперимент S=40 раз и оцените среднюю относительную
ошибку по S повторениям эксперимента. Сделайте выводы. Сделайте
сравнение в системе координат (σ, E).

2.6 Предположите, что нам известны точные значения математических
ожиданий E=(E 1 , E 2 , …, E N ). Повторите пп. 2.2-2.5. используя оценку только
матрицы ковариаций (т.е. решайте задачу оптимизации
-E(x)+ b σ est (x) -&gt; min, x 1 +x 2 +…+x N =1, x i ≥0
Здесь E(x)= E 1 x 1 +E 2 x 2 +…+E N x N , [σ est (x)] 2 =∑∑ σ est i,j x i x j
Сравните точность этих портфелей и портфелей п.2.3

3. Оценка неопределенности оптимального CVaR портфеля

3.1 Уровень значимости β выбран 0,95. Число наблюдений T. Используя
сгенерированные наблюдения из п.2.1 решите задачу ЛП для определения
оптимального CVaR β портфеля. Найдите и зафиксируйте веса портфеля и
значение целевой функции CVaR.

3.2 Сравните два портфеля: истинный (п.1) и найденный в п.3.1. Оцените
относительную ошибку в определении весов портфеля в норме Manhattan (L 1
норма Минковского). Сравните с ошибкой портфеля из п. 2.3

3.3. Повторите эксперимент S раз и оцените среднюю относительную ошибку
по S повторениям эксперимента. Сделайте выводы. Сравните с ошибкой из
п. 2.5

Примечание 1. Константа b подобрана таким образом, что истинный
оптимальный CVaR портфель совпадает с истинным оптимальным
портфелем п.1. Значение константы смотри в упражнениях к теме

Примечание 2. Для сравнения результатов п.2 и п.3 используйте одни и те
же сгенерированные наблюдения.
