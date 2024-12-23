# Сумма элементов вектора

Алгоритм суммирования элементов вектора на GPU и CPU представлен и реализован на языке Python в блокноте.

Ниже представлена таблица с временем выполнения операции суммирования элементов вектора на графическом процессоре и центральном процессоре:

| Размерность | CPU             | GPU          | Ускорение|
| ----------- | --------------- | ------------ | -------|
| 1000        | 0.000016975     | 0.00032713   | 0.0519 |
| 51000       | 0.000051972     | 0.00114645   | 0.0453 |
| 101000      | 0.000045488     | 0.00141596   | 0.0321 |
| 451000      | 0.000403638     | 0.00098772   | 0.4087 |
| 601000      | 0.000403125     | 0.00180061   | 0.2239 |
| 951000      | 0.000440012     | 0.00057936   | 0.7595 |

## Выводы

Для маленьких размерностей результаты показывают, что CPU работает быстрее, чем GPU. Это связанно с инициализацией GPU и передачей данных на графический процессор. Для таких малых задач накладные расходы на использование GPU могут перевешивать выгоды от его параллельной обработки.

С ростом размерности вектора наблюдается заметное улучшение производительности GPU. Это связано с тем, что GPU может эффективно обрабатывать большие объемы данных параллельно. При таких больших размерностях накладные расходы на инициализацию и передачу данных становятся менее значительными по сравнению с временем, необходимым для выполнения самой операции.

GPU оптимизированы для выполнения операций на больших массивах данных, особенно тех, которые могут быть параллелизованы. Когда размер вектора превышает определенный порог, параллельная обработка становится значительно более выгодной.

Некоторые затраты на производительность исходят из времени, необходимого для переноса данных между оперативной памятью и видеопамятью. На больших размерах векторов этот фактор также может оказать влияние, но в итоге преимущества параллелизма GPU становятся более выраженными.
