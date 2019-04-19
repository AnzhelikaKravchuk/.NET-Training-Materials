## Читать

- [C# in Depth. Jon Skeet. Manning Publications Co. 2013](https://www.manning.com/books/c-sharp-in-depth-third-edition)
   - *Chapter 5.* [Fast-tracked delegates.](https://livebook.manning.com/#!/book/c-sharp-in-depth-third-edition/chapter-5/)
   - *Chapter 9.* [Lambda expressions and expression trees.](https://livebook.manning.com/#!/book/c-sharp-in-depth-third-edition/chapter-9/)
- [C# 5.0 Unleashed. Bart De Smet. Sams Publishing. 2013](https://www.goodreads.com/book/show/16284093-c-5-0-unleashed)
   - *Chapter 17.* Delegates.
- [Programming C# 5.0. Ian Griffiths. O'Reilly Media. 2012.](http://shop.oreilly.com/product/0636920024064.do) 
   - *Chapter 9.* Delegates, Lambdas and Events. [Download Example Code](https://resources.oreilly.com/examples/0636920024064/blob/master/Ch09.zip)
- [CLR via C#. Jeffrey Richter. Microsoft Press. 2010](https://www.goodreads.com/book/show/7121415-clr-via-c)
   - *Chapter 17.* Delegates.

## Задачи

- (deadline - 22.04.2019, 24.00) Добавить в класс ArrayExtension (класс переименовать в EnumerableExtension) [Day 13 (Day 10)](https://github.com/AnzhelikaKravchuk/.NET-Training.-Spring-2019/tree/master/Day%2013%20-%2016.04.2019) перегруженные версии обобщенно-типизированных методов расширений типизированного интерфейса `IEnumerable<T>`, используя в качестве передаваемых параметов (стратегий фильтрации, трансформации, сравнения) соответствующие делегаты ([`Predicate<T>`](https://docs.microsoft.com/en-us/dotnet/api/system.predicate-1?view=netframework-4.8), [`Converter<TInput,TOutput>`](https://docs.microsoft.com/en-us/dotnet/api/system.converter-2?view=netframework-4.8), [`Comparison<T>`](https://docs.microsoft.com/en-us/dotnet/api/system.comparison-1?view=netframework-4.8)). При реализации "методов-двойников" использовать вызовы методов на интерфейсах.
      
            public static IEnumerable<TSource> Filter<TSource>(this IEnumerable<TSource> source, IPredicate<TSource> predicate) { }
            
            public static IEnumerable<TResult> Transform<TSource,TResult>(this IEnumerable<TSource>, ITransformer<TSource, TResult> transformer) { }
            
            public static IEnumerable<TSource> SortBy<TSource>(this IEnumerable<TSource>, IComparer<TSource> comparer) { }
        
            public static IEnumerable<TSource> Filter<TSource>(this IEnumerable<TSource> source, Predicate<TSource> predicate) { }
            
            public static IEnumerable<TResult> Transform<TSource,TResult>(this IEnumerable<TSource>, Converter<TSource, TResult> transformer) { }
            
            public static IEnumerable<TSource> SortBy<TSource>(this IEnumerable<TSource>, Comparison<TSource> comparer) { }
  
- (deadline - 22.04.2019, 24.00) Как альтернативу классу EnumerableExtension создать класс Enumerable, содержащий методы для фильтрации и трансформации, использующие в качестве параметров версии типа делегат [`Func<T>`](https://docs.microsoft.com/en-us/dotnet/api/system.func-2?view=netframework-4.8), перегруженные по параметрам. Изменить метод SortBy, заменив стратегию сравнения двух элементов на стратегию сортировки по ключу (сортировка по возрастанию). Добавить метод SortByDescending, который реализует сортировку по убыванию по ключу. 
      
            public static IEnumerable<TSource> Filter<TSource>(this IEnumerable<TSource> source, Func<TSource> predicate) { }
            
            public static IEnumerable<TResult> Transform<TSource,TResult>(this IEnumerable<TSource>, Func<TSource, TResult> transformer) { }
            
            public static IEnumerable<TSource> SortBy<TSource>(this IEnumerable<TSource>, Func<TSource,TKey> comparer) { }
            
            public static IEnumerable<TSource> SortByDescending<TSource>(this IEnumerable<TSource>, Func<TSource,TKey> comparer) { }
  
- (deadline - 23.04.2019, 24.00) Разработать (использовать код [Day 1 - 19.03.2019](https://github.com/AnzhelikaKravchuk/.NET-Training.-Spring-2019/tree/master/Day%201%20-%2019.03.2019) и [Day 11 - 11.04.2019](https://github.com/AnzhelikaKravchuk/.NET-Training.-Spring-2019/tree/master/Day%2011%20-%2011.04.2019)) статичесикй класс-хэлпер для поддержки операций с обобщенными массивами (методы сортировки - быстрая и слиянием, метод бинарного поиска). Предусмотреть возможность настройки логики сравнения, используя подходы, как на основе интерфейсов, так и на основе делегатов ([делегат](https://docs.microsoft.com/en-us/dotnet/api/system.comparison-1?view=netframework-4.8)). Продумать возможный набор удобных для использования перегруженных версий методов. Продемонстрировать работу разработанных методов, используя разработанные тесты [Day 1 - 19.03.2019](https://github.com/AnzhelikaKravchuk/.NET-Training.-Spring-2019/tree/master/Day%201%20-%2019.03.2019) и пользовательские типы (класс книга [Day 8 - 04.04.2019](https://github.com/AnzhelikaKravchuk/.NET-Training.-Spring-2019/tree/master/Day%208%20-%2004.04.2019)).

### [Репозиторий вопросов и ответов](https://github.com/AnzhelikaKravchuk/.NET-Training.-Spring-2019/tree/master/.Net-Interview-Questions)

![](https://github.com/AnzhelikaKravchuk/Materials/blob/master/Pictures/Q%26A.png)
