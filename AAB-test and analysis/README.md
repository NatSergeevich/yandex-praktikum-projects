# Анализ поведения пользователей мобильного приложения
## Цель исследования — - изучить воронку продаж. Узнать, как пользователи доходят до покупки. Сколько пользователей доходит до покупки, а сколько — «застревает» на предыдущих шагах? На каких именно?

 - исследовать результаты A/A/B-эксперимента. Дизайнеры захотели поменять шрифты во всём приложении, а менеджеры испугались, что пользователям будет непривычно. Договорились принять решение по результатам A/A/B-теста. Пользователей разбили на 3 группы: 2 контрольные со старыми шрифтами и одну экспериментальную — с новыми. Нужно выяснить, какой шрифт лучше.

## План исследования
О качестве данных ничего не известно. Поэтому перед исследование понадобится обзор данных. Необходимо проверить данные на ошибки и оценить их влияние на исследование. Затем, на этапе предобработки найти возможность исправить самые критичные ошибки данных.

Таким образом, исследование пройдёт в несколько этапов:

 1. Изучение общей информации.
 2. Подготовка данных.
 3. Изучение и проверка данных.
 4. Изучение воронки событий.
 5. Изучение результатов эксперимента.
 6. Общий вывод.

## Общий вывод
В ходе исследования быди изучены данные о работе мобильного приложения-магазина. Данные были получены в ходе проведения эксперимента результаты A/A/B-эксперимента. 

В ходе проверки и изучения данных было обнаружено, что данные до 1 августа 2019 года неполные и содержат очень мало записей. Поэтому было решено отбросить записи до 01.08.2019. В результате было удалено около 1% данных, потери были незначительны, при этом распределение количества записей по дням нормализовалось.

Воронка событий выглядит так:

 - Пользователь открывает приложение, попадает на главный экран, помечается событие `MainScreenAppear`;
 - После пользователь просматривает предложения к покупке - помечается событие `OffersScreenAppear`;
 - Пользователь добавляет то, что ему понравилось, в корзину, и открывает её - это событие `CartScreenAppear`;
 - отметка `PaymentScreenSuccessful` появляется, когда пользователь оплатил покупку.
 
На первый этап попадает 98% пользователей. Вероятно, это связано с тем, что у пользователя есть возможность перейти напрямую к каталогу через пуш-уведомление приложения или ссылку в письме в рассылке по электронной почте. Поэтому начинают свой путь с первого шага не все пользователи.

Наибольшая потеря пользователей происходит на этапе перехода с первого шага на второй - 62% пользователей переходит на второй шаг, в дальнейшем на третий шаг переходит 81% пользователей, на четвёртый 95%. Всего до четвёртого шага доходит 48% от пользователей, попавших на первый шаг.

А/А-тест показал, что статистически значимых отличий в долях между переходами со всех шагов нет: разбиение на группы работает корректно.

A/B-тест показал: в конечном итоге в сравнении как с обеими контрольными группами, так и с объединённой контрольной группой тестовая группа не показала значимых отличий.

При проверке выводов с пониженным уровнем статистической значимости в 0.003125 статистически значимой разницы нет.

A/B-тест можно остановить, и признать, что тестовая группа не показала более высоких результатов.