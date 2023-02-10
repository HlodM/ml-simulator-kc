Класс Experiment реализует метод group, который возвращает группу, к которой относится клик. 
Метод разделяет клики пропорционально весу группы детерменированным алгоритмом: для экспериментов с 
одинаковыми параметрами один и тот же click_id попадет в одну и ту же группу.
Для разных экспериментов с разными experiment_id клики распределяются по группам по-разному. 

В statistical_test функции:
- cpc_sample - генерирует CPC (cost-per-click) выборку нужного размера с нужными характеристиками.
- t_test - проводит статистический тест двух выборок с заданным уровнем значимости α и возвращает оценку, есть ли статистически значимое различие между выборками или нет.
- aa_test - генерирует двe CPC выборки с одинаковыми характеристиками и проводит t-тест заданное количество раз. Возвращает долю симуляций, где t_test зафиксировал ошибку первого рода.
- ab_test - генерирует двe CPC выборки, конверсии которых отличаются на заданное значение MDE (minimal detectable effect), и проводит t-тест заданное количество раз. Возвращает долю симуляций, где t_test зафиксировал ошибку второго рода.
- select_sample_size, select_mde - возвращают подобранный из сетки параметр и уровни ошибок первого и второго рода (в пределах заданных значений) при этом параметре.

В sample_size_and_mde_calc функции для теоретического расчета (можно использовать при определенных условиях) sample_size и mde. 