# connect_limit_analys
Analysis of simultaneous connections to documents by users of different groups

Задача состоит в том, чтобы оценить, сколько в пиковые моменты потребления у нас в эти дни происходило одновременных соединений с документами (ситуация в которой несколько пользователей одновременно находятся внутри документа) и визуализировать на подходящей для этого диаграмме.

Сейчас на всех серверах одновременно, исходя из нашего тарифа, мы можем предоставить пользователям не более 3000 одновременных подключений.

В результате анализа нужно увидеть, насколько далеко мы от лимитов в 3000 одновремнных подключений к документу. Также найти в данных, что сильнее всего влияет на величину одновременных подключений. Т.е. если бы мы захотели их уменьшить, с какого типа пользователей или порталов нам стоило бы начать.

Предполагаемый алоритм выполнения:

1. Просмотр информации о данных: пропуски, уникальные значения, формат даннных и т.п.
2. Создание нового столбца, который будет содержать значение 1 для каждой строки (с целью дальнейшего подсчета количества подлючений).
3. Создание нового столбца с длительностью подключения - разница между start_edit_time и conn_end_time.
4. Группировка данных по времени и подсчет общего количества подключений для каждого временного интервала.
5. Создание линейной диаграммы для визуализироования количества одновременных подключений во времени.
6. Определить максимальное количество одновременных подключений и сравнить его с лимитом в 3000.
7. Используя группировку и агрегацию, определить, какие типы пользователей или порталов имеют наибольшее влияние на количество одновременных подключений.
8. Выводы и рекомендации для уменьшения количества одновременных подключений, если это необходимо.
