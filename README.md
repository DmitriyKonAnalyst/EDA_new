# Разведочный анализ (EDA) - Т-Банк: поездки на самокатах

## Стек:

<div>
  <img src="https://img.shields.io/badge/python-white?logo=python&style=for-the-badge" title="Python" alt="Python" height="40"/>&nbsp;
  <img src="https://img.shields.io/badge/pandas-white?logo=pandas&logoColor=blue&style=for-the-badge" title="Pandas" alt="Pandas" height="40"/>&nbsp;
  <img src="https://img.shields.io/badge/numpy-white?logo=numpy&logoColor=black&style=for-the-badge" title="Numpy" alt="Numpy" height="40"/>&nbsp;
  <img src="https://img.shields.io/badge/scipy-white?logo=scipy&logoColor=black&style=for-the-badge" title="Scipy" alt="Scipy" height="40"/>&nbsp;
  <img src="https://img.shields.io/badge/matplotlib-white?logo=matplotlib&logoColor=black&style=for-the-badge" title="Matplotlib" alt="Matplotlib" height="40"/>&nbsp;
  <img src="https://img.shields.io/badge/pingouin-white?logo=pingouin&logoColor=black&style=for-the-badge" title="Pingouin" alt="Pingouin" height="40"/>&nbsp;
  <img src="https://img.shields.io/badge/requests-white?logo=requests&logoColor=black&style=for-the-badge" title="Requests" alt="Requests" height="40"/>&nbsp;
  <img src="https://img.shields.io/badge/urllib-white?logo=urllib&logoColor=black&style=for-the-badge" title="urllib" alt="urllib" height="40"/>&nbsp;
</div>

## Цели проекта:

1. Понимание структуры и характеристик набора данных
2. Выявление аномалий и выбросов
3. Идентификация связей и корреляций между переменными
4. Подготовка данных для дальнейших этапов анализа


## Данные:

groups.csv – файл с информацией о принадлежности пользователя к контрольной или экспериментальной группе (А – контроль, B – целевая группа).
| Название поля             | Описание                                                                                 |
|---------------------------|------------------------------------------------------------------------------------------|
| order_rk                  | Идентификатор заказа (поездки)                                                           |
| party_rk                  | Идентификатор клиента                                                                    |
| gender_cd	                | Пол клиента                                                                              |
| age                       | Возраст клиента                                                                          |
| education_level_cd        | Уровень образования клиента:                                                             |
|                           | SCH — начальное, среднее                                                                 |
|                           | GRD — высшее                                                                             |
|                           | UGR — неполное высшее                                                                    |
|                           | PGR — два высших                                                                         |
|                           | ACD — ученая степень                                                                     |  
| marital_status_cd	        | Семейный статус человека:                                                                | 
|                           | IMR — состоит в незарегистрированном браке                                               |  
|                           | MAR —женат/замужем                                                                       |  
|                           | DLW — не проживает с супругом(ой)                                                        |  
|                           | OMR — состоит в зарегистрированном браке                                                 |  
|                           | CIV — гражданский брак                                                                   |  
|                           | UNM — холост/не замужем                                                                  |  
|                           | DIV — разведен(а)                                                                        | 
|                           | FAL — никогда не состоял(а) в браке                                                      | 
|                           | WID — вдовец/вдова                                                                       | 
| lvn_state_nm              | Регион проживания человека                                                               |
| minute_cost               | Стоимость минуты                                                                         |
| activation_cost           | Стоимость активации поездки                                                              |
| hold_amount               | Размер суммы, которая замораживается на счете в момент взятия самоката                   |
| transport_model           | Название модели самоката                                                                 |
| distance_km	              | Километраж поездки                                                                       |
| created_dttm              | Дата и время создания заказа                                                             |
| book_start_dttm           | Дата и время начала поездки                                                              |
| book_end_dttm             | Дата и время завершения поездки                                                          |
| book_time_zone_cd         | Часовой пояс                                                                             |
| local_book_start_dttm     | Дата и время начала поездки в часовом поясе человека, который брал самокат               |
| nominal_price_rub_amt     | Стоимость поездки                                                                        |
| loyalty_accrual_rub_amt   | Размер выплаченного кэшбэка в рублях                                                     |
| loyalty_accrual_bns_amt   | Размер выплаченного кэшбэка в бонусах (если оплата происходила с помощью кредитной карты)|



## Результаты проекта:

1. Реализована функция для загрузки данных из файлов в проект.
2. Проведена предобработка данных.
3. Проведено детальное исследование данных, в результате которого выявлено, что в A/B тестировании участвуют 8341 активных пользователя (1538 в группе А и 6803 в группе B). Каждый платящий пользователь совершил по одному заказу. Также обнаружено, что 149 студентов оплатили, но не являются активными пользователями.
4. Определены и посчитаны ключевые метрики для проверки гипотез, такие как Conversion Rate (CR) и Average Revenue Per User (ARPU), что позволило оценить эффективность новых механик оплаты.
5. Проведена проверка данных на нормальность распределения, которая показала, что распределение не нормальное.
6. Проведена проверка на равенство дисперсий, которая показала, что дисперсии в группах равны.
7. Проведены два статистических теста: хи-квадрат и бутстрап. Оба теста показали, что статистически значимых различий между группами нет.
8. На основе проведенного анализа сделан вывод, что запуск новой механики оплаты на сайт не приведет к значительным улучшениям, и поэтому рекомендуется не вводить её в эксплуатацию.
9. Реализована функция, которая автоматически подгружает данные из файла, считает метрики по обновленным данным и строит графики, что значительно упрощает процесс анализа данных в будущем.
