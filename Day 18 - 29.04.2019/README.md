## Читать

- [C# in Depth. Jon Skeet. Manning Publications Co. 2013](https://www.manning.com/books/c-sharp-in-depth-third-edition)
   - *Chapter 11.* [Query expressions and LINQ to Objects.](https://livebook.manning.com/#!/book/c-sharp-in-depth-third-edition/chapter-11/)
   - *Appendix A.* [LINQ standard query operators.](https://livebook.manning.com/#!/book/c-sharp-in-depth-third-edition/appendix-A/)
- [C# 6.0 in a Nutshell. Joseph Albahari, Ben Albahari. O'Reilly Media. 2015.](http://shop.oreilly.com/product/0636920040323.do)
   - *Chapter 8.* LINQ Queries. [Code Listings](http://www.albahari.com/nutshell/ch08.aspx)
   - *Chapter 9.* LINQ Operators. [Code Listings](http://www.albahari.com/nutshell/ch09.aspx)
- [C# 5.0 Unleashed. Bart De Smet. Sams Publishing. 2013](https://www.goodreads.com/book/show/16284093-c-5-0-unleashed)
   - *Chapter 19.* Language Integrated Query Essentials.
   - *Chapter 20.* Language Integrated Query Internals
- [101 LINQ Samples](https://code.msdn.microsoft.com/101-LINQ-Samples-3fb9811b)

## Постановка задания

- Скачать архив *LINQ - Sample Queries.zip* демонстрационного приложения для изучения LINQ.

- Запустить приложение (папка C#, SampleQueries.sln), изучить основные запросы LINQ to Object - **101 LINQ Query Samples** (код находится в классе *LinqSamples*).
 
 ![](https://github.com/AnzhelikaKravchuk/Materials/blob/master/Pictures/Screenshot.png)
 
- Добавить в приложение класс *CustomSamples* производный от класса *SampleHarness*, класс декорировать атрибутами 
    > [Title("LINQ Query Samples")]   
    > [Prefix("Linq")]
    
 - Добавить в класс *CustomSamples* методы, каждый из которых является решением соответствующего пункта задания, методы именовать по шаблону *LinqQueryN* где N номер задания по порядку (01,02...). Методы декорировать атрибутами 
    > [Category("Category method here...")]`(опционально)   
    > [Title("Title method here...")]    
    > [Description("Description method here...")]  
    
  - Проверить результ, запуская приложение и просматривая полученный результат.

### Задание. 

1.	Получить список всех клиентов, сумма всех заказов которых превосходит некоторую заданную величину.
2.	Для каждого клиента получить список поставщиков, находящихся в той же стране и том же городе. Задание выполнить, как используя операцию группировки, так и без нее.
3.	Получить список тех клиентов, заказы которых превосходят по сумме заданную величину.
4.	Получить список всех клиентов в отсортированном виде по году, месяцу, оборотам клиента (от максимального к минимальному) и имени клиента.
5.	Получить список тех клиентов, у которых указан нецифровой почтовый код или не заполнен регион или в телефоне не указан код оператора (что равнозначно «нет круглых скобок в начале»).
6.	Сгруппировать все продукты по категориям, внутри – по наличию на складе, внутри последней группы - по стоимости.
7.	Сгруппировать все товары по группам «дешевые», «средняя цена», «дорогие», определив границы каждой группы произвольным образом.
8.	Рассчитать среднюю сумму заказа по всем клиентам из данного города и среднее количество заказов, приходящееся на клиента из каждого города.
9.	Cоставить свои запросы (не менее 5) к наборам данных, описанных классами Product, Customer, Supplier, Order.


### [Репозиторий вопросов и ответов](https://github.com/AnzhelikaKravchuk/.NET-Training.-Spring-2019/tree/master/.Net-Interview-Questions)

![](https://github.com/AnzhelikaKravchuk/Materials/blob/master/Pictures/Q%26A.png)
