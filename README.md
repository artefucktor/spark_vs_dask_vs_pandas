# Простой тест-сравнение PySpark, Dask и Pandas

**Условия**
- Тест в локал моде, не кластер
- на ноутбуке с 16 гб оперативы
- на диске свободно еще 17 гб для раздувания файла подкачки

В тесте используются [данные MTS ML Cup 2023](https://storage.yandexcloud.net/ds-ods/files/materials/124f46f0/competition_data_final_pqt.zip)

Датасет содержит 322млн.899435 строк – история активности пользователей в интернете.

Для теста сделаем простое преобразование – распарсим урлы:
- Добавлен поларс – отличный инструмент
- Спарк справляется с этой задачей легко и непринужденно
- Даск тоже, но немного подольше.
- Пандас – у меня не получилось, даже если ограничить чтение из датасета заданными колонками, The kernel appears to have died и Out of memory.

И добавим вторую задачу – агрегацию по операционным системам устройств:
- Поларс топчик, легко и на огромной скорости!
- Спарк ок
- Даск – ядро упало
- Пандас даже не будем пробовать

**Немного оптимизации**

Память:
- Cпарксешн по умолчанию ставит очень маленький объем памяти, тогда падает джава (connection refused).
- Если разрешить использовать слишком много – падает вообще все (too low space).
- Для моих условий получилось оптимальное – 4 гб для драйвера.

Процессор:
- По умолчанию используется только одно ядро. Это долго и печально.
- В local можно указать разрешенное количество ядер или звездочку – все. Тогда скорость выполнения приятно увеличивается.

Дополнение:
- Еще в настройках ноутбука надо отключить всякие зеленые фичи типа экономии энергии )

ПыСы: да, я эталонный нищеброд )))
