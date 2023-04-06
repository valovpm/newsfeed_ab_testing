# Анализ нового алгоритма для рекомендаций новостей
В данном проекте проводится анализ нового алгоритма рекомендации новостей для ленты.
Предполагается что новый алгоритм улучшит ключевую метрику Click-Through Rate (CTR).
Для анализа этого предположения, было проведено A/A и A/B тестирования.
Также было изучено влияние линеаризации на чувствительность линеаризации к изучаемой метрики.

## A/A тестирование
Цель A/A тестирования заключалась в проверке корректности системы сплитования исходных данных,
т.е. проверки что изучаемая метрика CTR не отличается между группами пользователей.
Для этого мы многократно (100,000 раз) извлекли подвыборки из наших данных из разных экспериментальных групп,
а затем сравнили их с помощью t-критерия Стьюдента.
В результате эксперимента мы обнаружили что из 100,000 пар подвыборок 4,661 продемонстрировали статистически значимую разницу,
то есть менее 5% пар подвыборок.
На основании этого был сделан вывод что система сплитования на группы является корректной.

## A/B тестирование
A/B тестирование продемонстрировало что CTR старого алгоритма превосходит CTR нового алгоритма, следовательно новый алгоритм рекомендации новостей не может быть рекомендован к внедрению.
В ходе анализа данных были использованы различные статистические критерии и трансформации данных.
Для проверки нормальности распределений использовались критерий Шапиро-Уилка и критерий Д'Агостино.
Для сравнения распределений между собой использовались Т-критерий Стьюдента и U-критерий Манна-Уитни.
Для трансформации исходных данных использовались сглаживание Лапласа, Пуассоновский бутстреп, и бакетное преобразование.

## Линеаризация метрики
Кроме A/A тестирования и A/B тестирования, был проведен анализ лайков и линеаризованных лайков.
Анализ продемонстрировал улучшение чувствительности статистических тестов к линеаризованной метрике.
