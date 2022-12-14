# План автоматизированного тестирования сервиса покупки туров

## Перечень автоматизируемых сценариев

### Исходные данные
**При заполнении полей считать следующие данные:**
- **"Номер карты"**: 16 цифр с пробелами после каждой 4-й цифры
- **"Месяц"**: число от 01 до 12
- **"Год"**: две последние цифры текущего или последующих годов 
- **"Владелец"**: Фамилия и Имя на латинице через пробел в верхнем регистре
- **"СVC/CVV"**: три цифры

**Номера карт, используемых для тестирования:**
- Номер валидной карты : "4444 4444 4444 4441" статус карты "Approved"
- Номер не валидной карты: "4444 4444 4444 4442" статус карты "Declined"

**Примечание**
- открыта страница покупки тура http://localhost:8080/


### UI тесты

#### Оплата по карте
1. **Успешная оплата тура "Путешествие дня" при валидном заполнение полей формы "Оплата по карте" по действующей карте
Ожидаемый результат: появление сообщения об успешной оплате тура**

1. **Успешная оплата в кредит тура "Путешествие дня" при валидном заполнение полей формы "Кредит по данным карты" по действующей карте 
   Ожидаемый результат: появление сообщения об успешной взятие кредита**

1. **Отказ в оплате тура "Путешествие дня" при валидном заполнение полей формы "Оплата по карте" по declined карте  
   Ожидаемый результат: появление сообщения об отказе в оплате тура**

1. **Отказ в кредите на покупку тура "Путешествие дня" при валидном заполнение полей формы "Кредит по данным карты" по declined карте 
   Ожидаемый результат: появление сообщения об отказе в взятие кредита**

1. **Оставление поля "Номер карты" пустым, остальные поля заполнены валидно в форме "Оплата по карте" тура "Путешествие дня"  
   Ожидаемый результат: под полем "Номер карты" появиться предупреждение о незаполненном поле**

1. **Заполнение поля "Номер карты" 15 цифрами, остальные поля заполнены валидно в форме "Оплата по карте" тура "Путешествие дня"  
   Ожидаемый результат: под полем "Номер карты" появиться предупреждение о недопустимой длине поля**

1. **Оставление поля "Месяц" пустым, остальные поля заполнены валидно в форме "Оплата по карте" тура "Путешествие дня"  
   Ожидаемый результат: под полем "Месяц" появиться предупреждение о пустом поле**

1. **Заполнение поля "Месяц" номером с 1 до 9, остальные поля заполнены валидно в форме "Оплата по карте" тура "Путешествие дня"  
   Ожидаемый результат: отправка формы невозможна, предупреждение "Неверный формат" под полем "Месяц"**

1. **Заполнение поля "Месяц" значением 00, остальные поля заполнены валидно в форме "Оплата по карте" тура "Путешествие дня"  
   Ожидаемый результат: под полем "Месяц" появиться предупреждение о не валидном значении**

1. **Заполнение поля "Месяц" значением 01, остальные поля заполнены валидно в форме "Оплата по карте" тура "Путешествие дня"  
   Ожидаемый результат: появление сообщения об успешной оплате тура**
   
1. **Заполнение поля "Месяц" значением 13, остальные поля заполнены валидно в форме "Оплата по карте" тура "Путешествие дня"  
   Ожидаемый результат: под полем "Месяц" появиться предупреждение о не валидном значении**

1. **Оставление поля "Год" пустым, остальные поля заполнены валидно в форме "Оплата по карте" тура "Путешествие дня"  
   Ожидаемый результат: под полем "Год" появиться предупреждение о пустом поле**

1. **Заполнение поля "Год" предыдущим годом, остальные поля заполнены валидно в форме "Оплата по карте" тура "Путешествие дня"  
   Ожидаемый результат: под полем "Год" появиться предупреждение о не валидном значении**
 
1. **Оставление поля "Владелец" пустым, остальные поля заполнены валидно в форме "Оплата по карте" тура "Путешествие дня"  
   Ожидаемый результат: под полем "Владелец" появиться предупреждение о пустом поле**

1. **Заполнение поля "Владелец" валидными данными с дефисом, остальные поля заполнены валидно в форме "Оплата по карте" тура "Путешествие дня"  
   Ожидаемый результат: появление сообщения об успешной оплате тура**

