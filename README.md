# flight_delay
 
Обзор данных 

Описание работы:
----
Перед компаниями авиаперевозчиками зачастую возникает необходимость оптимизации полетов и услуг. Для авиакомпании крайне важно мнение клиентов , 
ведь от этого напрямую зависит заработок. Мнения клиентов может быть крайне негативными. Как правило это связано с плохим качеством услуг на борту 
самолета или же из за задержек рейсов. В данном случае сделаем проект по определению длительности задержки рейсов. Нам предстоит определить основные 
причины задержек, выявить взаимосвязь между типами самолетов и  причины задержек ну и создать модель для  определения продолжительность задержек. 



Цель работы:
----
Определения задержки рейса в минутах.



О данных
-----
flight_delays.csv содержит в себе следующию информацию.

Flight_ID: Уникальный номер для каждого рейса

Airlines: Название авиакомпании

Origin_Airport: Код аэропорта отправления

Destination: Код аэропорта, до которого нужно добраться, или аэропорта назначения

ScheduledDeparture: Время запланированного вылета

ActualDeparture: Точный момент отправления

ScheduledArrival: Время запланированного прибытия

ActualArrival: Фактическое время прибытия

DelayMinutes: Задержка прибытия на несколько минут

DelayReason: Причина задержки

AircraftType: Тип самолетов 

TailNumber: Идентифиционный номер самолета

Distance: Дистанция 


План работы
---

1. Загрузка данных 

2. Анализ данных 

3. Подготовка данных к обучению 

4. Обучение 

5. Вывод





Результаты:
---

**Просмотр данных:**

Датафрейм содержит в себе 1747626 строк и 14 столбцов.

В DelayReason выявлены пропуски


**Подготовка данных:**

4 строки переведены в временой формат

Созданы 3 новых призныка


**Анализ данных**

Все авиакомпании совершили примерно одинаковое число вылетов

Как мы можем наблюдать Лидером авиаперевозок из аэропорта ATL является Американские авиалинии

Как мы можем увидеть для Airbus A320 главной причиной по продолжительности задержекой является Maintenance. Однако по количеству задержек на данный тип самолетов Air Traffic Control

Для Boeing 737 главной причиной по продолжительности задержекой является Air Traffic Control. И по количеству задержек Air Traffic Control

Для Boeing 777 главной причиной по продолжительности задержекой является Weather. И по количеству задержек Weather

В целом боинги кажутся более предсказуемыми чем Airbus

Бортовые номера самалетов. Каждый самолет имеет уникальный бортовой номер. Как мы можем видеть ниже все самолеты совершали более одного полета

Как мы можем видеть рекортсменом по количеству и по длительности длительных задержок является Southwest. А вот Delta менее всех имеет длительное число задержек.

В принципе все самолеты "Длительных ожиданий" имеют среднее 28 минутное время ожидания. Нельзя сказать что причиной являются проблемы с самолетами

Все вылеты и состоялись в 2024 году между 1-2 сентебря. Данный сценарий кажется крайне маловероятным. Учитывая количество перелетов в 1.8 миллионов. 
Складывается впячетления что данные сгенерированы в ручную или собраны с грубыми ошибками. 

Среднее время ожидания 9 мин. Есть рейсы которые прилетают раньше положенного срока

Средняя дистанция перелетов 1500 миль

Среднее время полета состовляет 200 мин

Среднее время задержки вылета состовляет 15 мин

Примечание
---
Данные скорей всего подтасованы. Или же в результате сбора данных произошла ошибка. Так как все полеты были совершины в 1-2 сентебря 2024 года.
---

Мультиколлинеарность между числовыми призныками не выявлено.


**Подготовка данных для обучения модели и обучение модели** 
(Скажем сразу, что не стоить ожидать хороших резльтата от модели. Так как данные явно сгенерированы или собраны с грубыми ошибками)

Данные разделены на 80% обучающей и 20% тестовой

Данные масштбированы и закадированы

Обучена модель линейной регресии.

В результате обучения получена МАЕ равное 7. 

МАЕ равное 7 значить что ошибка при предсказывании задержки состовляет 7 минут. Это и не удевильно ведь как мы уже даказали при Анализ данных. В данные собраны с грубыми ошибками или подтосованы. 



Рекомендации:
----

Мы выяснили что в США за год совершается около  9 639 096 миллионов авиарейсов а в нашем датафрейме 
указано 1.3 миллиона только за 1-2 два дня.  То скорей всего при сборе данных произошла ошибка. Рекомендуется перепроверить данные. 
Также в виду наличие большого числа категориальных данных можно предположить использование алгоритма случайного леса с подбором гиперпараметров.  

код указаны в файле 

predict_delay.ipynb
---