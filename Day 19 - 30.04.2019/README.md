## Читать
- [C# 6.0 in a Nutshell. Joseph Albahari, Ben Albahari. O'Reilly Media. 2015.](http://shop.oreilly.com/product/0636920040323.do)
   - *Chapter 6.* Framework Fundamentals. [Code Listing](http://www.albahari.com/nutshell/ch06.aspx)
- [CLR via C#. Jeffrey Richter. Microsoft Press. 2010](https://www.goodreads.com/book/show/7121415-clr-via-c)
   - *Chapter 14.* Chars, Strings, and Working with Text.

## Encoding
- [Юникод и .NET](https://m.habr.com/ru/post/193048/) - **обязательна к прочтению!**

## String
- [referencesource.String ](https://referencesource.microsoft.com/#mscorlib/system/string.cs,8281103e6f23cb5c)
- [Особенности строк в .NET](https://habr.com/ru/post/172627/) - **обязательна к прочтению!**
- [New Recommendations for Using Strings in Microsoft .NET 2.0](https://docs.microsoft.com/en-us/previous-versions/dotnet/articles/ms973919(v=msdn.10))
- [String.Intern делает строки ещё интереснее](https://habr.com/ru/post/224281/)
- [Строки в C# и .NET](https://habr.com/ru/post/165597/)
- [Строки, неизменяемость и персистентность. Невероятные приключения в коде. Перевод блога Эрика Липперта](https://blogs.msdn.microsoft.com/ruericlippert/2011/08/08/653/)

## StringBuilder
- [StringBuilder прошлое и настоящее](https://habr.com/ru/post/172689/) - **обязательна к прочтению!**
- [referencesource.StringBuilder](https://referencesource.microsoft.com/#mscorlib/system/text/stringbuilder.cs,adf60ee46ebd299f)

## Задания

1.  **(deadline - 01.04.2019, 24.00)** Реализовать метод, который принимает на вход строку **source** и количество итераций **count** (проект *StringExtension*).

          public string Convert(string source, int count)

  На каждой итерации метода объединяются нечетные символы строки и переносятся в ее начало, и четные символы, которые переносяться в конец.
  
  > Пример (строка «Привет Епам!»): 
  >    
  > 1 итерация:  «Пие пмрвтЕа!»    
  > 2 итерация: «Пепртаи мвЕ!»    
  > ...

   Результат работы метода – результат склеек символов через count итераций.

   При реализации алгоритма учесть, что входная строка может содержать очень большое количество символов, а количество итераций может быть огромным. Оптимизировать код с точки зрения быстродействия и потребления ресурсов.

   Проверить аргументы на валидность:
   - Запрещается передавать пустые строки, строки из пробелов, null.
   - Количество итераций должно быть больше 0.

   При нарушении этих условий метод генерирует исключение.

   Проверить работу метода с помощью модульных тестов (проект *StringExtension.Tests*), **к предложенным тест кейсам добавить дополнительные**.
   
   Проверить возможность работы разработанного метода с большими строками и большим количеством итераций (проект *StringExtensionWithFiles*), замерить время счета.
   
2. Для объектов класса Book, у которого есть свойства Title, Author, Year, PublishingHous, Edition, Pages и Price (за основу можно взять класс, разработанный ранее) реализовать
возможность строкового представления различного вида. Например, для объекта со значениями
    Title = "C# in Depth", 
    Author = "Jon Skeet", 
    Year = 2019, 
    PublishingHous = "Manning", 
    Edition = 4, 
    Pages = 900, 
    Price = 40$.
могут быть следующие варианты:
 - Book record: Jon Skeet, C# in Depth, 2019, "Manning", 
 - Book record: Jon Skeet, C# in Depth, 2019
 - Book record: Jon Skeet, C# in Depth
 - Book record: C# in Depth, 2019, "Manning"
 - Book record: C# in Depth и т.д.
 
Разработать модульные тесты. (NUnit фреймворк).

3. Не изменяя класс Book, добавить для объектов данного класса дополнительную (любую не существующую у класса изначально) возможность 
форматирования, не предусмотренную классом. Разработать модульные тесты. (NUnit фреймворк).

4. Представить решение задачи [Day 4 - 26.03.2019. Task 3](https://github.com/AnzhelikaKravchuk/.NET-Training.-Spring-2019/tree/master/Day%204%20-%2026.03.2019) в виде дополнительной возможности форматного вывода вещественного числа.

### [Репозиторий вопросов и ответов](https://github.com/AnzhelikaKravchuk/.NET-Training.-Spring-2019/tree/master/.Net-Interview-Questions)
![](https://github.com/AnzhelikaKravchuk/Materials/blob/master/Pictures/Q%26A.png)
