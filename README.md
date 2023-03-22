# Простой тест-сравнение PySpark, Dask и Pandas
**тест в локал моде, на макбуке с 16 гб оперативы, на диске свободно еще 17гб для раздувания файла подкачки**

В тесте используются данные MTS ML Cup
[Скачать архив с датасетом](https://storage.yandexcloud.net/ds-ods/files/materials/124f46f0/competition_data_final_pqt.zip)

В датасете содержится 322млн.899435 записей – история активности пользователей в интернете.


В качестве теста сделаем простое преобразование – распарсим урлы.
- Спарк справляется с этой задачей легко и непринужденно
- Даск тоже, но немного подольше.
- Пандас – у меня не получилось, даже если ограничить чтение из датасета единственной колонки, The kernel appears to have died и Out of memory.

И добавлю вторую задачу – агрегацию по операционным системам устройств.
- Спарк ок
- Даск – ядро упало
- Пандас даже не стала пробовать