1. **Заполнение поля "Владелец" латиницей в верхнем регистре, остальные поля заполнены валидно в форме "Оплата по карте" тура "Путешествие дня"  
   Ожидаемый результат: появление сообщения об успешной оплате тура**

1. **Заполнение поля "Владелец" кириллицей, остальные поля заполнены валидно в форме "Оплата по карте" тура "Путешествие дня"  
   Ожидаемый результат: под полем "Владелец" появиться предупреждение о не валидном значении**

1. **Заполнение поля "Владелец" фамилию на латинице без имени, остальные поля заполнены валидно в форме "Оплата по карте" тура "Путешествие дня"  
   Ожидаемый результат: под полем "Владелец" появиться предупреждение о не валидном значении**

1. **Заполнение поля "Владелец" цифрами, остальные поля заполнены валидно в форме "Оплата по карте" тура "Путешествие дня"  
   Ожидаемый результат: под полем "Владелец" появиться предупреждение о не валидном значении**

1. **Заполнение поля "Владелец" спецсимволами, остальные поля заполнены валидно в форме "Оплата по карте" тура "Путешествие дня"  
   Ожидаемый результат: под полем "Владелец" появиться предупреждение о не валидном значении**

1. **Оставление поля "CVC/CVV" пустым, остальные поля заполнены валидно в форме "Оплата по карте" тура "Путешествие дня"  
   Ожидаемый результат: под полем "CVC/CVV" появиться предупреждение о пустом поле**

1. **Заполнение поля "CVC/CVV" 2 цифрами, остальные поля заполнены валидно в форме "Оплата по карте" тура "Путешествие дня"  
   Ожидаемый результат: под полем "CVC/CVV"  появление сообщения о недопустимой длине**

1. **Заполнение поля "CVC/CVV" 1 цифрой, остальные поля заполнены валидно в форме "Оплата по карте" тура "Путешествие дня"  
   Ожидаемый результат: под полем "CVC/CVV"  появление сообщения о недопустимой длине**

### API-тесты
#### Post запросы

1. Отправка валидных данных действующей карты 4444 4444 4444 4441 (approved) на URL-адрес http://localhost:9999/payment   
   **Ожидаемый результат:** ответ сервера: код 200

2. Отправка валидных данных недействующей карты 4444 4444 4444 4442 (declined) на URL-адрес http://localhost:9999/payment  
   **Ожидаемый результат:** ответ сервера: код 200

3. Отправка валидных данных действующей карты 4444 4444 4444 4441 (approved) на URL-адрес http://localhost:9999/credit  
   **Ожидаемый результат:** ответ сервера: код 200

4. Отправка валидных данных недействующей карты 4444 4444 4444 4442 (declined) на URL-адрес http://localhost:9999/credit  
   **Ожидаемый результат:** ответ сервера: код 200


## Перечень используемых инструментов с обоснованием выбора
* JDK 11 - Язык программирования на котором будет написан проект
* IntelliJ IDEA - Код автотестов написан на Java, IntelliJ IDEA - инструмент для написания автотестов на java
* Gradle - Легче писать код, управлять зависимостями
* JUnit - Удобный фреймворк, есть все необходимые аннотации  
* Lombok - Автоматически генерируются конструкторы
* Selenide - Удобный фреймворк для написания автотестов 
* Docker - Для БД в нашем проекте
* Allure - Для составления отчетов

## Перечень и описание возможных рисков при автоматизации
* если будет изменен интерфейс/добавлены еще какие-то фичи в форме оплаты, то придется переделывать тесты
* отсутствие спецификации на приложении
* сразу использованы две базы данных, что добавляет сложностей при настройке SUT

## Интервальная оценка с учётом рисков (в часах):
* Настройка SUT - 12 часов
* Разработка тест-плана - 10 часов
* Написание авто-тестов и их прогон - 60 часов
* Написание баг-репортов - 10 часов
* Написание отчета по результатам автоматизации - 6 часов
* Настройка CI - 6 часов
* Устранение замечаний - 

## План сдачи работ
1. Разработка автотестов: 17 октября 2022 г.
2. Баг-репорты и отчет по результатам теста: 18 октября 2022 г.
3. Отчет по результатам автоматизированного тестирования: 19 октября 2022 г.
